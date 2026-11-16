# Site deployments

## Star Map

- Live URL: `https://stars.rondomingue.com/`
- Cloudflare Pages project: `stars`
- GitHub repository: `rondomingue/tools`
- Production branch: `main`
- Published directory: `stars/`
- Build command: none
- Build output directory: `stars`
- Root directory: repository root
- Cloudflare DNS: proxied CNAME `stars` → `stars-ba5.pages.dev`
- GitHub app access: restricted to the `tools` repository
- Automatic production deployments: enabled for commits to `main`

The site entry point is `stars/index.html`. Keep all files required by the
standalone Star Map inside `stars/` so the Pages project does not publish the
other tools in this repository.

## Pattern for future sites

1. Create a dedicated directory containing a top-level `index.html`.
2. Commit and push it to `main`.
3. In Cloudflare Pages, import `rondomingue/tools` using the legacy Pages Git
   workflow.
4. Leave the build command and root directory empty.
5. Set the build output directory to the dedicated directory name.
6. Restrict the Cloudflare GitHub app to only the required repository.
7. Add the desired hostname under **Custom domains**.
8. Create or confirm the proxied CNAME that Cloudflare Pages specifies.
9. Verify both the generated `pages.dev` URL and the custom HTTPS URL.

