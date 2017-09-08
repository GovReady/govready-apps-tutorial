Compliance Apps for GovReady-Q: A Tutorial
==========================================

Authoring with Docker
---------------------

The fastest way to get started creating compliance apps is to use GovReady-Q's Docker image.

First, clone this repository to get the tutorial's sample apps:

	git clone https://github.com/GovReady/govready-apps-tutorial

Then start the GovReady-Q Docker image using a "bind mount" to make the sample apps on your computer available to the Docker container:

	CONTAINER=$(docker container run \
	--detach -p 8000:8000 \
	--mount type=bind,src=/absolute/path/to/govready-apps-tutorial/apps,dst=/mnt/apps \
	govready/govready-q)

Create a Django database superuser and set up your first organization:

	docker container exec -it $CONTAINER ./first_run.sh

Visit your organization in your web browser at:

	http://localhost:8000/

The "Sample Component App" and "Sample Top Level App" will appear in your list of available compliance apps. The built-in editor will automatically appear when you add either app to a work folder because you are logged in as a superuser and both apps are sourced from your local file system. (It is only possible to author/edit apps that are sourced from the local file system.)

To pause and restart the container without destroying its data:

	docker container stop $CONTAINER
	docker container start $CONTAINER

To destroy the container and all user data entered into Q:

	docker container rm -f $CONTAINER

See the [GovReady-Q Docker Deployment README](https://github.com/GovReady/govready-q/blob/master/deployment/docker/README.md) for additional commands helpful for running the Docker image.


Credits
-------

Generic server icon by [Stock Image Folio from Noun Project](https://thenounproject.com/search/?q=computer&i=870428).
