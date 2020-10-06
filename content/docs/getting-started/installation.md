---
title: "Installation"
weight : 1010
menu:
  docs:
    parent: getting_started
---

To get up and running with <b>zenoh</b> you will have to install the router and then get hold of the API you would like to use to write your applications. 

## Installing zenoh's router
At the present stage zenoh's router is supported only on Linux and MacOS.
However, for other platforms, you can use the [Docker image](../quick-test#run-zenoh-in-docker).

Below are the detailed information on how to install the binaries directly on supported platforms (i.e. without Docker).

### MacOS
The first step is to tap our brew package repository:

```bash
$ brew tap atolab/homebrew-atobin
```    

And simply install zenoh as follows:

```bash
$ brew install zenoh
```

Then you can start the zenoh router with this command:
```bash
$ zenohd -v
```

### Ubuntu (20.04)
**TODO**


## Testing Your Installation
To test the installation, try to see the zenoh man page by executing the following command:

```bash
$ zenohd --help
```
You should see the following output on your console:

```text
The zenoh router 

USAGE:
    zenohd [FLAGS] [OPTIONS]

FLAGS:
    -h, --help               Prints help information
        --no-backend         If true, no backend (and thus no storage) are created at startup. If false (default) the
                             Memory backend it present at startup.
        --no-timestamp       By default zenohd adds a HLC-generated Timestamp to each routed Data if there isn't already
                             one. This option desactivates this feature.
        --plugin-nolookup    When set, zenohd will not look for plugins nor try to load any plugin except the ones
                             explicitely configured with -P or --plugin.
    -V, --version            Prints version information

OPTIONS:
        --http-port <http-port>         The listening http port [default: 8000]
    -i, --id <hex_string>...            The identifier (as an hexadecimal string - e.g.: 0A0B23...) that zenohd must
                                        use. WARNING: this identifier must be unique in the system! If not set, a random
                                        UUIDv4 will be used.
    -l, --listener <LOCATOR>...         A locator on which this router will listen for incoming sessions. Repeat this
                                        option to open several listeners. [default: tcp/0.0.0.0:7447]
        --mem-storage <PATH_EXPR>...    A memory storage to be created at start-up. Repeat this option to created
                                        several storages
    -e, --peer <LOCATOR>...             A peer locator this router will try to connect to. Repeat this option to connect
                                        to several peers.
    -P, --plugin <PATH_TO_PLUGIN>...    A plugin that must be loaded. Repeat this option to load several plugins.
[...]
```

## Installing client library
To develop your application zenoh application, you need to install a zenoh client library.
Depending your programmation language, choose one of the following API and refer to the installation and usage instructions in here:

- [Python API](https://github.com/eclipse-zenoh/zenoh-python)
- [C API (only zenoh-net API)](https://github.com/eclipse-zenoh/zenoh-c)
