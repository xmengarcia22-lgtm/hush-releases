# Hush release fingerprints

Every release of the Hush web app at **https://hushappofficial.com** is listed here with the SHA-256 fingerprint of its `index.html`.

`index.html` carries an integrity fingerprint for every other file the app loads (scripts and styles), and browsers refuse any file that doesn't match. So this one fingerprint pins the whole app. If the page you are served matches the newest line below, you are running exactly the code that was released.

**This list is append-only.** Lines are only ever added, never edited or removed. A fingerprint served by the site that doesn't appear here is a warning sign.

| # | Date (UTC) | Release | SHA-256 of index.html |
|---|------------|---------|-----------------------|
| 1 | 2026-10-09 | Go-live: first release on hushappofficial.com | `230981406a09e72623baf55b34ac33ec11186852ca1dbd868d48bc9c094b9072` |
| 2 | 2026-10-09 | Founder badge, tappable @mentions, @mention picker | `78e87b54de583f73e15da9edaea62e9699400bd9f8943d9a0345c8b086771514` |
| 3 | 2026-10-09 | Caching fix: versioned file addresses so updates never mix old and new files | `84bb13e1c3808373b37e3cdf2787d4fbcf120918ee0907bbc4453e25d4e14290` |
| 4 | 2026-10-09 | Badges shown everywhere a name appears (side menu, account lists, search, forwards, replies and more) | `7700d5364fdd25b7695aa4d62208b127d4d65f1fce834093be0ca78176b70e51` |
| 5 | 2026-10-09 | Neutral example phone numbers in sign-up and settings fields | `e87def444e4e654949627b1ee7e83bcf3c31cef567c71cdb8dddcc19b75ae247` |
| 6 | 2026-10-09 | Swipe navigation, Back closes what is open, Contacts tab, own @mention opens Saved Messages | `13dffd0797428bf5991cf10264cfb015443ff0ea590e97f2f554a69ace5e1bc1` |
| 7 | 2026-10-10 | Instant sign-up, log in with email, phone or username, emailed verification codes, 60-second resend cooldown, typed device-approval code | `787cefc8e7c04b06eea1073e00c64febb66768156526165bde5308a854b4bc9e` |
| 8 | 2026-10-10 | New-device login fixes: retry after backing out, longer sign-in window, clearer error messages, update notice for open pages | `d169c3e5d851e266ca77c76e0a498c8ae489c2d39c631bac2a503c1c1a015c63` |

## How to check it yourself

Download the page the site is serving and compute its fingerprint. The result should equal the newest line in the table.

**Windows (PowerShell):**

```
curl.exe -s -o hush.html https://hushappofficial.com/
certutil -hashfile hush.html SHA256
```

**macOS:**

```
curl -s https://hushappofficial.com/ | shasum -a 256
```

**Linux:**

```
curl -s https://hushappofficial.com/ | sha256sum
```
