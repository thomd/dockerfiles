## build

    docker build -t thomd/awscli .

## run

    docker run \
      --env AWS_ACCESS_KEY_ID=<YOUR_ACCESS_KEY> \
      --env AWS_SECRET_ACCESS_KEY=<YOUR_SECRET_ACCESS> \
      --env AWS_DEFAULT_REGION=eu-central-1 \
      thomd/awscli

## set alias

    aws() {
      docker run -it --rm \
        -v "${HOME}/.aws:/root/.aws" \
	--log-driver none \
	--name aws \
	thomd/awscli "$@"
    }

