LuaDNS module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with LuaDNS.

## Caddy module name

```
dns.providers.luadns
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "luadns",
				"email": "YOUR_PROVIDER_EMAIL",
				"api_key": "YOUR_PROVIDER_API_KEY"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns luadns {
		api_key <your_provider_email>
		api_key <your_provider_api_key>
	}
}
```

```
# one site
tls {
	dns luadns {
		api_key <your_provider_email>
		api_key <your_provider_api_key>
	}
}
```
