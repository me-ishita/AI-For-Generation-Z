# Connect form submissions to Google Sheets

The form and the Apps Script handler are ready. The handler writes each submission to the first tab of the linked spreadsheet, creating a `Submissions` tab if needed. It adds the column headings when the selected tab is empty.

## One-time setup

1. Open the linked Google Sheet and choose **Extensions → Apps Script**.
2. Replace the editor contents with `google-apps-script/Code.gs` and save.
3. Choose **Deploy → New deployment → Web app**.
4. Set **Execute as** to your account and **Who has access** to **Anyone**, then deploy and authorize the script.
5. Copy the Web app URL ending in `/exec` into `.env.local` as `VITE_GOOGLE_SCRIPT_URL=https://script.google.com/macros/s/.../exec`.
6. Restart the local site or rebuild/redeploy it so the environment value is included.

The public web-app URL accepts form submissions and can append rows to the spreadsheet as the deploying account. It does not expose a read endpoint. Share that URL only with the brochure site; if you no longer need form submissions, disable or delete the Apps Script deployment.
