# podman-nginx

Installs a `nginx` podman container as system service.

The configuration template is similar to a typical openSUSE installation with virtual hosts being present in `vhosts.d`.
The configuration location by default is `/etc/nginx`, but can be configured.

## Requirements

Basic ansible, no further dependencies or requirements are needed.

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `nginx_container_image` | docker.io/library/nginx:stable | Container image |
| `nginx_service_name` |  nginx | Systemd service name |
| `nginx_container_name` | nginx | Name of the podman container |
| `nginx_auto_pull` | true | Pull the container before creating it in the systemd unit |
| `nginx_auto_update` | true | Apply the auto-update label for podman |
| `nginx_mem_limit` | 64M | Memory limit for nginx |
| `nginx_health_check` | true | If true, add a --healthcheck to the systemd service - we use `curl` on the container localhost |
| `nginx_default_conf` | true | If true, we install the `default.conf` in `vhosts.d` |
| `nginx_data_dir` | /srv/www | Default location for www content to be served |
| `nginx_conf_dir` | /etc/nginx | Configuration directory for nginx |
| `nginx_log_directory` | | If defined, mount this directory for storing log files |
| `nginx_network` | host | podman network to be used |

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: podman-nginx

## License

[`AGPL-3.0-or-later`](LICENSE)

## Author Information

phoenix
