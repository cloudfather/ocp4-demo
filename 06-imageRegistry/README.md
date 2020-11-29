## Builtin Image Registry

#### To start the images registry
```bash
oc edit configs.imageregistry.operator.openshift.io cluster
```

1. In the previous command you need to search for 
** managementState **

Then you need to change the status to ** Managed **

2. Search for ** storage ** -> in spec, and change it to whatever sotorageClass you have or make it emptyDir
```yaml
  storage:
    emptyDir: {}
```

3. To ensure the edit takes place
```bash
oc get pods -n openshift-image-registry
```

4. Ensure the image registry cluster operator is in ** Available **
```bash
oc get co image-registry
```
