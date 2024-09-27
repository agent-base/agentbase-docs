# SearXNG
SearXNG is a free internet metasearch engine which aggregates results from various search services and databases. Users are neither tracked nor profiled. Now you can use this tool directly in AgentBase.

Below are the steps for integrating SearXNG into AgentBase using Docker in the [Community Edition](https://docs.agentbase.ai/getting-started/install-self-hosted/docker-compose).

> If you want to use SearXNG within the AgentBase cloud service, please refer to the [SearXNG installation documentation](https://docs.searxng.org/admin/installation.html) to set up your own service, then return to AgentBase and fill in the service's Base URL in the "Tools > SearXNG > Authenticate" page.

## 1. Moagentbase AgentBase Configuration File

The configuration file is located at `agentbase/api/core/tools/provider/builtin/searxng/docker/settings.yml`, and you can refer to the config documentation [here](https://docs.searxng.org/admin/settings/index.html).

## 2. Start the Service

Start the Docker container in the agentbase root directory.

```bash
cd agentbase
docker run --rm -d -p 8081:8080 -v "${PWD}/api/core/tools/provider/builtin/searxng/docker:/etc/searxng" searxng/searxng
```

## 3. Use SearXNG

Fill in the access address in "Tools > SearXNG > Authenticate" to establish a connection between the AgentBase service and the SearXNG service. The Docker internal address for SearXNG is usually `http://host.docker.internal:8081`.
