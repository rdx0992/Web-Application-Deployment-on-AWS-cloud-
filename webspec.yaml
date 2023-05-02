version: 0.2

phases:
  install:
    runtime-versions:
      python: 3.11
    commands:
      - echo Installing AWS CLI
      - apt-get update && apt-get install -y python3-pip
      - pip3 install awscli
  build:
    commands:
      - echo Build started on `date`
      - aws s3 cp . s3://bucket-name --recursive --include "*.html" --include "*.css" --exclude "*"
  post_build:
    commands:
      - echo Website deployed on S3

artifacts:
  files:
    - index.html
    - style.css