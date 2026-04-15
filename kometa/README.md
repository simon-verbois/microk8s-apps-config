# Kometa

This folder contains MicroK8s manifests and reusable templates for deploying a media library automation tool.

## Contents

- `00-namespace.yaml.template`
- `01-configmap.yaml.template`
- `02-deployment.yaml.template`
- `README.md`
- `config/config.yml.template`: template for the main Kometa configuration
- `config/movies.yml.template`: template for movie collections
- `config/shows.yml.template`: template for show collections
- `config/assets/`: tracked asset directory

## How To Use

1. Review the tracked `.template` files first.
2. If you want working local files without the `.template` suffix, run:

```bash
for file in *.template; do
  mv "$file" "${file%.template}"
done
```

3. Copy `config/config.yml.template` to `config/config.yml`.
4. Copy `config/movies.yml.template` to `config/movies.yml` if you want a local editable movie configuration.
5. Copy `config/shows.yml.template` to `config/shows.yml` if you want a local editable show configuration.
6. Replace all placeholders for storage paths, IPs, tokens, and API keys.
7. Apply the manifests in filename order when numeric prefixes are present.

## Notes

- Production `.yaml` files in this folder are local environment files and are ignored by the root `.gitignore`.
- The `.template` files are sanitized versions intended for reuse and publication.
- `config/config.yml`, `config/movies.yml`, and `config/shows.yml` are intended to stay local and ignored by Git.
- `config/assets/`, `config/config.yml.template`, `config/movies.yml.template`, and `config/shows.yml.template` are tracked on purpose.
