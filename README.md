# Stoplight CircleCI Orbs

For more information on orbs, check out https://circleci.com/docs/2.0/orb-intro/

## Orbs

### stoplight/cli

Add the following environment variables to your CircleCI project settings:

- `SL_ANALYZE_TOKEN`: your project's private analyze token
- `SL_API_HOST`: your Stoplight API host (ex. `https://api.stoplight.io`)

```yml
version: 2.1

orbs:
  stoplight: stoplight/cli@0.0.1

workflows:
  stoplight-analyze:
    jobs:
      - stoplight/analyze
```

### stoplight/build-commands

Add the following environment variables to your CircleCI project settings:

- `NPM_TOKEN`: the authToken from your .npmrc (copy from another project)
- `BOT_ACCESS_TOKEN`: the API token of the stoplight-bot Github user (copy from another project)

```yml
version: 2.1

orbs:
  stoplight: stoplight/build-commands@0.0.1

jobs:
  build:
    docker:
      - image: circleci/node:10-stretch
    steps:
      - checkout
      - setup_remote_docker:
          docker_layer_caching: true
      - stoplight/clone_build_scripts
      - stoplight/set_npm_token
```
