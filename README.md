# Universal Relay Boilerplate
Boilerplate + examples for React Native (iOS, Android), React (isomorphic, Material-UI), Relay, GraphQL, JWT, Node.js, Apache Cassandra

[![StackShare](http://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](http://stackshare.io/code-foundries/code-foundries)

[Project Overview](http://codefoundries.com/products/UniversalRelayBoilerplate.html)

[Project Details](http://codefoundries.com/developer/rebar/)

[Live demo](http://universal-relay-boilerplate.herokuapp.com/)


# Technologies used in Rebar and Universal Relay Boilerplate

For the most up to date list of technologies used please go to [CodeFoundries.com](http://codefoundries.com/developer/rebar/technologies-used.html).

## Client side

| **Technology** | **Description**|
|----------------|----------------|
| [React JS](/stack/react-js.html)                                | Library for building Single Page Applications and apps. Often called the 'V' in the MVC model. |
| [react-router](https://github.com/reactjs/react-router)         | React Router keeps your UI in sync with the URL. It has a simple API with powerful features like lazy code loading, dynamic route matching, and location transition handling built right in. Make the URL your first thought, not an after-thought. |
| [React Native](/stack/react-native.html)                        | React Native enables you to build world-class application experiences on native platforms using a consistent developer experience based on JavaScript and React. |
| [react-native-router-flux](https://github.com/aksonov/react-native-router-flux) | Router for React Native based on new React Native Navigation API. |
| [Relay](/stack/relay.html)                                      | A Javascript framework for building data-driven react applications. |
| [Material UI](http://www.material-ui.com/)                      | Library for implementing [Material Design](https://www.google.com/design/spec/material-design/introduction.html) in React. All user interface in this kit is built exclusively with Material UI components. |
| [material-ui-country-flags](https://github.com/codefoundries/material-ui-country-flags) | Library with flag icons for Material-UI, used for the language selector. |
| [material-ui-credit-card-icons](https://github.com/codefoundries/material-ui-credit-card-icons) | Library with icons for all major credit cards, used in the Stripe payment functionality. |

## Server side

| **Technology** | **Description**|
|----------------|----------------|
| [Node.js](/stack/node-js.html)                                  | Event-driven, non-blocking I/O runtime based on JavaScript that is lightweight and efficient. |
| [Passport](http://passportjs.org/)                              | [Rebar](../../products/rebar.html) only. Simple, unobtrusive authentication for Node.js. |
| [GraphQL](/stack/graph-ql.html)                                 | A query language created by Facebook in 2012 for describing the capabilities and requirements of data models for client‐server applications. |
| [Express GraphQL](https://github.com/graphql/express-graphql)   | A Node.js express library that allows the creation of GraphQL servers. |
| [Isomorphic Relay](https://github.com/denvned/isomorphic-relay) | Adds server side rendering support to React Relay. IMRSK fully utilizes this library, while waiting for [https://github.com/facebook/relay/issues/589](https://github.com/facebook/relay/issues/589). The eventual goal is to have full isomorphism with authentication. |
| [Data Loader](https://github.com/facebook/dataloader)           | Generic utility to be used as part of your application's data fetching layer to provide a consistent API over various backends and reduce requests to those backends via batching and caching. |
| [Apache Cassandra](/stack/cassandra.html)                       | The right choice when you need scalability and high availability without compromising performance. Linear scalability and proven fault-tolerance on commodity hardware or cloud infrastructure make it the perfect platform for mission-critical data. Cassandra's support for replicating across multiple datacenters is best-in-class, providing lower latency for your users and the peace of mind of knowing that you can survive regional outages. |
| [JWT](https://jwt.io/)                                          | JSON Web Tokens is an industry standard [RFC 7519](https://tools.ietf.org/html/rfc7519) method for representing claims securely between two parties. |
| [React Helmet](https://github.com/nfl/react-helmet)             | Reusable React component will manage all of your changes to the document head with support for document title, meta, link, script, and base tags. |

## Development tools

| **Technology** | **Description**|
|----------------|----------------|
| [Flow](http://flowtype.org/)                                    | Static type checker, designed to find type errors in JavaScript programs. |
| [ESLint](http://eslint.org/)                                    | Pluggable linting utility for JavaScript and JSX. |
| [Babel](http://babeljs.io)                                      | Compiles ES6/ES7 to ES5. Allows using features from ES6 and ES7 today. Also, used by Relay. |
| [Webpack](http://webpack.github.io)                             | Bundles npm packages and the application Java Script into a single file. Includes hot reloading via [react-transform-hmr](https://www.npmjs.com/package/react-transform-hmr). Also, Webpack can bundle any required CSS. |
| [NPM Scripts](https://docs.npmjs.com/misc/scripts)              | Glues all this together in a handy automated build. |


# Development Setup

For the most up to date setup instructions please go to [CodeFoundries.com](http://codefoundries.com/developer/rebar/technologies-used.html).


## Initial Development Machine Setup

The setup is for OS X only. Prerequisites:

* **Install [Node.js](https://nodejs.org)**.  
* **Install [Git](https://git-scm.com/downloads)**.
* **Install [Apache Cassandra](/developer/cassandra/cassandra-installation-mac.html)**.
* **Make sure** that Node.js is at least version 5.0 and NPM is at least version 3.
* **In order to speed up NPM** run `npm set progress=false`. This [speeds up NPM significantly](https://twitter.com/gavinjoyce/status/691773956144119808).


## Initial Project setup on local machine

In order to set up the project locally, perform the following steps:

* **Clone from github.** `git clone https://github.com/codefoundries/UniversalRelayBoilerplate`.
* **Install node packages.** `npm install`. You will see errors like `Error: ENOENT: no such file or directory, open '.env'.`. They can be ignored.
* **Perform initial setup.** `npm run setup-local`.
* **Specify JWT_SECRET** by modifying the `.env` file. This step can be skipped if you do not care about the actual security and simply want to get the project running.
* **Start the server.** `npm run prod` or `npm run dev`.
* **The application is available at:** `http://localhost:4444`.


## Running in development mode

Two separate servers need to be started. The first one is the actual application in development mode. The second server is the webpack server which is to be run at all times for hot replace. This can be done with one command.

* Start application HTTP and Webpack server: `npm run dev`.

To open the app:

* Navigate to `http://localhost:4444`, unless you specified a different IP and/or port either manually or by using `npm run update-ip`.


## Configuring to use Cassandra

* Install and configure Cassandra following the steps in [Cassandra Installation on Mac](http://codefoundries.com/developer/cassandra/cassandra-installation-mac.html).
* Verify that the name of the database in `\.env` is the name of the database you want.
* Create the database with `npm run setup-cassandra-init`.
* Configure to use Cassandra with `npm run config-da-cassandra`.
