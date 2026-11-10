# HTTPS SSL

| File | What it does |
| --- | --- |
| `0-world_wide_web` | Prints the record type and destination of the subdomains `www`, `lb-01`, `web-01` and `web-02`, or of one given subdomain |
| `1-haproxy_ssl_termination` | HAProxy configuration that accepts HTTPS on port 443 with the certificate for `www.friendherve.tech` and balances the traffic between web-01 and web-02 |
| `2-redirect_http_to_https` | The same HAProxy configuration, which answers port 80 with a 301 redirect to HTTPS |

## Usage

```bash
./0-world_wide_web example.tech
./0-world_wide_web example.tech web-02
```

Each line of output looks like this:

```text
The subdomain www is a A record and points to 3.8.125.225
```
