# microk8s-ansible

Playbook de ansible para la instalación de un microk8s con nodos en HA y complementos.


Script para pasar las claves ssh:

```bash
#!/bin/bash

# Define the path to the file containing the SSH public key
SSH_KEY_FILE="path/to/your/public_key.pub"

# Define the list of remote hosts and their corresponding passwords
HOSTS=(
    "user@192.168.1.100"
    "user@192.168.1.101"
    "user@192.168.1.102"
    "user@192.168.1.110"
    "user@192.168.1.111"
)

# Define the corresponding passwords for the remote hosts
PASSWORDS=(
    "password_for_192.168.1.100"
    "password_for_192.168.1.101"
    "password_for_192.168.1.102"
    "password_for_192.168.1.110"
    "password_for_192.168.1.111"
)

# Define the path to the authorized_keys file on the remote host
AUTHORIZED_KEYS_PATH=".ssh/authorized_keys"

# Read the SSH public key
if [ ! -f "$SSH_KEY_FILE" ]; then
    echo "SSH key file not found: $SSH_KEY_FILE"
    exit 1
fi

SSH_KEY=$(cat "$SSH_KEY_FILE")

# Check if sshpass is installed
if ! command -v sshpass &> /dev/null; then
    echo "sshpass is not installed. Please install sshpass and try again."
    exit 1
fi

# Function to add the SSH key to a remote host
add_ssh_key() {
    local host="$1"
    local password="$2"
    
    # Check if the SSH key is already present on the remote host
    sshpass -p "$password" ssh -o StrictHostKeyChecking=no "$host" "grep -qF '$SSH_KEY' $AUTHORIZED_KEYS_PATH || echo '$SSH_KEY' >> $AUTHORIZED_KEYS_PATH"
    
    if [ $? -eq 0 ]; then
        echo "SSH key added to $host"
    else
        echo "Failed to add SSH key to $host"
    fi
}

# Iterate over the list of hosts and add the SSH key
for i in "${!HOSTS[@]}"; do
    add_ssh_key "${HOSTS[$i]}" "${PASSWORDS[$i]}"
done
```