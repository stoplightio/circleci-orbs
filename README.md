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
