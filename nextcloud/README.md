# Nextcloud

This folder contains MicroK8s manifests and reusable templates for deploying a self-hosted collaboration and file sharing platform.

## Contents

- `README.md`
- `ingressroute.yaml.template`
- `nextcloud-values.yaml.template`

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
