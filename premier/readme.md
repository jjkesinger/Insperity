# premier readme

# Services

## Premier.Content
    * Endpoint that exposes authoring content
    * Entrypoint: Premier.Content.Api

## Premier.Auth
    * Authorization and Identity Server
    * Entrypoint: Premier.Auth.Identity

# Gateways

## Premier.Gateway
    * Back-end for front-end aggregator for premier
    * Premier.Gateway.Api

## Web Gateway (web-gateway)
    * Gateway for routing web traffic to microservices
    * Entrypoint: Envoy container image- see config