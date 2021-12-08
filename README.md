# Install postgres

## Install the latest Python and setup a new Python virtualenv

```bash
pkcon install -y git
pkcon install -y python3-pip
pkcon install -y python3-virtualenv
virtualenv-3 ~/python
source ~/python/bin/activate
echo "source ~/python/bin/activate" | tee -a ~/.bashrc
```

## Install the latest Ansible

```bash
pip install setuptools_rust wheel
pip install --upgrade pip
pip install ansible selinux setools
```

## Install the PostgreSQL dependencies

```bash
pkcon install -y gcc
pkcon install -y make
pkcon install -y git
pkcon install -y bison
pkcon install -y flex
pkcon install -y readline-devel
pkcon install -y zlib-devel
pkcon install -y systemd-devel
pkcon install -y libxml2-devel
pkcon install -y libxslt-devel
pkcon install -y openssl-devel
pkcon install -y perl-core
pkcon install -y libselinux-devel
pkcon install -y container-selinux
```

## Install the postgres ansible role

### Create a directory for the ansible role. 

```bash
install -d ~/.ansible/roles/computate.computate_postgres
```

### Clone the postgres ansible role. 

```bash
git clone git@github.com:computate-org/computate_postgres.git ~/.ansible/roles/computate.computate_postgres
```

## Run the postgres ansible playbook to install the application locally

```bash
cd ~/.ansible/roles/computate.computate_postgres
ansible-playbook install.yml
```

