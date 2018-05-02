# Geth Private CloudConfig

This config file allow to create node which has no public access from the
outer network. It uses iptables to close any network activity except of
node itself and SSH connections.

## Usage

After node creation you can connect to the node via SSH tunnel. Assume that
you node has hostname like `ethnode` (you can replace it with node IP address).

```bash
ssh -L 8040:ethnode:8545 -N ethereum@ethnode
```

Now you can connect to the network with web3 like so:
```javascript
const web3 = new Web3('http://localhost:8040');
```
