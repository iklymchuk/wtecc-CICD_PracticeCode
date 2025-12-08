# Building an Image

This folder holds the files for the lab: _Building an Image_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
tkn clustertask ls | grep buildah
```

We need to reference the new buildah task that you want to use. In the previous steps, you simply changed the name of the reference to the task. But since the `buildah` task is a `ClusterTask`, you need to add the statement `kind: ClusterTask` under the name so that Tekton knows to look for a ClusterTask and not a regular Task:
```
      taskRef:
        name: buildah
        kind: ClusterTask
```

```
kubectl apply -f pipeline.yaml
kubectl apply -f pvc.yaml
```

Start the Pipeline
```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch=main \
    -p build-image=image-registry.openshift-image-registry.svc:5000/$SN_ICR_NAMESPACE/tekton-lab:latest \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

```
kubectl get clustertask buildah -o yaml > buildah-task.yaml
```
