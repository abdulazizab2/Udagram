# Udagram

A simple website for uploading your photos with sign up functionality.

[Udagram Website](http://image-filtering-bucket-944182564155.s3-website-us-east-1.amazonaws.com/home)

### Documentation

- [Dependencies](docs/dependencies.md): Tools and packages required
- [Infrastructure](docs/infrastructure.md): Online services used for deployment and CI/CD
- [Pipeline](docs/pipeline.md): Diagram and explanation of the CI/CD pipeline

### Code Structure

At the **root**, we have CircleCI pipeline configuration and main scripts in package.json.

In **udagram**, there are two folders.

1- udagram-api: Backend
2- udagram-frontend: Frontend

### Installation

#### Local run (for development purposes):

1- Create a postgres database

2- Create a ```set_env.sh``` file in **udagram** folder and export the following environment variables:

```bash
export POSTGRES_USERNAME=$
export POSTGRES_PASSWORD=$
export POSTGRES_HOST=$
export POSTGRES_DB=$
export JWT_SECRET=$
```
Fill the $ with your values. and ```source set_env.sh```

3- Start the backend then start the frontend. At the project root:
```npm run api:start && npm run frontend:start```

You can access the page after starting the server at ```localhost:4200```

#### Deploying on the cloud
Provision the necessary AWS services needed for running the application:

1. In AWS, provision a publicly available RDS database running Postgres.
2. In AWS, provision a s3 bucket for hosting the uploaded files.
3. Export the ENV variables by creating a ```set_env.sh``` file in **udagram** folder
```bash
export POSTGRES_USERNAME=$
export POSTGRES_PASSWORD=$
export POSTGRES_HOST=$
export POSTGRES_DB=$
export AWS_BUCKET=$
export AWS_REGION=$
export AWS_PROFILE=$
export JWT_SECRET=$
```
1. At the root, ```npm run deploy```. Then you can access the url in the created s3 bucket (Make sure to enable static hosting)
## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1. `cd starter/udagram-frontend`
1. `npm run test`
1. `npm run e2e`

There are no Unit test on the back-end

### Tests:

Frontend:

Unit tests are using the Jasmine Framework.
```cd udagram/udagram-frontend && npm run test```

The e2e tests are using Protractor and Jasmine.
```cd udagram/udagram-frontend && npm run e2e```

Backend:

Tests not implemented
## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

## License

[License](LICENSE.txt)
