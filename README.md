# askakhil.github.io — Tesla Fleet API public key hosting

This repo is the GitHub Pages user site for `askakhil`. It exists so Tesla can fetch this Fleet API app's public key at:

https://askakhil.github.io/.well-known/appspecific/com.tesla.3p.public-key.pem

Contents:
- `.well-known/appspecific/com.tesla.3p.public-key.pem` — the app's ECDH P-256 public key (public by design; the private key never leaves Muse's VM)
- `.nojekyll` — disables Jekyll so GitHub Pages serves the dot-directory
- `index.html` — placeholder page at the site root

Why the user-site repo and not a project repo: Tesla fetches the key from the ROOT of the registered domain. A project repo (e.g. askakhil/tesla-key) would serve the file under /tesla-key/.well-known/..., which Tesla never requests. Only the <username>.github.io repo controls the site root.

Publish: push to the default branch of askakhil/askakhil.github.io. GitHub Pages serves user sites automatically from the default branch.
