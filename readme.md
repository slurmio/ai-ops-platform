## Install kubespray

## Run following commands from kubespray directory:

```bash
VENVDIR=kubespray-venv
KUBESPRAYDIR=slurm_webinar_16_04_25
python3 -m venv $VENVDIR
source $VENVDIR/bin/activate
cd $KUBESPRAYDIR
pip install -U -r requirements.txt
ansible-playbook cluster.yml -i inventory/hetzner/inventory.ini --key-file ../keys/hetzner -e @vars.yml