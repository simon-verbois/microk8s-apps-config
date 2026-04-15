# MicroK8s Apps Config

This repository contains application deployment examples for a self-hosted MicroK8s cluster.

It is organized as a collection of small app-focused folders. Each project folder contains production YAML files used locally and sanitized `.template` files that can be copied and adapted to another environment.

## Repository Goal

This repository is meant to be a practical toolbox for common self-hosted applications on MicroK8s.

It helps you:

- keep app manifests grouped by project
- keep reusable templates without personal data
- document deployment steps in a simple and consistent way
- version one root repository instead of many small nested repositories

## Structure

Each application lives in its own folder.

Common patterns in each folder:

- ordered Kubernetes manifests such as `00-namespace.yaml`, `01-pvc.yaml`, `03-deployment.yaml`
- a matching `.template` file for each YAML file
- a local `README.md` explaining the project

Some projects also include a local `config/` directory used by production manifests. Those directories are intentionally ignored by Git because they often contain machine-specific or private data.

## How To Use A Project Folder

1. Open the project folder you want.
2. Read its `README.md`.
3. Copy the `.template` files into local `.yaml` files or adapt them to your own workflow.
4. Replace storage paths, domains, secrets, usernames, emails, and any placeholder values.
5. Apply the manifests to your MicroK8s cluster in file order.

## Naming Convention

Project folders use the application name directly, without the old `-k8s` suffix.

Examples:

- `audiobookshelf`
- `gitea-runner`
- `nextcloud`
- `vaultwarden`

## Notes

- Production `.yaml` files are ignored at the root level.
- Reusable `.template` files are tracked.
- The file `path-reference-report.txt` summarizes renamed paths and old references reviewed during this cleanup.

## License

This repository is distributed under the MIT license included in [LICENSE](/data/md0/microk8s-apps-config/LICENSE).

## Disclaimer

The content of this repository is provided for educational, informational, and self-hosting learning purposes only.

All files, manifests, templates, examples, and configuration ideas are shared as-is, without any warranty or guarantee of fitness for a particular purpose. You are solely responsible for reviewing, testing, securing, and adapting anything from this repository before using it in your own environment.

Some applications or deployment patterns included here could be misused for unauthorized access, copyright infringement, content piracy, data extraction, automation abuse, or other unlawful or unethical activities if deployed irresponsibly. This repository is not intended to encourage, support, or legitimize any illegal, harmful, abusive, or non-consensual use.

By using any content from this repository, you agree that you are fully responsible for complying with all applicable laws, regulations, service terms, licensing terms, and access rights in your jurisdiction and in the systems or content you interact with.

The author cannot be held responsible for any misuse, legal issue, content theft, copyright violation, unauthorized access, data loss, service outage, security issue, misconfiguration, or any other direct or indirect damage resulting from the use or misuse of the content provided here.
