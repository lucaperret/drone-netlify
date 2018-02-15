# Drone-netlify

![Netlify logo](netlify.png?raw=true "netlify.com")

[![Docker Pulls](https://img.shields.io/docker/pulls/lucap/drone-netlify.svg)](https://hub.docker.com/r/lucap/drone-netlify/)
[![Image](https://images.microbadger.com/badges/image/lucap/drone-netlify.svg)](https://microbadger.com/images/lucap/drone-netlify "Get your own image badge on microbadger.com")
[![GitHub release](https://img.shields.io/github/release/lucaperret/drone-netlify.svg)](https://github.com/lucaperret/drone-netlify/releases/latest)

Deploying to [Netlify](https://netlify.com) with [Drone](https://drone.io) CI.

Use case examples:

- Automatically create staging deployments for pull requests
- Automatically deploy and alias upon pushes to master

## Usage

For the usage information and a listing of the available options please take a look at [the docs](DOCS.md).

There are two ways to deploy.

### From docker

Deploy the working directory to Netlify.

```bash
docker run --rm \
  -e PLUGIN_TOKEN=xxxxx \
  -e PLUGIN_SITE_ID=xxxxxxx-xxxx-xxx-xxxxxxxx \
  -e PLUGIN_SITE_NAME=netlify-subdomain
  -v $(pwd):$(pwd) \
  -w $(pwd) \
  lucap/drone-netlify
```

### From Drone CI

```yaml
pipeline:
  netlify:
    image: lucap/drone-netlify
    token: xxxxx
    site_id: xxxxxxx-xxxx-xxx-xxxxxxxx
    site_name: netlify-subdomain
```
