# generate controlplanes
talosctl gen config sshme-in https://192.168.1.111:6443   --with-secrets cluster-secrets.yaml   --config-patch @patches/cluster/general.yaml   --config-patch @patches/cluster/network.yaml   --config-patch-control-plane @patches/nodes/cp-nuc-n150.yaml --force

# apply config
use talos config instead of insecure when node is already setup
talosctl apply-config --insecure -n 192.168.1.226 --file controlplane.yaml

