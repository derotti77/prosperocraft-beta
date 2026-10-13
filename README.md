# Beta codes

`revoked.json` is the only file in this folder that has to be published. Consoles fetch it once a
day from the URL in [`src/ps5_brand.hpp`](../src/ps5_brand.hpp) (`kRevokeUrl`) and refuse the codes
listed in it. When the file is unreachable, codes that were accepted before keep working, so a
broken link never locks players out.

```jsonc
{
  "min_serial": 0,            // every code below this serial is refused (bulk end of a wave)
  "revoked": [7, 12],         // single serials that are refused
  "message": "Beta 1 is over" // optional line shown on the console
}
```

Handing out and withdrawing codes:

```bash
tools/betacode.py new --count 20 --days 90 --label "wave 2"   # mint, writes tooling/beta_codes.csv
tools/betacode.py list                                        # which serial went where
tools/betacode.py revoke 7 12 --message "Beta 1 is over"      # updates this folder's revoked.json
git -C . add beta/revoked.json && git commit -m "Withdraw wave 1" && git push
```

`tooling/beta_secret.txt` signs every code and is deliberately not in the repository. Back it up:
without it, codes already handed out cannot be re-created, and a build made with a different secret
rejects all of them.
