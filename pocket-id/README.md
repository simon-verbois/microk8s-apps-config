# Pocket ID

This folder contains MicroK8s manifests and reusable templates for deploying Pocket ID.

## Contents

- `00-namespace.yaml.template`
- `01-pvc.yaml.template`
- `02-secrets.yaml.template`
- `03-configmap.yaml.template`
- `04-deployment.yaml.template`
- `05-service.yaml.template`
- `06-ingressroute.yaml.template`
- `README.md`

## How To Use

1. Review the tracked `.template` files first.
2. If you want working local files without the `.template` suffix, run:

```bash
for file in *.template; do
  mv "$file" "${file%.template}"
done
```

3. Replace all placeholders for domains, secrets, storage values, and sensitive configuration.
4. Apply the manifests in filename order when numeric prefixes are present.

## Notes

- Production `.yaml` files in this folder are local environment files and are ignored by the root `.gitignore`.
- The `.template` files are sanitized versions intended for reuse and publication.
- Generate the `ENCRYPTION_KEY` with a command such as `openssl rand -base64 32`.
- Create the initial admin account from `https://<your-app-url>/setup` after the deployment is reachable.
