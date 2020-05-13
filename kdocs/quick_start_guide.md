
cp -rfp inventory/sample inventory/mycluster

declare -a IPS=(192.168.219.43)
CONFIG_FILE=inventory/mycluster/hosts.yaml python3 contrib/inventory_builder/inventory.py ${IPS[@]}


ansible-playbook -i inventory/mycluster/hosts.yaml  --become --become-user=root cluster.yml
