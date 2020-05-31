# Proxy server with certificates generator

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)

## General info
In *conf.d* directory are examples of configuration domains. All files must be end with *.conf*
In *letsencrypt* are whole data about Letsencrypt certificates. In subdirectory *archive* are certificates.
In *nginx.conf* is general nginx configuration
*./build/renewcerts* is rensponsible for every day all certificates renew 
*./build/renewcerts*

## Technologies
* Nginx
* Let's Encrypt
* docker-compose

## Setup
New domains are created based on example files. 

#### Example command which create certificate
> docker exec proxy_certbot certbot --nginx --redirect --non-interactive --agree-tos -d SUBDOMAIN.MY.DOMAIN -d www.SUBDOMAIN.MY.DOMAIN

#### Generally:
> docker exec CONTAINER_NAME certbot --nginx --redirect --non-interactive --agree-tos -d DOMENA -d www.DOMENA

#### Test of nginx configuration:
> docker exec proxy_certbot nginx -t

#### Restart container:
> docker restart proxy_certbot
