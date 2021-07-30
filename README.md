The Rancher overlay test tests the overlay network.

To test the overlay network create the DaemonSet that runs the swiss-army-knife container on every node.
The swiss-army-knife container pings the containers on all hosts.

Launch the overlay DaemonSet:

```
kubectl apply -f https://raw.githubusercontent.com/reylejano/rancher-overlay-test/master/overlaytest.yaml
```

Wait till until the DaemonSet has rolled out:

```
kubectl rollout status ds/overlaytest -w returns: daemon set "overlaytest" successfully rolled out.
...

daemonset "overlaytest" successfully rolled out
```

Run the script to test:

```
wget -O- https://raw.githubusercontent.com/reylejano/rancher-overlay-test/master/overlaytest.sh | sh
```
