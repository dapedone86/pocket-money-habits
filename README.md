# Pocket Money & Habits

A pocket money, chores and habits app for one child on one Android phone. It is a single self contained `index.html` that installs as a progressive web app from any HTTPS host.

## What it does

**Jobs.** The child taps a chore to claim it. A parent approves or rejects it behind a PIN.

**Money.** One balance that earns monthly interest set by the parent. Up to 3 goals (name, price, icon) hold part of it. The rest is free to spend. A small overdraft (default $15) is allowed only when nothing is in a goal.

**Habits.** Daily routines (morning and night) and weekly routines on chosen days, with streaks.

**Parent.** PIN protected approvals, adding money, editing chores and habits, interest rate, backup and restore.

## Design rules

1. All money is stored as integer cents.
2. The ledger is append only. Balances are always derived from transactions, never stored.
3. All day boundaries use Australia/Adelaide time.
4. Habit ticks are stored per date and streaks are computed from history.
5. A `migrate()` step upgrades older saved data without loss.
6. Data lives in the browser's local storage for the address it is served from. Use **Parent → Backup** regularly.

## Install on a phone

1. Host `index.html` on any static HTTPS host (GitHub Pages, Netlify, Cloudflare Pages).
2. Open the address in Chrome on the phone.
3. Chrome menu → **Add to home screen**.
4. Set the parent PIN on first launch. It cannot be recovered.

## Versions

| Tag | Notes |
|---|---|
| `v1.0` | Revision one, as running on the phone from August 2026 |
| `v2.0` | In progress: money bar fix, clearer habit days, weekly habit rewards |

## Privacy

Never commit backup files. They contain the child's name, the full money history and the PIN hash. `.gitignore` blocks the usual backup file names.
