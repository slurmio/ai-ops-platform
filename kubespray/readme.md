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
```
## To install ingress controller to Kube

```bash
ansible-playbook kubernetes/install-ingress.yml 
```

DO NOT forget to set proper external ip vars to %CP_IP% %NODE1_IP% %NODE2_IP% in inventory as well as %EXTERNAL_IP% in ingress