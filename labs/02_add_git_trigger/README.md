# Adding GitHub Triggers

This folder holds the files for the lab: _Adding GitHub Triggers_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

```
tkn task ls
tkn pipeline ls
tkn eventlistener ls
```

Terminal 1
```
kubectl port-forward service/el-cd-listener  8090:8080
```

Terminal 2
```
curl -X POST http://localhost:8090 \
  -H 'Content-Type: application/json' \
  -d '{"ref":"main","repository":{"url":"https://github.com/iklymchuk/wtecc-CICD_PracticeCode.git"}}'
  ```
