# NanoClaw Setup Status

**Last Updated**: 2026-04-07 01:00

## ✅ All Done!

### Channels

| Channel | Status | Details |
|---------|--------|---------|
| Telegram | ✅ Working | Bot: `@Clawseg7_bot`, chat: `telegram_kev` |
| Slack | ✅ Working | Bot: `@Claw`, channel: `#general` (`slack_main`) |

### Infrastructure

- **Credential proxy**: Running on `172.17.0.1:3001`, injecting OAuth token into containers
- **NixOS firewall**: `docker0` added as trusted interface so containers can reach host
- **Service**: `nanoclaw.service` (systemd user service), enabled and running

## 🔧 Configuration

- **Working directory**: `/home/kev/projects/nanoclaw`
- **Logs**: `logs/nanoclaw.log`
- **Database**: `store/messages.db`
- **Environment**: `.env` (synced to `data/env/env` for containers)

## 📝 Quick Commands

```bash
# Check service status
systemctl --user status nanoclaw

# Restart service
systemctl --user restart nanoclaw

# View logs
tail -f /home/kev/projects/nanoclaw/logs/nanoclaw.log

# Check registered groups
sqlite3 store/messages.db "SELECT jid, name, folder FROM registered_groups;"
```
