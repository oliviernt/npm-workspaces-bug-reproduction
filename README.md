# NPM Workspaces Docker Bug Reproduction

I'm reproducing a bug I'm encountering where npm 7 workspaces don't work the same when run in the official docker node:15 container as when running it locally.

Using this project I get two different outputs when running `npm run hello --workspaces` locally or in a docker container.

# Local

```
$ npm run hello --workspaces

> workspace-a@1.0.0 hello
> echo "Hello from workspace-a"

Hello from workspace-a
```

# Docker

```
$ docker run -it -v "$PWD":/opt/workdir -w /opt/workdir node:15 npm run hello --workspaces

> npm-workspaces-bug-reproduction@1.0.0 hello
> echo "Hello from npm-workspaces-bug-reproduction"

Hello from npm-workspaces-bug-reproduction
```
