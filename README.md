# Pangolin VPS Stack

Production-ready VPS stack for running Pangolin with networking, security, monitoring, and observability.

---

## Description

This repository provides a full production-grade VPS stack to run Pangolin.

It includes:

- networking layer  
- reverse proxy  
- security engine  
- monitoring & logging stack  

Designed for secure, scalable self-hosting.

---

## Architecture Overview
Internet → Traefik (Routing + HTTPS) → Pangolin (Core API) → Services / Middleware
Internet → Gerbil (Ingress + WireGuard) → Pangolin (Core API) → Services / Middleware

Supporting services:

- CrowdSec → analyzes logs & blocks attacks  
- Prometheus → collects metrics  
- Grafana → visualization  
- Traefik Dashboard → logs & analytics  

---

## Environment Variables

Example `.env`:

- CF_DNS_API_TOKEN=your_cloudflare_token
- AGENT_API_TOKEN=generate_agent_token
- GEOIPUPDATE_ACCOUNT_ID=your_maxmind_id
- MAXMIND_LICENSE_KEY=your_maxmind_key
- MOBILE_API_KEY=generate_mobile_key

---

## Security Features

- CrowdSec real-time protection  
- Traefik HTTPS enforcement  
- GeoIP tracking and blocking
- Log-based intrusion detection  

---

## Observability

- Prometheus → metrics  
- Grafana → dashboards  
- Traefik Log Dashboard → logs  
- GeoIP enrichment  

---

## Notes

Exposed ports:

- 80 / 443 → public traffic  
- 51820 → WireGuard for Newt connections  
- 21820 → WireGuard for client connections  

Make sure DNS and firewall are properly configured.

The Pangoling documentation is great, consult it to make a clean install https://docs.pangolin.net/about/how-pangolin-works
