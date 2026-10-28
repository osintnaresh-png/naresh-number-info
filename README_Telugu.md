# NARESH Number Information — Render Free Hosting

ఈ project లో Flask Hacker Theme UI, number lookup proxy, readable `VIEW_RAW_JSON_DUMP`,
Copy JSON, Download JSON features ఉంటాయి.

## Files
- `app.py` — Flask application
- `requirements.txt` — Python packages
- `render.yaml` — Render service configuration
- `.gitignore` — local secret/environment files ignore చేయడానికి

## Render లో deploy చేయడం

1. GitHub.com లో sign in/create account చేయండి.
2. `New repository` ఎంచుకోండి. పేరు `naresh-number-info` పెట్టండి; **Private** ఎంచుకోవడం మంచిది.
3. `Create repository` చేయండి.
4. `Add file` → `Upload files` నొక్కండి.
5. ఈ ZIP లోని folder లో ఉన్న files (`app.py`, `requirements.txt`, `render.yaml`, `.gitignore`, `README_Telugu.md`) upload చేయండి. ZIP file ని మాత్రమే upload చేయవద్దు.
6. `Commit changes` నొక్కండి.
7. Render.com లో sign in చేసి `New` → `Web Service` ఎంచుకోండి; GitHub connect చేసి repository ని connect చేయండి.
8. Build Command: `pip install -r requirements.txt`
9. Start Command: `gunicorn app:app`
10. Free plan ఎంచుకోండి.
11. Environment Variables లో `NUMBER_API_KEY` అనే key, `1Week` అనే value (లేదా API provider ఇచ్చిన valid key) పెట్టండి.
12. Deploy చేయండి. Deploy పూర్తయ్యాక Render ఇచ్చిన `https://...onrender.com` URL open చేయండి.

## Local run (optional)

Windows PowerShell:
```powershell
$env:NUMBER_API_KEY="1Week"
pip install -r requirements.txt
python app.py
```
Browser: `http://127.0.0.1:5000`

## Notes
- API key ని public GitHub repository లో code గా ఉంచవద్దు; Render Environment Variables లో మాత్రమే పెట్టండి.
- `1Week` key invalid/expired అయితే API provider నుంచి valid key అవసరం.
- API data, response fields, provider access limits external API మీద ఆధారపడి ఉంటాయి.
- Render free web services inactivity తర్వాత sleep అవుతాయి; మొదటి request కి startup delay ఉండవచ్చు.
- Use this lookup only for information you are authorized to access.
