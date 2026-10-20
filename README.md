# Cron to systemd Timer (lite)

Free subset. A short field map and two filled unit pairs. The full pack adds the converter, `/etc/cron.d` mode, the round-trip notes, and the billing, homelab, and cron.d examples.

## English

### Deliverables

- `deliverables/CHEATSHEET.md` — minute/hour/day/weekday pieces and the `@daily` / `@hourly` / `@reboot` rows
- `examples/daily-backup.service` and `examples/daily-backup.timer` — `@daily /home/deploy/bin/backup.sh`
- `examples/boot-warmup.service` and `examples/boot-warmup.timer` — `@reboot` as `OnBootSec=1min`

```bash
systemd-analyze calendar '*-*-* 00:00:00'
```

Enable the `.timer` only. The service has no `[Install]` section.

`0 2 * * *` is `*-*-* 02:00:00`. `15 3 * * 1-5` is `Mon..Fri *-*-* 03:15:00`. `*/15 * * * *` is `*-*-* *:00/15:00`.

Cron ORs a restricted day-of-month with a restricted day-of-week. systemd ANDs them. The full pack's converter warns on that line and documents the split.

Full version: GUMROAD_URL

## 中文

免费子集：一张字段对照和两对填好的单元。完整版另有转换脚本、`/etc/cron.d` 模式、往返说明，以及账单、家用和 cron.d 三份示例。

### 交付物

- `deliverables/CHEATSHEET.md` — 分、时、日、周的写法，以及 `@daily` / `@hourly` / `@reboot`
- `examples/daily-backup.service` 与 `examples/daily-backup.timer` — `@daily /home/deploy/bin/backup.sh`
- `examples/boot-warmup.service` 与 `examples/boot-warmup.timer` — `@reboot` 写成 `OnBootSec=1min`

只启用 `.timer`。service 没有 `[Install]`。

日和周同时限制时，cron 是“或”，systemd 是“并且”。完整版会在这种行上写警告，并说明要怎么拆成两条。

Full version: GUMROAD_URL

## Delivery time / 交付时间

Delivery time: instant download after purchase
