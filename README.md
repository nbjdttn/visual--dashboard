# Money Snapshot

A private money dashboard for your iPhone. It shows all your pots in one place, projects them month by month, and tells you what to do next. It runs as a web app you add to your Home Screen.

**Your figures never live here.** This repository only holds the empty app. Your balances are stored inside the app on your phone, and the app's security policy stops it sending data to any other website. The one exception is Anthropic, and only when you use the optional assistant. Never upload your starting file or a backup (`*.json`) to this repository. The `.gitignore` file blocks the usual names, but please don't rely on it.

## What it does

- **Home**: your total, an estimate for today (interest and growth since your last update), a chart of the next 12 months, how your money is split (by type or by provider), anything that needs attention and what's coming up.
- **Forecast, month by month**: every pot projected for 1, 2, 3 or 5 years. Slide your finger along the chart to see the total and the mix for any month. It also shows when each fixed saver or gilt unlocks and what it will be worth.
- **Forecast, to retirement**: the long-term picture in today's money, with low, central and high cases.
- **Pots** and **Monthly**: your accounts, this month's money moves to tick off, interest and your ISA allowance.
- **Tax**: the tax on your savings interest for this tax year and next, where the interest comes from, and ways to pay less. Add your taxable pay once and it works out your band, your Personal Savings Allowance and the tax. Gilts count only their coupons, which the app reads from a gilt's name or notes (such as "0⅜% Treasury Gilt 2030"). It uses the rules for England, Wales and Northern Ireland, with savings tax at 24%, 44% and 49% from 6 April 2027. It's an estimate, not tax advice.
- **Share with family**: a full report in Chinese and English, as a long picture (good for WeChat), a PDF or text, from the share button on Home or from **More**. It covers every account, the next three years, what matures and where the money goes, savings plans, tax, the long-term outlook and a plain explanation of each kind of account. Never account numbers.
- **Assistant** (optional): ask Claude about your money, or give it screenshots from your banking apps and it reads the balances for you. Nothing changes until you tap **Apply**. It needs your own Anthropic API key (see below).
- **Face ID and passcode** (optional): the app locks when it opens and after time away. Face ID unlocks it, and a 6-digit passcode does if Face ID doesn't work.
- **Appearance**: Paper by default, with Evergreen, Midnight and Aurora under **More**.

## Switch on the website (once)

1. In this repository on GitHub, open **Settings**, then **Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose branch **main** and folder **/ (root)**, then **Save**.
4. After a minute or two the app is at **https://nbjdttn.github.io/visual--dashboard/**

## Put it on your iPhone

1. Open that address in **Safari**.
2. Tap **Share**, then **Add to Home Screen**.
3. Always open it from the Home Screen icon. Figures entered in an ordinary Safari tab are kept separately.
4. Save your starting file to Files or iCloud Drive, open the app and tap **Import my starting file**.

## Each month (about two minutes)

- Tap **Update balances**. Either type the figures in, or paste them: take a screenshot in each banking app, open it in Photos, tap the Live Text button, then **Copy All**, and paste into the box at the top. The app finds the £ amounts, fills in the pots it recognises and asks once about the rest. It remembers your answers next time. If you've set up the assistant, you can tap **Let Claude read the screenshots** instead.
- Tick off the month's money moves on **Monthly**.
- Every month or two, go to **More**, then **Back up to a file**, and save it to iCloud Drive. That backup is how you restore everything on a new phone.

## Face ID and passcode (optional)

1. Go to **More**, then **Face ID and passcode**, then **Turn on Face ID**.
2. Choose a 6-digit passcode and enter it twice. It's for when Face ID doesn't work, so don't use your bank card PIN.
3. Tap **Turn on Face ID**. Your iPhone offers to save a passkey for the app: that's how Face ID works for web apps. Allow it.

