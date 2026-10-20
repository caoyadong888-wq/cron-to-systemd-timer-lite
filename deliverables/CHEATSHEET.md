# Cron to OnCalendar (lite)

| Crontab | systemd |
| --- | --- |
| `0 2 * * *` | `OnCalendar=*-*-* 02:00:00` |
| `*/15 * * * *` | `OnCalendar=*-*-* *:00/15:00` |
| `15 3 * * 1-5` | `OnCalendar=Mon..Fri *-*-* 03:15:00` |
| `0 0 * * 0` | `OnCalendar=Sun *-*-* 00:00:00` |
| `0 6 1 * *` | `OnCalendar=*-*-01 06:00:00` |
| `@daily` | `OnCalendar=*-*-* 00:00:00` |
| `@hourly` | `OnCalendar=*-*-* *:00:00` |
| `@reboot` | `OnBootSec=1min` (no OnCalendar) |

Weekday numbers: 0 or 7 Sunday, 1 Monday, 5 Friday, 6 Saturday.

Service: `Type=oneshot`, absolute `ExecStart=`, optional `User=` and `WorkingDirectory=`. Timer: `Persistent=true` on calendar timers, `Unit=<name>.service`, `WantedBy=timers.target`. Do not enable the service and the timer together.

A `/home/deploy/...` command is a guess of `User=deploy` and the directory that holds the script. Confirm both before enable.
