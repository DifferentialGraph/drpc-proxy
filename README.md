# DRPC Proxy
Repository containing the setup for a [DRPC](https://drpc.org/docs/providers/setup) proxy.
<p align="center">
  <img width="40%" src="media/drpc-install-prompt.png">
  <img width="40%" src="media/drpc-monitor.png">
</p> 

## Preliminaries
This particular setup uses an NGINX base reverse proxy. You can find it [here](https://github.com/DifferentialGraph/reverse-proxy).

## Installation
In order to setup the DRPC proxy first create a copy of the `.env` file named `.env.user`. Fill it with the options that suits your framework. Before proceeding with the installation you have to create the `config.yaml` under the folder `config`. You can start from the template `config-template.yaml` you find under the same folder.

From within the drpc-proxy folder run:
```sh
./install
```
to install the DRPC proxy. An interactive prompt will guide you through the various steps.

## Monitor & Manage
In order to monitor the DRPC proxy type
```sh
drpc-monitor
```
This will create a tmux session with the following windows:
- **drpc-proxy-log**: log of the drpc-proxy container. Shows all the operation performed by it.
- **drpc-proxy-cli**: in this window you can operate from within the drpc-proxy container.

In order to start, stop and restart the DRPC proxy use `drpc-start`, `drpc-stop` and `drpc-restart`.

## Options
- `PROVIDER_NAME`: the name of your company.
- `PROVIDER_HOST`: domain linked to your provider.
- `PROVIDER_CHAINS`: blockchains supported by your provider.

## Useful links
- [Upstream config](https://github.com/emeraldpay/dshackle/blob/21cb0f009c7acfd47431a63f75b7b56751b3ad6c/docs/04-upstream-config.adoc#L251)
- [Erigon methods](https://github.com/erigontech/erigon/blob/6f831548e94950838d4f81b0acafd572d55fb9d1/cmd/rpcdaemon/README.md)
