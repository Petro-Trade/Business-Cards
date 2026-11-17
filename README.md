# Petro Trade – Digital Business Cards

Free digital business cards hosted on GitHub Pages. Scan a QR code → contact card opens → tap **Save Contact** to add it to the phone.

## Files
| File | Purpose |
|---|---|
| `index.html` | The card page. Shows one person, chosen by `?id=` in the URL |
| `staff.json` | **The only file you edit** – company details + one entry per person |
| `qr.html` | Admin page – generates a QR code for everyone in staff.json (download PNG / print) |
| `qrcode.js` | QR library (MIT licence), so no outside services are needed |
| `logo.png` | *(add this yourself)* Petro Trade logo. If missing, a text wordmark is shown |

## Set up (once)
1. On GitHub, create a new **public** repo, e.g. `cards` under the `ptcard` account.
2. Upload all files from this folder (plus `logo.png`).
3. Repo **Settings → Pages → Deploy from a branch → main / root** → Save.
4. After a minute the site is live at `https://ptcard.github.io/cards/`

## Add or edit a person
Edit `staff.json` on GitHub and commit. Each person needs a unique `id` (lowercase, no spaces):

```json
{
  "id": "john-smith",
  "firstName": "John",
  "lastName": "Smith",
  "title": "Operations Manager",
  "mobile": "+1 555 123 4567",
  "phone": "",
  "email": "john.smith@petrotrade.com",
  "linkedin": ""
}
```
Leave a field as `""` to hide it. If `phone` is blank, the company phone is used as the office number.

Their card is then at `https://ptcard.github.io/cards/?id=john-smith`

## Get QR codes
Open `https://ptcard.github.io/cards/qr.html` → **Download PNG** for each person (1200 px, print quality).

The QR code only contains the link, so **changing someone's details never requires reprinting** – just edit staff.json. Only changing their `id` breaks their QR.

## Notes
- `staff.json` is public (anyone can view it). Only put details you'd print on a business card.
- When someone leaves, delete their entry – their QR will then show "Contact not found".
