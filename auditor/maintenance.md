# 🩼 Maintenance

## No space left on device

If you see this message, it means that our cleaner job has not finished it's work and volumes from containers haven't removed

You may create a crontab via `crontab -e` to remove volumes every 15 minutes.

Example:

```
*/15 * * * * docker compose -f /opt/auditor/docker-compose.yml exec scanner-worker sh -c "docker volume rm \$(docker volume ls -q)"
*/15 * * * * echo "cleaning of volumes is done: " > /opt/auditor/last-cron-cleanup.txt
*/15 * * * * date >> /opt/auditor/last-cron-cleanup.txt
```
