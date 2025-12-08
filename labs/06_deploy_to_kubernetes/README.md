# Deploy to Kubernetes / OpenShift

This folder holds the files for the lab: _Deploy to Kubernetes_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
tkn clustertask ls | grep openshift-client
```

```
kubectl apply -f pipeline.yaml
```

```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch=main \
    -p app-name=hitcounter \
    -p build-image=image-registry.openshift-image-registry.svc:5000/$SN_ICR_NAMESPACE/tekton-lab:latest \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

```
tkn pipelinerun ls
tkn pipelinerun logs --last
```

Check the Deployment
```
kubectl get all -l app=hitcounter
```
