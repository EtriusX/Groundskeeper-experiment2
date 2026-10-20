GROUNDSKEEPER — CLEAN RAILWAY / GITHUB DEPLOYMENT

IMPORTANT: DO NOT upload this ZIP file itself to GitHub.
Extract it, then upload these items from INSIDE the extracted folder:
  server.js
  package.json
  public/ (with index.html, app.js, style.css and assets/)
  .gitignore (optional)
  README-DEPLOY.txt

GitHub repository top level must contain: 
  package.json
  server.js
  public/index.html
  public/app.js
  public/style.css
  public/assets/ (30 image files)

Do not upload app.js/index.html/style.css/assets separately to the repository root.
Do not upload prior data/responses.jsonl or API keys.

RAILWAY
Use the repository root as the service root directory.
Start command: npm start (or node server.js)
Service Settings > Networking > Generate domain. Ensure service deployment is ACTIVE.
Test: https://YOUR-RAILWAY-DOMAIN/health
It should show: {"ok":true,"homepageExists":true,"assetsExist":true,...}
Then load https://YOUR-RAILWAY-DOMAIN/ .

SAVING RESULTS
Before sending the live link to participants, attach a Railway volume
with mount path /app/data and set variable DATA_DIR=/app/data, if
/app is the runtime's app root. Check Railway's runtime working directory.
Without persistent storage, redeployments may delete saved responses.

EMAIL (OPTIONAL)
Railway service Variables:
  RESULTS_EMAIL=kaanugurlu85@gmail.com
  RESEND_API_KEY=your_private_api_key
  EMAIL_FROM=Study <study@your-verified-domain.com>
Resend requires valid sender verification for regular use.
Never store API keys in GitHub.

ADMIN EXPORT (OPTIONAL)
  ADMIN_TOKEN=strong-random-value
GET /api/results with Authorization: Bearer <token>.

Local test: node server.js then open http://localhost:3000/
(The supplied old launcher is not included; use node directly.)
