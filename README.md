# quick-local-https

Really small and quick https server for serving static html. Great for POC's prototyping or testing web APIs that require HTTPS

## Usage

- install docker
- clone this repo
- run `docker-compose up -d`
- open your browser and go to [https://0.0.0.0](https://0.0.0.0)
- you have to set the page as exception, since the cert is self-signed
- you'll see the `index.html` in this repo over https

## Configuration

See the `docker-compose.yml` to set port, paths, etc if necessary.

## Recreate SSL cert

The cert is generated for 365 days, you can create a new one anytime using the following command:

```bash
cd nginx-https
rm nginx.crt nginx.key
openssl req -newkey rsa:2048 -nodes -keyout nginx.key -x509 -days 365 -out nginx.crt

```