# Pipeline Description


### Build

1. Install dependencies for backend and frontend
1. Transpile TS to JS for backend and frontend

### Hold

1. Manual accepting or rejecting by developer to execute more jobs in the pipeline after build is done


### Deploy

1. Push the environment variables from CircleCI to elastic beanstalk
1. Push backend to elastic beanstalk
1. Push frontend to S3 bucket
