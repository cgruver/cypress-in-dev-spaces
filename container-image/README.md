# Container Image with Node 20 and an embedded Chrome Browse

__Note:__ You will need `cluster-admin` privileges, or be granted access to the `etc-pki-entitlement` Secret by a `cluster-admin` for this first step.

```bash
oc extract secret/etc-pki-entitlement -n openshift-config-managed --to=entitlement --confirm
```

```bash
podman build -t cypress-in-devspaces:latest -f Containerfile -v ${PWD}/entitlement:/etc/pki/entitlement:Z .
```
