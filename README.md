# srsRAN snap

srsRAN is a 4G/5G software radio suite developed by [SRS](https://www.srs.io/).

See the [srsRAN project pages](https://www.srsran.com/) for information, guides and project news.

The srsRAN suite includes:
- srsUE - a full-stack SDR 4G/5G UE application
- srsENB - a full-stack SDR 4G/5G e(g)NodeB application
- srsEPC - a light-weight 4G core network implementation with MME, HSS and S/P-GW

For application features, build instructions and user guides see the [srsRAN documentation](https://docs.srsran.com/en/latest/).

## Usage

### Install

```bash
snap install srsran
```

### Run the EPC

```bash
srsepc
```

### Run the eNodeB

```bash
srsenb --rf.device_name=zmq --rf.device_args="fail_on_disconnect=true,tx_port=tcp://*:2000,rx_port=tcp://localhost:2001,id=enb,base_srate=23.04e6"
```

### Run the UE

```bash
srsue --rf.device_name=zmq --rf.device_args="tx_port=tcp://*:2001,rx_port=tcp://localhost:2000,id=ue,base_srate=23.04e6" --gw.netns=ue1
```
