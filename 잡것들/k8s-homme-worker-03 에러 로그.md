### rpc error: code = Unknown ###

./syslog:Mar  6 00:50:15 k8s-homme-worker-03 kubelet[1068]: E0306 00:50:15.931015    1068 run.go:74] "command failed" err="failed to run Kubelet: unable to determine runtime API version: rpc error: code = Unknown desc = server is not initialized yet"

./syslog:Mar  6 01:37:14 k8s-homme-worker-03 containerd[1023]: time="2024-03-06T01:37:14.952831832+09:00" level=error msg="ContainerStatus for \"6a9c130bd6a18a996dce4b2d928a1f52dee8298c93a8255f6672e0667573ac3e\" failed" error="rpc error: code = NotFound desc = an error occurred when try to find container \"6a9c130bd6a18a996dce4b2d928a1f52dee8298c93a8255f6672e0667573ac3e\": not found"

### dial tcp 127.0.0.1:6443: connect: connection refused ###

./syslog:Mar 6 00:50:26 k8s-homme-worker-03 kubelet[1138]: E0306 00:50:26.073046 1138 controller.go:144] failed to ensure lease exists, will retry in 200ms, error: Get "https://localhost:6443/apis/coordination.k8s.io/v1/namespaces/kube-node-lease/leases/k8s-homme-worker-03?timeout=10s": dial tcp 127.0.0.1:6443: connect: connection refused

### Network is unreachable ###

./syslog:Mar  6 00:50:15 k8s-homme-worker-03 rsyslogd: omfwd/udp: socket 14: sendto() error: Network is unreachable [v8.2001.0 try https://www.rsyslog.com/e/2354 ]
./syslog:Mar  6 00:50:15 k8s-homme-worker-03 rsyslogd: omfwd: socket 14: error 101 sending via udp: Network is unreachable [v8.2001.0 try https://www.rsyslog.com/e/2354 ]

./metricbeat/metricbeat.1:2024-03-06T00:52:27.426+0900	ERROR	[publisher_pipeline_output]	pipeline/output.go:155	Failed to connect to backoff(elasticsearch(http://10.3.10.163:9200)): Get http://10.3.10.163:9200: dial tcp 10.3.10.163:9200: connect: network is unreachable

Binary file ./journal/4f04abd8bc1d4a4cab36e8573eed039b/system.journal matches
./installer/cdebconf/questions.dat:Name: netcfg/gateway_unreachable
./installer/cdebconf/questions.dat:Template: netcfg/gateway_unreachable
./installer/cdebconf/templates.dat:Name: netcfg/gateway_unreachable

### ceph error ###

rook-ceph.cephfs.csi.ceph.com-reg.sock
./syslog:Mar 6 00:50:26 k8s-homme-worker-03 kubelet[1138]: }. Err: connection error: desc = "transport: Error while dialing dial unix /var/lib/kubelet/plugins_registry/rook-ceph.cephfs.csi.ceph.com-reg.sock: connect: connection refused"

rook-ceph.rbd.csi.ceph.com-reg.sock
./syslog:Mar 6 00:50:26 k8s-homme-worker-03 kubelet[1138]: }. Err: connection error: desc = "transport: Error while dialing dial unix /var/lib/kubelet/plugins_registry/rook-ceph.rbd.csi.ceph.com-reg.sock: connect: connection refused"

### btrfs, devmapper, zfs###

./syslog:Mar 6 00:50:15 k8s-homme-worker-03 containerd[1002]: time="2024-03-06T00:50:15.498324233+09:00" level=info msg="skip loading plugin \"io.containerd.snapshotter.v1.btrfs\"..." error="path /var/lib/containerd/io.containerd.snapshotter.v1.btrfs (ext4) must be a btrfs filesystem to be used with the btrfs snapshotter: skip plugin" type=io.containerd.snapshotter.v1

./syslog:Mar 6 00:50:15 k8s-homme-worker-03 containerd[1002]: time="2024-03-06T00:50:15.498418084+09:00" level=warning msg="failed to load plugin io.containerd.snapshotter.v1.devmapper" error="devmapper not configured"

./syslog:Mar 6 00:50:15 k8s-homme-worker-03 containerd[1002]: time="2024-03-06T00:50:15.500244310+09:00" level=info msg="skip loading plugin \"io.containerd.snapshotter.v1.zfs\"..." error="path /var/lib/containerd/io.containerd.snapshotter.v1.zfs must be a zfs filesystem to be used with the zfs snapshotter: skip plugin" type=io.containerd.snapshotter.v1