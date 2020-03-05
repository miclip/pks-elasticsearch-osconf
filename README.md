git clone https://github.com/miclip/pks-elasticsearch-osconf && cd pks-elasticsearch-osconf
git submodule init ; git submodule update
cd os-conf-release
bosh create-release --force
bosh upload-release ./dev_releases/os-conf/os-conf-21.0.0+dev.1.yml

```
4. Configure the addon from this repo
```
cd ..
bosh -n update-config --name=pks-elasticsearch-osconf --type=runtime ./addon.yml
```
