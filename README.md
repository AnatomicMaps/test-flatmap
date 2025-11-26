# test-flatmap

This is a simple flatmap for testing purposes. The features are included to demonstrate three key functions:
- Example for keast-5:
  Provides a clean example of the keast-5 ApiNATOMY neuron population—from the pelvic ganglion, through the pelvic splanchnic nerve, to spinal cord segments containing lamina VII. Other populations (e.g., keast-6) appear only because they partially share the same features.
- Nerve cuff rendering differences:
  Includes nerve cuffs such as the vagus nerve, the splanchnic nerve, and the external branch of the inferior laryngeal nerve. Their sizes intentionally differ based on how many neuron populations pass through them.
  The vagus nerve is the largest example, reflecting traffic from ‘bolew-unbranched’ and the mmset4-type neuron population.
- Proxy usage demonstration:
  Shows how proxies work using right ovary → ovary. Here, mmset4-5 and femrep 94 target the right ovary proxy, while femrep 40 targets the general ovary.

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
