# Swaggy

Is your code swag enough?

With Swaggy, you can check code style on your favorite GitHub repositories!

## Prerequisite

### Build linter images

    make images

The first build takes a lot of time. If you want you can also pull official
images:

    make images-pull

If you want to push these images to your own repository:

    REPOSITORY="<you repository>" make images-push

### Set Docker remote API url

You need to specify a docker remote API url to connect with.

    export DOCKER_URL="http://127.0.0.1:2375"

If your are using Docker API through `https`, your `DOCKER_CERT_PATH` will be
mounted has a volume inside the container.

>Be careful: boot2docker enforces tls verification since version 1.3.

## Launch the web application

    make run

The web app should now be listening on port 3000 on your docker daemon (if you
are  using boot2docker, `boot2docker ip` will tell you its address).

You can also run Grounds in production mode:

    RAILS_ENV=production make run

>When running in production mode, a default secret key is set as convenience,
but this should be changed in production by specifying `SECRET_KEY_BASE`.
