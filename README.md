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
				"email": "YOUR_LUADNS_EMAIL",
				"api_key": "YOUR_LUADNS_API_KEY"
			}
		}
	}
}
```

or with the Caddyfile:

```Caddyfile
# globally
{
	acme_dns luadns {
		api_key <your_luadns_email>
		api_key <your_luadns_api_key>
	}
}
```

```Caddyfile
# one site
tls {
	dns luadns {
		api_key <your_luadns_email>
		api_key <your_luadns_api_key>
	}
}
```
