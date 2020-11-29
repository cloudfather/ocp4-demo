## Builtin Image Registry

#### To start the images registry
```bash
oc edit configs.imageregistry.operator.openshift.io cluster
```

1. In the previous command you need to search for 
__managementState__

Then you need to change the status to __Managed__

2. Search for __storage__ -> in spec, and change it to whatever sotorageClass you have or make it emptyDir
```yaml
  storage:
    emptyDir: {}
```

3. To ensure the edit takes place
```bash
oc get pods -n openshift-image-registry
```

4. Ensure the image registry cluster operator is in __Available__
```bash
oc get co image-registry
```
