# selinux-policy-dnsmasq-network-access
Allow **dnsmasq** to use TCP sockets.

## Why?
**dnsmasq** provides a couple ways to call external scripts under certain conditions. You may want to allow such scripts to make an outgoing TCP connection.

For example, you could use the `--dhcp-script` option to send details of a new DHCP lease to a HTTP server for automation purposes.

## Install
1. Install the `policycoreutils-devel` package (`yum install policycoreutils-devel` or `dnf install policycoreutils-devel`).
2. Run `build.sh`. This compiles the policy definition (.te) file to a compiled SELinux module binary (.pp), using a Makefile provided by your `policycoreutils-devel` package.
3. Install the generated .pp file by running `install.sh`.
