# Container Dynamics

The container dynamics bundle illustrates an ad-hoc Juju/Docker based PAAS.

The juju infrastructure deployed in this bundle contains everything you need to
deploy docker containers to production. The containers deployed with a mapped
port are then registered in Consul, and provided a reverse proxy. This makes it
trivial to deploy entire webapp stacks and get a web-enabled endpoint, reverse
proxied through nginx pointing back at your webhead container.


## Usage

This bundle is formatted according to the juju-bundles 3.0 pec. This is
deployable with juju-deployer, and assumes you have the entirety of all the
repositories cloned locally.

#### Setup your Juju Repository

    mkdir -p $HOME/charms/trusty $HOME/charms/precise
    export JUJU_REPOSITORY=$HOME/charms

#### clone the repositories

    cd $JUJU_REPOSITORY
    git clone chuckbutler/docker-charm trusty/docker
    git clone chuckbutler/docker-compose-charm trusty/docker-compose
    git clone mbruzek/nginx-proxy-charm trusty/nginx-proxy
    git clone mbruzek/consul trusty/consul

#### execute deployer

    juju-deployer -c bundles.yaml


## Scale

## Caveats

## Upstream Charms

## Contact

