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

See the [GovReady-Q Docker Deployment README](https://github.com/GovReady/govready-q/blob/master/deployment/docker/README.md) for additional commands helpful for running the Docker image.



Credits
-------

Generic server icon by [Stock Image Folio from Noun Project](https://thenounproject.com/search/?q=computer&i=870428).
