# BOSH release for avalanche

This BOSH release and deployment manifest deploy an instance of avalanche.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
git clone https://github.com/kfkonrad/avalanche-boshrelease.git
bosh deploy avalanche-boshrelease/manifests/avalanche.yml -d avalanche
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `avalanche-boshrelease` are released the `manifests/avalanche.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
cd avalanche-boshrelease
git pull
bosh deploy manifests/avalanche.yml -d avalanche
```
