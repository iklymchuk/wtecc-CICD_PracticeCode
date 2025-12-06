# Integrate Unit Test Automation

This folder holds the files for the lab: _Integrate Unit Test Automation_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
tkn hub install task flake8
tkn task ls
```

```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

```
tkn pipelinerun ls
tkn pipelinerun logs --last
```

Fix OpenShift error for external package
```
tkn task describe git-clone
curl -O https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.9/git-clone.yaml
```

```
#  OpenShift's Pod Security admission controller
      securityContext:
        runAsNonRoot: true
        capabilities:
          drop:
            - ALL
        seccompProfile:
          type: RuntimeDefault
```

```
kubectl apply -f git-clone.yaml
```

```
tkn task describe flake8
curl -O https://raw.githubusercontent.com/tektoncd/catalog/main/task/flake8/0.1/flake8.yaml
kubectl apply -f flake8.yaml
```
