# Databox

The Databox platform. See http://www.databoxproject.uk/ for more information

## Installation

All Databox components, including the container manager, run in Docker
containers. So,
first [install and run Docker](https://www.docker.com/products/docker), and
then
[install `docker-compose`](https://docs.docker.com/compose/install/#install-compose).

## Operation

Once docker is installed, just run the following to get your databox up and
running using images published to <https://hub.docker.com/r/databoxsystems>:

    ./databox-start

Once it's started point a web browser at <https://127.0.0.1:8989> and have fun.

To stop databox and clean up,

    ./databox-stop

## Development

To develop on the platform and core components run

    ./databox-start dev

This will clones all the relevant repositories locally, and builds them into the
required Docker images. To try your component out, add your code into a
directory with a Databox manifest and `Dockerfile`, and then add a reference to
it in `docker-compose-dev-local-images.yaml`. Your image will then be built
alongside the platform. To install your app, upload the manifest to the local
app store on <http://127.0.0.1:8181> and it should then become visible in the
UI, ready for you to install.

### Get Started with the Graphical SDK

The graphical SDK will allow you to quickly build and test simple databox apps. To start the sdk run:

	./databox-start sdk

The SDK web UI is available at http://127.0.0.1:8086

To stop the SDK run: 

	./databox-stop sdk

## Contributing 

The databox project welcomes contributions via pull requests see [CONTRIBUTING.md](./CONTRIBUTING.md) for more information.

## Known issues

- TLS certificates invalid.

  In some cases, the time in docker containers on Mac can get out of sync with
  the system clock. This causes the HTTPS certs generated by the CM from being
  valid. See <https://github.com/docker/for-mac/issues/17>. Fix by restarting
  Docker for Mac.
