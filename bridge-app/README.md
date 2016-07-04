The bridge app exists only to hold together the Bluemix services needed by your Docker
containers.

manyfest.yml states the bridge-app is a noop-buildpack, which means nothing is expected
to run here. So there is nothing to be deployed. But CloudFoundry fails if there are no
files to deploy, so we create an empty place holder file for it not to fail.