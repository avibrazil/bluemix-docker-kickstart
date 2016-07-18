Bluemix with Docker and automated full-stack deployments
========================================================

A boilerplate and source code kickstarter for your Bluemix+Docker app.

![Docker on Bluemix app architecture](https://avi.alkalay.net/articlefiles/2016/07/app-architecture.png)

About this repo
===============

The source code in this repo is educational and serves as a basis for you to organize your Bluemix with Docker app.

Additionally, it provides great reference and examples to make full stack app deployments,
including Bluemix services creation, CloudFoundry app deployment, Docker images
preparation, and Docker containers to CloudFoundry apps binding. The examples are provided
in 2 strategies: through ⓐ [Bluemix DevOps Services pipeline](https://avi.alkalay.net/2016/07/bluemix-docker-delivery-pipeline.html#deployment) (see [the pipeline as code](.bluemix/pipeline.yml)) and through ⓑ [a simple shell
script](https://avi.alkalay.net/2016/07/bluemix-docker-delivery-pipeline.html#deployment)
that can be executed from your laptop (see [`admin/deploy`](admin/deploy)).

This repo is [extensively documented on my blog: https://avi.alkalay.net/2016/07/bluemix-docker-delivery-pipeline.html](https://avi.alkalay.net/2016/07/bluemix-docker-delivery-pipeline.html)

If you [click to deploy](https://bluemix.net/deploy?repository=https://github.com/avibrazil/bluemix-docker-kickstart), this repo, as an example, will fully install a WordPress site on a Docker container group using a Bluemix-native ClearDB MySQL as backend.

