# syntax=docker/dockerfile:1
FROM caddy:2.11.6-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/WeidiDeng/caddy-cloudflare-ip \
    --with github.com/mholt/caddy-dynamicdns \
    --with github.com/caddy-dns/duckdns \
    --with github.com/caddy-dns/desec \
    --with github.com/mholt/caddy-ratelimit \
    --with github.com/greenpau/caddy-security \
    --with github.com/porech/caddy-maxmind-geolocation \
    --with github.com/mholt/caddy-l4

FROM caddy:2.11.7

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
