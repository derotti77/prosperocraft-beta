# ProsperoCraft beta list

`revoked.json` is the list of beta codes that are no longer accepted. Every ProsperoCraft console
reads it over HTTPS about once a day. If the file cannot be reached, codes that already work keep
working — a broken link never locks anybody out.

```jsonc
{
  "min_serial": 0,            // every code below this number is refused
  "revoked": [7, 12],         // single codes that are refused
  "message": "Beta 1 is over" // optional line shown on the console
}
```

ProsperoCraft is a free, native Minecraft: Java Edition port for jailbroken PlayStation 5 consoles.
It is not affiliated with Mojang, Microsoft or Sony, and Minecraft itself is not distributed with
it — the launcher downloads it with the player's own account.

- Beta codes and devlogs: https://tiktok.com/@derotti77
- Releases and contact: https://github.com/derotti77
- Support the project: https://ko-fi.com/derotti

ProsperoCraft is licensed under GPL-3.0-or-later; the source is handed out on request (see the
`SOURCE-OFFER.txt` that ships with the download).
