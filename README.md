# ansibleの使い方ガイド

## Setup

### ansibleのインストール

```bash
apt install ansible -y
pip install ansible
apt-get install sshpass
```

### known_hostsエラー回避

/etc/ansible/ansible.cfgの[ssh_connection]のブロックに以下の設定を記載する。

```bash
ssh_args = -o ControlMaster=auto -o ControlPersist=60s -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null
```

## 18.04 -> 20.04の自動更新

```bash
ansible-playbook update.yml -i inventory.ini
```

## shutdown

```bash
ansible-playbook shutdown.yml -i inventory.ini
```

## dockerコンテナ作成

```bash
ansible-playbook docker.yml -i inventory.ini
```

## GPUのuser追加

```bash
ansible-playbook user.yml -i inventory.ini
```

## GPUのホスト名の変更
```bash
ansible-playbook hostname.yml -i inventory.ini
```

## ip確認

```bash
ansible-playbook ip.yml -i inventory.ini
```

## Docker接続確認

```bash
ansible-playbook docker.yml -i dockers.ini
```