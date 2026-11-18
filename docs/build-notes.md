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

## Planned milestones

1. Complete the Nginx test and save the verification results for a demo.
2. Set up Tailscale and verify OpenSSH access from Ultron over the private
   connection.
3. Build an unprivileged Python health check for uptime, memory, disk
   usage, and service status. Test it manually, then schedule it with a
   systemd timer and review the journal from Ultron.
4. Back up selected configuration files and verify recovery with a
   sample restore.
5. Explore an assistant that summarizes health reports and requires
   explicit approval before executing system changes.

## Running update plan

Update the repository only after a significant project change. Examples
include completing a verified milestone, deploying or retiring a service,
changing the network or security setup, and resolving a blocker that changes
the project roadmap. Bundle routine troubleshooting and minor adjustments
into the next relevant milestone entry.

For each significant change, record the date, step, result, verification,
and next action. Update the [repository README](../README.md) if that
change moves the project checkpoint. Update the relevant instructions or
configuration example if the tested procedure changes. Keep credentials,
private network addresses, and unredacted logs out of the public repository.

### Update history

| Date | Update | Result and next action |
| --- | --- | --- |
| 2026-11-18 | Published the initial project files on GitHub. | Verified the README, build notes, Nginx instructions, and Compose example on `main`. Step 15B remains open. Validate the corrected Compose file on Vision, then verify the container status and HTTP response. |
