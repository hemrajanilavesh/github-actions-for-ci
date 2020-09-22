# Using Github Actions for CI-CD Workflow

[![Node.js CI](https://github.com/hemrajanilavesh/github-actions-for-ci-cd/workflows/Node.js%20CI/badge.svg?branch=master&event=push)](https://github.com/hemrajanilavesh/github-actions-for-ci-cd/actions?query=branch%3Amaster+is%3Acompleted)
[![codecov](https://codecov.io/gh/hemrajanilavesh/github-actions-for-ci-cd/branch/master/graph/badge.svg)](https://codecov.io/gh/hemrajanilavesh/github-actions-for-ci-cd)
[![Known Vulnerabilities](https://snyk.io/test/github/hemrajanilavesh/github-actions-for-ci-cd/badge.svg?targetFile=package.json)](https://snyk.io/test/github/hemrajanilavesh/github-actions-for-ci-cd?targetFile=package.json)

The repository contains a working example of Continuous Integration & Continuous Delivery of a Tic Tac Toe Web App.
 
## Workflow Contents

##### Workflow yaml can be found [here](https://github.com/hemrajanilavesh/github-actions-for-ci-cd/blob/master/.github/workflows/node.js.yml)

It has the following Jobs:

1. Build
    * [x] Install Node Dependencies
    * [x] Build webpack
    * [x] Upload webpack artifact
2. Test
    * [x] Run tests against different platforms using below matrix strategy:
        <table>
        <thead>
        <tr>
        <th>OS</th>
        <th>Node version 1</th>
        <th>Node version 2</th>
        </tr>
        </thead>
        <tbody>
        <tr><td>ubuntu-latest</td><td>12.x</td><td>14.x</td></tr>
        <tr><td>windows-2016</td><td>12.x</td><td>14.x</td></tr>
        </tbody>
        </table>
3. Coverage
    * [x] Run Tests and Generate Code Coverage Report
    * [x] Publish report to https://codecov.io/
4. Security
    * [x] Run Snyk to check for vulnerabilities
5. Build-and-Push-Docker-Image   
    * [x] Download Webpack Artifact
    * [x] Build Docker Image and include webpack
    * [x] Publish Docker Image to Github Registry
       

##### Published Image can be found [here](https://github.com/hemrajanilavesh/github-actions-for-ci-cd/packages/404800)

## Actions Used in the Workflow

- [Checkout](https://github.com/actions/checkout)
- [Upload Artifact](https://github.com/actions/upload-artifact)
- [Download Artifact](https://github.com/actions/download-artifact)
- [Setup Node](https://github.com/actions/setup-node)
- [Codecov](https://github.com/marketplace/actions/codecov)
- [Snyk](https://github.com/snyk/actions/tree/master/node)
- [Docker Build Push](https://github.com/docker/build-push-action)

## References

[Building and Testing Node.js](https://docs.github.com/en/actions/guides/building-and-testing-nodejs)

[Github Learning Lab: Continuous Integration](https://lab.github.com/githubtraining/github-actions:-continuous-integration)

[Github Learning Lab: Publish to GitHub Packages](https://lab.github.com/githubtraining/github-actions:-publish-to-github-packages)
