I created this repository just to illustrate a bug in the JSPM framework.

# Install a local NPM repository #
To test this, you will need to run an NPM server locally. I am suggesting using Sinopia. If you already have a local NPM repository, you can skip these steps.

I'm pretty sure that I would get the same error using the official NPM repository. But I do not want to publish this package into the official NPM repository unnecessarily.

Run the following commands to install Sinopia.

    npm install -g sinopia
    sinopia

In a new command prompt:

    npm adduser --registry http://localhost:4873/
    npm set registry http://localhost:4873/

# Publish this package to your local NPM repo #

Get the source code for this package.

    git clone https://github.com/ncochard/jspm-bug-01.git
    cd jspm-bug-01

Publish it to your local NPM repo.

    npm publish

# Consume this package in a new project #

    cd ..
    mkdir my-test-project
    cd my-test-project
    npm init
    jspm init
    jspm install npm:jspm-bug-01

**At this point you should be able to see the following error...**

    err  Error looking up github:github:systemjs/plugin-css@^0.1.15.

# Additional information #

* I'm using jspm version 0.15.7
* I'm using npm  version 3.2.2
