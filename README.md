
# pivxfoundation/docker-electrumx
[![Build Status](https://travis-ci.org/pivxfoundation/docker-electrumx.svg?branch=master)](https://travis-ci.org/pivxfoundation/docker-electrumx)
[![Image Layers](https://images.microbadger.com/badges/image/pivxfoundation/docker-electrumx.svg)](https://microbadger.com/images/pivxfoundation/docker-electrumx)
[![Docker Pulls](https://img.shields.io/docker/pulls/pivxfoundation/docker-electrumx.svg)](https://hub.docker.com/r/pivxfoundation/docker-electrumx/)

> Run an Electrum server with one command

An easily configurable Docker image for running an Electrum server. Configured to add support for running with PIVX daemon.

## Usage

```
docker run  -v "/home/username/electrumx:/data" \
    -e DAEMON_URL=http://localuser:localpassword@192.168.0.100:51473 \
    -e COIN=PIVX \
    -e RPC_HOST=0.0.0.0 \
    -p 8000:8000 \
    -p 5001:50001 \
    pivxfoundation/docker-electrumx
```

If there's an SSL certificate/key (`electrumx.crt`/`electrumx.key`) in the `/data` volume it'll be used. If not, one will be generated for you.

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst

### TCP Port

By default only the SSL port is exposed. You can expose the unencrypted TCP port with `-p 50001:50001`, although this is strongly discouraged.


## License

MIT

## Copyright

Copyright © Luke Childs

Copyright © 2019 PIVX Foundation
