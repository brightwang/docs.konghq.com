---
name: Kong Upstream HMAC
publisher: brightwang

categories:
  - security

type: plugin

desc: This plugin will add HMAC Signature authentication into the HTTP Header Authorization of proxied requests through the Kong gateway. The purpose of this, is to provide means of Authentication, Authorization and Non-Repudiation to API providers (APIs for which Kong is a gateway).

support_url: https://github.com/brightwang/kong-upstream-hmac/issues

source_url: https://github.com/brightwang/kong-upstream-hmac

license_type: Apache-2.0

kong_version_compatibility:
  community_edition:
    compatible:
      - 1.0.x

params:
  name: kong-upstream-hmac
  api_id: true
  service_id: true
  consumer_id: false
  route_id: true

extra: |
  Installing this plugin globally will ensure security across all proxies for service providers who implement the HMAC validation correctly.
###############################################################################
# END YAML DATA
# Beneath the next --- use Markdown (redcarpet flavor) and HTML formatting only.
#
# The remainder of this file is for free-form description, instruction, and
# reference matter.
# Your headers must be Level 3 or 4 (parsing to h3 or h4 tags in HTML).
# This is represented by ### or #### notation preceding the header text.
###############################################################################
# BEGIN MARKDOWN CONTENT
---

### Installation

Recommended:

```bash
$ luarocks install kong-upstream-hmac
```

Other:

```bash
$ git clone https://github.com/brightwang/kong-upstream-hmac.git /path/to/kong/plugins/kong-upstream-hmac
$ cd /path/to/kong/plugins/kong-upstream-hmac
$ luarocks make *.rockspec
```

### Configuration

```bash
curl -X POST http://kong:8001/routes/{route-id}/plugins -d "name=kong-upstream-hmac" -d "config.token=token" -d "config.secret=secret"
```

### Maintainers

[brightwang](https://github.com/brightwang)  

Feel free to [open issues](https://github.com/brightwang/kong-upstream-hmac/issues)