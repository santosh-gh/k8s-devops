# Create Cluster
kind create cluster --config kind.config --name my-cluster

#! Note: Choose 1080 and 1443 due to
# Command Output: Error: rootlessport cannot expose privileged port 80, you can add 'net.ipv4.ip_unprivileged_port_start=80' to /etc/sysctl.conf (currently 1024), or choose a larger port number (>= 1024): listen tcp 0.0.0.0:80: bind: permission denied

kind delete clusters --all