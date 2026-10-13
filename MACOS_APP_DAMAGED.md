# macOS says “gg0rg is damaged and can’t be opened”

gg0rg is signed with an Apple Developer ID and notarized by Apple. If macOS still
refuses to open it, the download was almost always marked as “quarantined” on the way
(browser, AirDrop, a copy via Finder or a sync folder) and the check failed on that
copy — not on the app itself.

## Fix

1. Move `gg0rg.app` into **Applications**.
2. Open **Terminal** and run:

   ```bash
   xattr -cr /Applications/gg0rg.app
   ```

3. Open gg0rg again.

This only removes the quarantine marker from this one app. It does not turn off any
protection for other apps.

## If that does not help

- Download the **.dmg** again from <https://mgmt0rg.com> (not the `.pkg`), open it and
  drag gg0rg into Applications.
- Right-click `gg0rg.app` → **Open** → **Open** once. macOS remembers the choice.
- Still stuck: in gg0rg use **Help → Fehlerbericht senden**, or write to
  mail@juliuskuehn.com with your macOS version.

Apple Silicon (M1 or newer) is required; Intel Macs are not supported.
