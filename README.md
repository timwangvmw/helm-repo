# helm-repo

## 1. Package Chart and update index
```
helm package tap
helm repo index --url https://timwangvmw.github.io/helm-repo/ --merge index.yaml .
```

## 2. Push to Github Pages
```
git add .
git commit -m "update chart"
git push
```

## 3. Update Helm Repo (this will done by TAP FluxCD Controller)
```
helm repo update timwang_github
```

## 4. Search Helm Repo to see if it has been updated. 
```
helm search repo timwang_github
```

## 5. Test
```
helm install test-tim tap -n tap-sit --dry-run -f tap/values.yaml
```