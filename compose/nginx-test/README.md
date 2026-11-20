# NGINX Compose Test

**Deployment deferred as of November 20, 2026.** Step 15B can validate
Docker Compose without pulling or starting NGINX. See the
[project roadmap](../../docs/build-notes.md#current-checkpoint).

If Vision already has a running `vision-nginx-test` container, stop the test
and keep it offline while checking its image and any previous exposure.

## When the test resumes

- Verify the current NGINX advisories and select a patched official image.
  The example uses `nginx:1.30.7-alpine`, which contains the November 18
  upstream fixes. Record the exact image digest and verify the version in the
  running container.
- Review Debian kernel security updates and verify the running kernel on
  Vision before starting the test.
- Use Docker Engine 28 or newer for the `127.0.0.1:8080` binding. Verify the
  HTTP response from Vision and confirm the port is unreachable from Ultron
  over the LAN. Keep the router free of port forwards for the test.
- Enable the `nginx-test` Compose profile only for the test and remove the
  test container afterward.

[NGINX security advisories](https://nginx.org/en/security_advisories.html) ·
[Official NGINX image tags](https://hub.docker.com/_/nginx/tags) ·
[Docker port publishing](https://docs.docker.com/engine/network/port-publishing/)
