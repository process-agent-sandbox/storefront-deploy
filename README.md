# storefront-deploy

Argo CD configuration for [storefront](https://github.com/process-agent-sandbox/storefront).

- `argo/` holds the Argo CD `Application` per environment. Argo CD syncs automatically.
- `envs/staging` and `envs/prod` are Kustomize overlays. `images[].newTag` is the storefront
  image that runs in that environment.

To deploy, open a pull request that changes `newTag`: first in `envs/staging`, then promote the
same tag to `envs/prod`. To roll back, set `envs/prod` back to the previous tag or revert the
promotion.
