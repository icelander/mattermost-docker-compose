# Mattermost Production Docker Setup

## About

This is a minimal production setup for Mattermost. It includes an Nginx reverse proxy and PostgreSQL database. By default it doesn't include TLS, but this can be added fairly easily. 

## How to Use

1. Modify `mattermost.env` to match your environment
2. Create an environment file by running `ln -s mattermost.env .env`
3. Run `docker-compose up -d`

## Adding TLS

1. Find your TLS certificate and key and put them in `./nginx/ssl`
2. Modify `./nginx/templates/default.conf.template` to uncomment lines 13-33 and correct the certificate & key filenames (if necessary)
3. Re-run `docker-compose up -d` to reload the configuration