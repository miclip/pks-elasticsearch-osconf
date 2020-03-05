# PKS ElasticSearch Configuration

This will enable the sysctl configuration for `vm.max_map_count=262144` that [ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html) requires on PKS worker nodes without having to enable privileged containers.  

```
git clone https://github.com/miclip/pks-elasticsearch-osconf && cd pks-elasticsearch-osconf
git submodule init ; git submodule update
cd os-conf-release
bosh create-release --force
bosh upload-release ./dev_releases/os-conf/os-conf-21.0.0+dev.1.yml

```
Configure the addon from this repo
```
cd ..
bosh -n update-config --name=pks-elasticsearch-osconf --type=runtime ./addon.yml
```
