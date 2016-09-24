# Psinfo
Psinfo is a Volatility plugin which collects the process related information from the VAD (Virtual Address Descriptor) and PEB (Process Enivornment Block) and displays the collected information and suspicious memory regions for all the processes running on the system. This plugin should allow a security analyst to get the process related information and spot any process anamoly without having to run multiple plugins.

Full details can be found in the link:
https://cysinfo.com/detecting-malicious-processes-psinfo-volatility-plugin/

### Running the Plugin

Copy the plugin to volatility/plugins directory

Run the plugin against memory image as shown below

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 psinfo
```

### Other Options

To filter on a specic process id use -p option

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 psinfo -p 1820
```

To filter on multiple process ids use -p followed by comma seperated process ids

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 psinfo -p 1820,868
```

To dump the suspicious memory regions use -D followed by directory name

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 psinfo -p 1820 -D dump/
```

To redirect the output to file use --output-file option

```sh
$ python vol.py -f infected.vmem --profile=Win7SP0x86 psinfo --output-file=output.txt
```
