Gazzang Ansible Playbooks
=========================

Ansible playbooks for deploying the full Gazzang product-set. This includes:

* `zncrypt` - Lightweight encryption utility that provides:
  * Transparent data-at-rest encryption (AES-256 CBC-IV, by default)
  * Process-based access provisioning to prevent unauthorized access to encrypted data
  * Integrated key management (when paired with zTrustee Server)
  
* `ztrustee-server` - Universal Key Management with fine-grained policy and access controls built in.

Getting Started
---------------

In order to get started, you will need to have Ansible installed and an inventory file ready to go.

To get up and running, we recommend utilizing the Python `virtualenv` application to create a staging environment. If using `virtualenv`:

```
# clone the Gazzang ansible repo
git clone https://github.com/gazzang/ansible.git

# create the virtual environment (assuming virtualenv is installed)
cd ansible
virtualenv venv
source venv/bin/activate

# install the necessary prerequisites (including ansible)
pip install -r requirements.txt
```

Once Ansible is installed, you will need to create an inventory (a list of servers you would like to bootstrap/convert). An example inventory file will look like:

```
# servers to install zncrypt on
[zncrypt]
root@machine1.example.com
root@machine2.example.com
root@machine3.example.com
```

And is expected (unless running custom commands) to be in the `hosts` file. This is optional though.

Once Ansible and your inventory are installed, simply run the included `run-playbook.sh` script to get started. This will take all commands from the CLI and pass them to the `ansible-playbook` command, so pass any extra configuration options as necessary.

As long as you have SSH configured to your machine correctly (passwords, SSH keys, etc.), then everything should (hopefully) work out of the box.

Inventory
---------

The inventory categories can be either `zncrypt` or `ztrustee-server` depending on the product you would like to install. 

The quickstart script expects the inventory to be specified in a `hosts` file in the current working directory, but this is optional.

Comments, Concerns
------------------

If you happen to stumble upon a bug, or would like to contribute, just send us a note at <support@gazzang.com>.