- **Opening the app**: Face ID starts by itself. If it doesn't recognise you, can't run, or you cancel it, type your passcode on the keypad. Tap the face on the keypad to try Face ID again.
- **When it locks**: when the app opens, and when you come back after a minute away. Change this under **Ask for it**, or tap **Lock now**.
- **If you forget the passcode**: tap **Forgot passcode?**. With Face ID, you can choose a new passcode. Without it, the only way in is to delete the figures on this phone and restore your backup file.
- **What it protects**: it stops anyone who picks up your phone from opening Money Snapshot. Only a scrambled (hashed) version of the passcode is stored. The passcode, Face ID and your API key aren't in backups, so on a new phone you set them up again.

## The assistant (optional)

1. Create an API key in the Claude Console at **platform.claude.com**, under **API keys**. Add some credit there; you can also set a monthly spending limit.
2. In the app, go to **More**, then **Assistant**, then **Add your API key**, and paste it. Paste it only into the app, never into a chat, email or file.
3. Tap the sparkle button on Home. Ask a question, or attach screenshots and say "update my balances".

- **What's sent, and when**: nothing until you send a message. Then your question, the app's figures and any screenshots go to Anthropic, and nowhere else.
- **Your key** stays on this phone. It's stored apart from your figures, so it's never in a backup or a family report. **Remove the key from this phone** (under **More**, then **Assistant**) deletes it. If you think someone has seen it, delete it in the Claude Console too.
- **Nothing changes by itself**: Claude can read your figures, forecast and tax estimate. Anything it wants to change (a balance, a rate, a new pot or a setting) appears as a card, and only **Apply** saves it.
- **Cost**: Anthropic charges your account for what you use. Most questions cost a few pence, a little more with screenshots, and the chat shows a running estimate. Claude Opus 5.5 is the default. Sonnet 5.5 and Haiku 5.5 are cheaper and are under **Key and model**; changing model starts a new chat.

## How the month-by-month forecast works

- Each pot grows at its own rate: interest for savings, the average prize rate for Premium Bonds and the expected return for shares and pensions. Figures are before tax and in today's money: future sums are shrunk by inflation, 2.5% a year unless you change it in **Settings**, under **Inflation**. Tax figures stay in actual pounds.
- When a pot matures, the money goes where you choose on that pot (**When it matures, the money goes to**), otherwise to your best easy-access saver.
- The forecast follows your plan for investing (for example 70% in investments and pensions by 30 April 2029). Each month, money in your main saver above your emergency cushion (your months of fixed costs) goes into your investment pot as needed to stay on that path, so most maturing money ends up invested. Add a **Shares and funds** pot without the tax-free tick if you invest outside your ISA, and the forecast will use that one.
- Monthly moves count when you set **From** and **To** on them. Your pay counts as **My pay or other new money**.
- Extra pension from pay goes into your pension pot, following the amounts in Settings.
- If a bonus rate ends, set **Bonus or offer rate ends on** and **Rate after the offer ends** on that pot.

## A new icon

iPhone keeps the icon it had when you added the app to your Home Screen. To get a new one, first go to **More**, then **Back up**, and save the file. Then remove the app from your Home Screen, add it again from Safari, open it and tap **Import my starting file**, then choose your backup. Removing it also removes the figures stored inside it, which is why the backup comes first. Your passcode, Face ID and API key aren't in the backup, so set them up again afterwards.

## Why it doesn't connect to your bank

Automatic bank feeds in the UK use Open Banking. That needs a regulated company and a server that holds access to your accounts, so your figures would leave your phone. Open Banking also doesn't cover gilts, investment ISAs, Premium Bonds or pensions, which is most of a typical portfolio. Instead, the app estimates your balances automatically each day from your rates and plans, and you correct them with real figures once a month.

## Updating the app

The whole app is `index.html`, plus `sw.js` (which lets it work offline), the icons and `manifest.webmanifest`. When a new version is pushed to `main`, your phone picks it up the next time you open the app with a connection. Your figures are not affected.
