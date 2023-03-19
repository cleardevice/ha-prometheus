# Ansible role with docker stack with high available Prometheus + Alertmanager + Thanos

## Prerequisites
2 VMs with docker installed. Also you should have ansible installed on your PC.
You should copy your ssh key to these servers under `root` user.
It can be done with `ssh-copy-id` command.

## Installation
For deploying Grafana, Prometheus, Alertmanager and Thanos in HA mode do these actions:
1. Clone repo
```
git clone https://github.com/digitalstudium/ha-prometheus.git
```
2. Change `hosts.ini` file. You should have exactly two hosts under `[servers]` group and asbitrary number of hosts in `exporters` group.
3. Add `tg_bot_token` and `tg_chat_id` variables if you want to get alerts to Telegram group.
4. Deploy monitoring
```bash
ansible-playbook playbook.yml -i hosts.ini --user root
```

That's it!

After 5 minutes sor so you'll get Grafana installed on both hosts of `servers` group.
Default user/password admin/admin