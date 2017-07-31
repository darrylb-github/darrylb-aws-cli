# darrylb/aws-cli

Simple docker image with aws-cli and redis-cli pre-installed.

Intended to be used as job image for GitLab CI jobs to enable easily calling AWS and Redis commands from CI build scripts. 

## Tags

### latest

Built from alpine:3.5 with aws-cli and redis-cli installed.

#### Usage

    image: darrylb/aws-cli
    script:
      - aws s3 cp ....
      - aws ecs update-task....
      - redis-cli -h $host -p 6379 FLUSHALL...

### docker

Same tools as latest but built from docker:latest base image instead of alpine. 

This tag is useful when building docker images for AWS ECR. 

#### Usage

If using this in Gitlab CI, see https://docs.gitlab.com/ce/ci/docker/using_docker_build.html. I recommend Docker socket binding if going down this route.

    image: darrylb/aws-cli:docker
    script:
      - aws ecr get-login....
      - docker build -t my-ecr-repo/my-image:latest .
      - docker push my-ecr-repo....
      - redis-cli -h $host -p 6379 FLUSHALL...
