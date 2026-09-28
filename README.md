# Lifafa: Envelope Pay Prototype

A single-file web prototype to check whether the Lifafa flow works on real phones. The flow is: scan a UPI QR, check the envelope, then open GPay/PhonePe.

## What's inside `index.html`
- **Home page**, with a demo or your own envelopes
- **Envelopes:** spending, goal (with target) and locked savings
- **Scan & pay:**
  - camera QR scanning, plus "Upload QR image" and "Paste UPI link" fallbacks
  - reads the payee and the amount (if the QR has one)
  - balance check, then a confirmation screen, then **Pay with UPI app**
  - on return, "Did it go through?" deducts from the envelope only on "Yes"
- **Insufficient balance:** a popup, then pick other envelopes to cover the gap (split payment). Goal envelopes show how long the goal gets delayed; savings stay locked unless unlocked for that payment.
- **Move money** between envelopes, and **Month end** (keep leftovers, or move them to Savings)
- **UPI test lab:**
  - device checks (HTTPS, camera, QR reader)
  - a ₹1 quick test with no scan needed
  - a test-QR generator, so a teammate can scan it
  - a results log with **Copy results**

Data is saved only in the phone's browser (localStorage).

## ⚠️ Important
- **Real money moves.** Test with ₹1, paying a teammate or your own business QR.
- **It must be opened over HTTPS on the phone.** The camera doesn't work on `file://` or `http://`.

## Put it online (pick one, about 5 minutes)

**Option A: Netlify Drop (fastest)**
1. Go to https://app.netlify.com/drop (it may ask you to sign in).
2. Drag the `lifafa-qr-prototype` folder onto the page.
3. Open the `https://….netlify.app` link on your Android phone in Chrome.

**Option B: GitHub Pages**
1. Create a new public repo and upload `index.html`.
2. Go to Settings → Pages → Source: *Deploy from a branch* → `main` / root → Save.
3. After about a minute, open `https://<your-username>.github.io/<repo-name>/`.

**Option C: Vercel**
1. Put `index.html` in a GitHub repo.
2. Go to vercel.com → Add New → Project → import the repo → Deploy.

## Test plan (do this on 2–3 team phones)
1. Open the link in **Chrome on Android**, then tap **Open the UPI test lab**. Check that HTTPS, Camera and QR reader all show **Yes**.
2. **Quick link test:** enter a teammate's UPI ID and tap **Start ₹1 test payment**, then **Pay with UPI app**. Note whether the app opened with ₹1 and the payee filled in, and whether the payment went through.
3. **Scan test (personal QR):** a teammate taps **Make a test QR** on their phone. Scan it from an envelope with **Make a payment**, and pay ₹1.
4. **Scan test (merchant QR):** scan a real shop QR (or a teammate's PhonePe Business / Google Pay for Business QR) and pay ₹1. **This is the case your app depends on.**
5. If the main button doesn't work, open **Nothing opened? Try another way**. Test the GPay / PhonePe / Paytm specific options and note which ones work.
6. In the test lab, tap **Copy results** and paste them into your team chat.

## How to decide
| Result | Decision |
|---|---|
| Merchant QR payments open the UPI app with the amount filled in and succeed on most phones | ✅ Build Lifafa as planned |
| Merchant QRs work, but personal UPI IDs get blocked | ✅ Build it; demo with a merchant QR (a free business QR from a teammate) |
| The UPI app opens but blocks or declines link payments | ⚠️ Build it with the fallback: Lifafa does the envelope check, then the user pays using their UPI app's own scanner and confirms back in Lifafa |
| Nothing opens on any phone | ❌ High risk. Choose Kharcha (the tracker idea) instead |
