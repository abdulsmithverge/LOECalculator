# Verge LOE & Margin Calculator

An internal tool for scoping new business engagements — estimating level of effort, Verge costs, billing targets, and net profit margin across multiple roles.

---

## What it does

The calculator lets you build out a full engagement estimate with multiple roles, each with their own hours, rate type, and resource assigned. It calculates hours per week, hours per month, and Verge costs per role automatically, and rolls everything up to an engagement-level margin and net profit based on a single billing amount.

A built-in margin reference key shows the billing amount needed to hit 40%, 45%, and 50% margin based on your actual costs — removing the guesswork when setting a number.

Estimates are saved to a shared JSON file in this repo, so every team member sees the same data in real time. The dashboard provides a searchable, sortable view of all saved estimates with expandable per-role breakdowns.

---

## Pages

| Page | URL |
|---|---|
| Calculator | `https://abdulsmithverge.github.io/LOECalculator/index.html` |
| Dashboard | `https://abdulsmithverge.github.io/LOECalculator/dashboard.html` |

---

## First-time setup (each team member)

### Step 1 — Create a GitHub account
Go to [github.com/signup](https://github.com/signup) and create a free personal account if you don't already have one.

### Step 2 — Accept the repo invitation
Abdul will send you an invite to this repo. Check your email and accept it before proceeding — your token won't work until you have access.

### Step 3 — Generate a Personal Access Token (PAT)
1. Go to [github.com/settings/tokens/new](https://github.com/settings/tokens/new)
2. Give it a name like `Verge LOE & Margin Calculator`
3. Set expiration to **No expiration**
4. Check the **repo** scope (top-level checkbox)
5. Click **Generate token**
6. Copy it immediately — GitHub only shows it once
7. **Save it somewhere safe** — paste it into your notes app (locked), a password manager, or anywhere you can retrieve it later. You'll need it if you ever set up the tool on a new device. If you lose it, you'll need to generate a new one.

### Step 4 — Connect the tool
1. Open the calculator URL above
2. When the setup panel appears, fill in:
   - **Token** — the one you just copied
   - **Repo owner** — `abdulsmithverge`
   - **Repo name** — `LOECalculator`
   - **Path to data file** — `estimator/estimates.json`
   - **Your name** — how you want to appear on saved estimates
3. Click **Save & connect**

That's it. You won't be asked again on that device.

### Repeat on additional devices
Each device (laptop, phone, tablet) needs its own one-time setup. Use the same token you saved in Step 3 — just open the tool URL on the new device and fill in the setup panel with the same details. This is why saving your token somewhere safe matters; it means you only ever generate one and reuse it across all your devices.

---

## Browser note

The tool uses Google Fonts (Poppins) for typography. If your browser has an aggressive tracker or privacy blocker extension, it may block the font and affect how the tool renders. If the tool looks unstyled:

- Try opening it in an incognito/private window to confirm the issue
- In your privacy extension, whitelist `abdulsmithverge.github.io` to allow Google Fonts to load

---

## How estimates are stored

Estimates are saved as a JSON file at `estimator/estimates.json` in this repo. Every save writes directly to that file via the GitHub API. Since the file is git-tracked, you get a full commit history of every change as a free audit trail — visible in the repo under **commits**.

Data is portable — if we ever migrate to another tool, the JSON can be exported or converted to CSV at any time.

---

## Role types

Each role in an estimate supports two rate structures:

- **Hourly** — total hours × hourly rate paid = Verge costs
- **Fixed monthly fee** — monthly fee × total engagement months = Verge costs

Hours per week and hours per month auto-calculate for both types and are used for contractor capacity planning.

---

## Margin reference key

The margin reference key appears in the Billing & margin section once role costs are entered. It shows the billing amount needed to achieve:

| Target | Description |
|---|---|
| 40% | Margin Floor |
| 45% | Margin Target |
| 50% | Margin Target for Complex Engagements |

Formula: `billing = total costs ÷ (1 − target margin)`

---

## Repo structure

```
LOECalculator/
├── index.html          # Margin calculator
├── dashboard.html      # Estimates dashboard
└── estimator/
    └── estimates.json  # Shared estimates data
```

---

## Need help?

Come back to the Claude conversation where this tool was built — the full history is there and any changes, additions, or fixes can be made quickly.
