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

At Step 15B, the first Nginx Compose file reported a validation error.
The next milestone is to validate the corrected configuration and verify
an HTTP response from Vision.

## Running update plan

1. Verify that Nginx responds locally on Vision after deployment with Docker
   Compose.
2. Set up Tailscale for private SSH access from Ultron to Vision.
3. Automate read-only health checks for uptime, memory, disk usage, and service
   status with a Python script and a systemd timer.
4. Back up key configuration files and verify that they can be restored.
5. Explore a monitoring assistant that summarizes health reports and requires
   approval before making system changes.
