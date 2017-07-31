# darrylb/aws-cli

Built from alpine with aws-cli and redis-cli tools installed. 

Used as image for Gitlab CI jobs to enable triggering aws cli calls without having to install the tools as part of the CI job.

## Usage in gitlab-ci

    image: darrylb/aws-cli
    script:
      - aws s3 cp ....
      - aws ecs update-task....
      - redis-cli -h $host -p 6379 FLUSHALL...