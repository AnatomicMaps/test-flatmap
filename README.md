# test-flatmap

This is a simple flatmap for testing purposes. Included are features used by the `keast-5` ApiNATOMY neuron population, including spinal cord segments containing lamina VII gray matter. Because `neuronConnectivity` in the manifest specifies all of the `keast-bladder` model, parts of `keast-4`, `keast-9`, `keast-10`, and `keast-20` also appear.

## Map generation

```
$ python runmaker.py --output ../map-server/flatmaps  --source ../map-sources/test-flatmap/manifest.json --background-tiles --ignore-git
INFO: Generated map: id: test-flatmap, uuid: None, models: NCBITaxon:1, output: ../map-server/flatmaps/test-flatmap
```

## Upload to SPARC Ubuntu system

IP address is 34.209.7.109

```
$ cd ../map-server/flatmaps
$ tar czf test-flatmap.tar.gz test-flatmap/
$ scp test-flatmap.tar.gz sparc:
```

## Extract archive

```
$ ssh sparc
$ cd services/devel-flatmap-server/flatmaps/
$ tar xzf ~/test-flatmap.tar.gz
$ rm ~/test-flatmap.tar.gz
$ exit
```
