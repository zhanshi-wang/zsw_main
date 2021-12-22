# Chipmunk: A simple webapp develeped using docker

## Development
```
# Local build
docker-compose -f docker-compose-dev.yml run web

# Run tests
docker-compose -f docker-compose-dev.yml run tests
```

## Deployment
- Create an AWS Elastic Beanstalk instance named chipmunk
- Uncomment corresponding deploy section in .travis.yml
- Modify deploy section to match the new Elastic Beanstalk environment
