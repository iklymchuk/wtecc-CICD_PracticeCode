# Create a base pipeline

This folder holds the files for the lab _Create a Base Pipeline_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
kubectl apply -f tasks.yaml
kubectl apply -f tasks.yaml
tkn pipeline start --showlog hello-pipeline
```

```
kubectl get pipelinerun hello-pipeline-run-9v84r -o yaml
kubectl get taskrun -o yaml
kubectl get taskrun hello-pipeline-run-9v84r-hello -o yaml
tkn taskrun logs hello-pipeline-run-9v84r-hello --follow
```

```
tkn pipeline start hello-pipeline \
    --showlog  \
    -p message="Hello Tekton!"
```

```
tkn pipeline start cd-pipeline \
    --showlog \
    -p repo-url="https://github.com/iklymchuk/wtecc-CICD_PracticeCode.git" \
    -p branch="main"
```
