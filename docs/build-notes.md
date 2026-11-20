# Build Notes and Roadmap

## Work completed

1. Installed Debian directly on Vision and switched from installation-time
   Wi-Fi to wired Ethernet.
2. Configured SSH with a passphrase-protected Ed25519 key on Ultron.
   Checked the SSH daemon configuration before reloading the service.
3. Reestablished SSH access after replacing the home router.
4. Confirmed UFW was active and Fail2ban was running.
5. Installed Docker Engine and Compose. Created separate data and Compose
   directories under `/opt/docker`.

## Current checkpoint

Step 15B remains open after the initial Compose validation error. NGINX
deployment is deferred as of November 20, 2026. The November 18 upstream
release addressed multiple vulnerabilities, including CVE-2026-123007 and
CVE-2026-123633. The fixes start at NGINX 1.30.7 stable and 1.31.9 mainline.
A successful NGINX deployment on Vision has yet to be confirmed.

If the test container is already running, stop it and review the deployed
version and any prior network exposure. The next Docker milestone is to
validate a simple Compose file and run a one-shot `hello-world` service with
no published ports.

[NGINX release notice](https://nginx.org/2026.html) ·
[CERT-EU advisory](https://cert.europa.eu/publications/security-advisories/2026-022)

## Running update plan

1. Validate Docker Compose on Vision with a one-shot `hello-world` service
   and no published ports.
2. Set up Tailscale for private SSH access from Ultron to Vision.
3. Automate read-only health checks for uptime, memory, disk usage, and service
   status with a Python script and a systemd timer.
4. Back up key configuration files and verify that they can be restored.
5. Explore a monitoring assistant that summarizes health reports and requires
   approval before making system changes.
6. Revisit the optional NGINX test after verifying a patched official image
   against the current advisories and reviewing the running Debian kernel
   against Debian security guidance. Verify loopback-only access and remove
   the container after testing. [Test plan](../compose/nginx-test/README.md) ·
   [Debian kernel security tracker](https://security-tracker.debian.org/tracker/source-package/linux)
