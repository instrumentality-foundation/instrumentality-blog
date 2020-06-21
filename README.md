# Instrumentality Blog

This repository hosts the code for the Instrumentality blog and includes all the logic, styling and structure. The whole project is a [Svelte](https://svelte.dev/) 
aplication and rellies on rollup to build everything up. Most styling is done through [UIkit](https://getuikit.com/).

How to build the project follows:

## Installing dependencies

[Node.js](https://nodejs.org/en/) 12 was used when creating the blog.

Use a javascript package manager of your choice, either `yarn` or `npm` are fine. This guide will focus on `yarn` since this was the used tool when creating the project.

To install dependencies, in the root of the project, open a terminal and run `yarn install`.

## Runing the development server

To run the development server just run `yarn dev`.

## Building for deployment

In order to deploy the app to a server you need a minified and optimized version of the code so you should run `yarn build`. All the compiled code will be put in
the `/docs` folder. If you want to serve that folder locally or on a server run the command `yarn start`.
