# Use Tekton CD Catalog

This folder holds the files for the lab: _Use Tekton CD Catalog_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
tkn hub install task git-clone --version 0.8
kubectl apply -f pvc.yaml
kubectl apply -f pipeline.yaml
```

```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

Output:
```
PipelineRun started: cd-pipeline-run-78x8t
Waiting for logs to be available...
```

```
tkn pipelinerun ls
tkn pipelinerun logs --last
```
