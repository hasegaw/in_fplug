# in_fplug

in_fplug is data source for [Fluent bit](http://fluentbit.io) that works on Linux with Bluetooth radio modules. Reads power consumption from Fujitsu BSC [F-PLUG](http://www.bsc.fujitsu.com/services/f-plug/) and writes JSON logs.

## Prequesties

 - F-PLUG must be paired with the host.
 - Depends on [pyfplug](https://github.com/hasegaw/pyfplug/), pyserial.

## Running

```bash
python -u ./in_fplug /dev/rfcomm? | ~hasegaw/work/fluent-bit.upstream/build/bin/fluent-bit -i stdin -o stdout
```

### Output example

```bash
# python -u ./in_fplug /dev/rfcomm?
[1441138038, {"name": "rfcomm1", "power": 148.0}]
[1441138038, {"name": "rfcomm2", "power": 0}]
[1441138038, {"name": "rfcomm3", "power": 0}]
[1441138038, {"name": "rfcomm4", "power": 0.3}]
[1441138039, {"name": "rfcomm5", "power": 168.0}]
[1441138068, {"name": "rfcomm1", "power": 150.0}]
[1441138068, {"name": "rfcomm2", "power": 0}]
[1441138069, {"name": "rfcomm3", "power": 0}]
[1441138069, {"name": "rfcomm4", "power": 0.4}]
[1441138069, {"name": "rfcomm5", "power": 166.0}]
```
