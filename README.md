# homework2-template
A template for CS590 intruduction to Software Containerization Homework 2

## Assignment Requirements
Follow the hints in this README file in order to complete the assignment. A successful assignment will use
the provided nginx configuration and the production asset bundle of the react application to host make the
application available via the url http://localhost:8000. **The Dockerfile should use the workdir /app.**
The use of workdir is mainly to create a clean workspace for your application code. Using the root directory
of the container is seen as bad practice.

## How to build and run a react application
In order to run the application, The dependencies must be installed and the static asset bundle must be built.
To accomplish this, the dependency manager yarn should be used. The following sequence of commands handle 
the installing and building of dependencies.

```
yarn install
yarn run build
```

The `yarn install` command creates a folder `node_modules` and downloads the appropriate dependencies as defined
by the `package.json` file. These dependencies are stored in the `node_modules` folder. The `yarn run build`
command produces the production static asset bundle. The command creates the `/build` folder which contains
the full production bundle. For running the application with the provided nginx file, the contents of `/build`
should be copied to the `/public` directory. The build will contain an index.html file designed to receive
all of the appropriate requests from nginx and handle the requests on the appropriate routes in the application.


## How to prepare the nginx configuration
The supplied nginx configuration should be used to override the default nginx configuration. To override the default
nginx configuration, the file `nginx.conf` should be copied to the location `/etc/nginx/conf.d/default.conf`.
