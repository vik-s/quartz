---
title: Making sure that Traefik can auto-renew a certificate
created: 2023-11-07 19:10
status: permanent
tags:
  - homelab
  - traefik
---
Make sure that the IP address being auto-renewed by Traefik is white-listed in Namecheap API.

Go to Profile --> Tools --> Namecheap API access and click on Manage.
Add the whitelisted IP address.

If pointing to a VPS entry, make sure that address is whitelisted as well.

If the home WAN IP changes, then you need to manually go update this.