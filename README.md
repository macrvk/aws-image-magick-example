# Amazon Linux 2 ImageMagick Binaries (From Source)

This repository builds standalone ImageMagick binaries for Amazon Linux 2 that can be copy-pasted to any AWS Lambda function or EC2 instance.

**Blog post:** https://www.bytescale.com/blog/installing-imagemagick-on-amazon-linux-2/

**AWS Lambda Full Example:** https://github.com/bytescale/aws-lambda-image-magick-resize-example

## Quick Start

1. Checkout the repository:
 
   ```bash
   git clone git@github.com:bytescale/aws-image-magick-example.git
   
   cd aws-image-magick-example
   ```
   
2. Build the docker image:

   ```shell
   docker build \
     --platform linux/amd64 \
     -t amazonlinuxmagick .
   
   docker build --platform linux/amd64 -t amazonlinuxmagick .
   ```

3. Extract the docker image's ImageMagick binaries:

   ```shell
   docker run \
     --rm -it \
     --platform linux/amd64 \
     -v $(pwd)/binaries:/root/output \
     amazonlinuxmagick \
     mv /root/result /root/output
   
   docker run --rm -it --platform linux/amd64 -v C:\Users\macrv\WebstormProjects\aws-image-magick-example/binaries:/root/output amazonlinuxmagick mv /root/result /root/output
   ```

4. `./binaries/result` on your host machine now contains a portable set of ImageMagick binaries!
5. `cd ./binaries/result`
6. `zip -ry ../resultado.zip *`
7. `sudo unzip resultado.zip -d /`

## Varios


**Error 'no such file or directory':** https://unix.stackexchange.com/questions/433444/cant-run-script-file-in-docker-no-such-file-or-directory

**aws-lambda-base-images** https://github.com/aws/aws-lambda-base-images

**Amazon linux ECR** https://gallery.ecr.aws/amazonlinux/amazonlinux

**imagemagick-aws-lambda-2** https://github.com/serverlesspub/imagemagick-aws-lambda-2

**Docker Lambda Lambci** https://github.com/lambci/docker-lambda
