# mmeuric_iot

Repo de configuration du projet **Inception-of-Things** (42), partie 3.

Argo CD (namespace `argocd`) surveille le dossier `manifests/` et le déploie
dans le namespace `dev` d'un cluster k3d.

Application : image Docker Hub [`wil42/playground`](https://hub.docker.com/r/wil42/playground), tags `v1` et `v2`, port 8888.

## Changer de version

```bash
sed -i 's#wil42/playground:v1#wil42/playground:v2#' manifests/deployment.yaml
git commit -am "v2" && git push
```

Puis `curl http://localhost:8888/` renvoie `{"status":"ok", "message": "v2"}`.
