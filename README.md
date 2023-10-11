# test-flatmap

A repository to store test flatmaps.

This is a simple flatmap for testing purposes. Included here are the connectivity in the `keast-5` which includes organs such as `the spinal cord segment` where `lamina VII of gray matter of spinal` is located. Then, because neuronConnectivity is set to `keast-bladder`, additional parts of `keast-4`, `keast-9`, `keast-10`, and `keast-20` appear.

## Map generation

```
$ python runmaker.py --output ../published/flatmaps  --source ../published/sources/test-flatmap/manifest.json --background-tiles
INFO: Generated map: id: test-flatmap, uuid: 381999f7-fdec-58ca-a522-62e0c0c64cfe, models: NCBITaxon:1, output: ../published/flatmaps/381999f7-fdec-58ca-a522-62e0c0c64cfe
```

## Upload to SPARC Ubuntu system

IP address is 34.209.7.109

```
$ cd ../published/flatmaps
$ tar czf test-flatmap.tar.gz knowledgebase.db 381999f7-fdec-58ca-a522-62e0c0c64cfe/
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
