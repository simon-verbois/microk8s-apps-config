# joal

This folder contains MicroK8s manifests and reusable templates for deploying a torrent ratio simulator service.

## Contents

- `00-namespace.yaml.template`
- `01-pvc.yaml.template`
- `02-configmap.yaml.template`
- `03-deployment.yaml.template`
- `04-service.yaml.template`
- `README.md`
- `config/`: local configuration directory used by the production manifests

## How To Use

1. Review the tracked `.template` files first.
2. If you want working local files without the `.template` suffix, run:

```bash
for file in *.template; do
  mv "$file" "${file%.template}"
done
```

3. Replace all placeholders for storage paths, domains, secrets, usernames, and email addresses.
4. Apply the manifests in filename order when numeric prefixes are present.

## Notes

- Production `.yaml` files in this folder are local environment files and are ignored by the root `.gitignore`.
- The `.template` files are sanitized versions intended for reuse and publication.
- The local `config/` directory can contain private or machine-specific data and is ignored by Git.
