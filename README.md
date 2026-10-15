# Activité — Automatisation avec Ansible & API Node.js

**Étudiant :** [Narjess Dabbech]  
**VM Administration :** devsecops-vm (Ubuntu 22.04)  
**Date :** 15/10/2026

---

## VII. Automatisation avec Ansible

### 25- Installation d'Ansible

**Commandes exécutées :**

```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
ansible --version
```

**Résultat :**

```
ansible [core 2.17.14]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/Ubuntu/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /home/Ubuntu/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible
  python version = 3.10.12
  jinja version = 3.0.3
  libyaml = True
```

**Capture d'écran :**

![Version Ansible](./screenshots/25-ansible-version.png)

---

### 26- Inventory et test de communication

**Fichier `inventory` :**

```ini
[ubuntu_servers]
localhost ansible_connection=local ansible_python_interpreter=/usr/bin/python3

[all:vars]
ansible_python_interpreter=/usr/bin/python3
```

**Commande :**

```bash
ansible all -i inventory -m ping
```

**Résultat :**

```json
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

**Capture d'écran :**

![Ansible ping](./screenshots/26-ansible-ping.png)

---
