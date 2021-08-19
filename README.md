# dnsmasq-exporter

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/dnsmasq-exporter/status.svg)](https://drone.osshelp.ru/ansible/dnsmasq-exporter)

Role for [dnsmasq_exporer](https://github.com/google/dnsmasq_exporter) installation and configuration.

## Usage (example)

```yaml
    - role: dnsmasq-exporter
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `dnsmasq-exporter_setup` | `full` | Setup mode. See [OSSHelp KB article](https://oss.help/kb4895) |
| `dnsmasq_exporter_version` | `0.2.0` | Which version to install (taken from our MinIO storage) |
| `dnsmasq_exporter_params.address` | `localhost:53` | Address dnsmasq is listening on. |
| `dnsmasq_exporter_params.leases_path` | `/var/lib/lxd/networks/lxdbr0/dnsmasq.leases` | Absolute path to dnsmasq leases file. |
| `dnsmasq_exporter_params.listen` | `0.0.0.0:9153` | Address for exporter to listen on. |

### Misc

Usually there is no need in changing these.

| Param | Default | Description |
| -------- | -------- | -------- |
| `dnsmasq_exporter_config_file` | `dnsmasq_exporter.cfg` | Name that will be given to main configuration file. |
| `dnsmasq_exporter_user_name` | `dnsmasq_exporter` | Name of user to be created for exporter. |
| `dnsmasq_exporter_service_name` | `dnsmasq_exporter` | Name of systemd service to be created for exporter. |
| `dnsmasq_exporter_systemd_unit` | `/etc/systemd/system/{{dnsmasq_exporter_service_name}}.service` | Absolute path to systemd unit. |
| `dnsmasq_exporter_dirs.binary_dir` | `/usr/local/bin` | Absolute path to directory where exporter binary will be placed. |
| `dnsmasq_exporter_dirs.config_dir` | `/usr/local/etc/dnsmasq_exporter` | Absolute path to to directory where exporter configuration file will be placed. |

## FAQ

None, so far.

## Useful links

- [Official documentation](https://github.com/google/dnsmasq_exporter/blob/master/README.md)

## TODO

- Add focal support.
- Change pinned default values in cfg. templates to variables.

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
