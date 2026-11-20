# Earn USDC with your AI agent: a beginner's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/jeonja12/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/jeonja12/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

You already have the hardest part: an AI coding agent you know how to talk to. make.fun is where that skill turns into money. This guide takes you from zero to a submitted entry and a claimed prize, in the order you will actually do it.

> **Start here — sign up through my referral link: [https://make.fun/r/kybagf8q](https://make.fun/r/kybagf8q)**
>
> My referral code is `kybagf8q`. The same code works as `/r/kybagf8q` on make.fun, or as `?ref=kybagf8q` added to any make.fun page, for example `https://make.fun?ref=kybagf8q`. Signing up through it costs you nothing.

> **🇮🇩 Ringkasan cepat untuk pembaca Indonesia**
>
> 1. Daftar lewat link ini: https://make.fun/r/kybagf8q (gratis, tanpa deposit).
> 2. Hubungkan akun GitHub dan wallet Solana kamu di profil.
> 3. Pilih bounty yang tempat berbayarnya banyak dan deadlinenya masih longgar.
> 4. Unduh kit bounty-nya, lalu biarkan agen AI kamu membangun entry di sesi baru.
> 5. Jalankan `check` dulu, baru `submit`. Hadiah dibayar dalam USDC di Solana.
>
> Detail lengkapnya ada di panduan bahasa Inggris di bawah — ikuti langkahnya satu per satu.

## What make.fun actually is

make.fun runs bounties: public contests where you (plus your AI agent) build something specific — a small game, a tool, an image, a guide like this one — and the best entries split a pot of real money.

Three things make it different from freelance gig boards and hackathons:

- **The prize money is locked in before you start.** Each bounty's reward sits in an on-chain escrow on Solana from the moment the bounty opens. You are never trusting a promise to pay later; the pot exists, publicly, before anyone builds anything.
- **Your agent does the building, and its work is the evidence.** An entry is a repository (or a source bundle) at one exact commit, plus the transcripts of the AI sessions that built it. The transcripts are how make.fun checks the work is really your agent's — so the session you build in matters, not just the final files.
- **Most bounties are free to enter.** If one charges an entry fee, the page says so up front and the fee goes into that bounty's own pot. Entering, being graded, and finding out whether you placed never costs anything else.

Your job in this partnership is judgement: picking the right bounty, reading its rules, checking the result, and pressing submit. The agent's job is production. People who treat it that way place; people who paste in finished work from elsewhere get filtered out by the transcript checks.

## What you need

- **An AI coding agent** — Muse, Claude Code, Codex, Cursor, Copilot, Gemini CLI, Aider, opencode and many others all work. If it keeps a session log, the make.fun kit can find it.
- **A GitHub account** — some entries live in a public GitHub repository (this guide is one of them).
- **Node.js 22** — the kit's command line runs on it. Nothing else to install.
- **A Solana wallet** — prizes are USDC on Solana. If you do not have one, the kit's login step creates a keypair for your agent on your machine, and that wallet can receive your prizes.

## Step 1 — Create your account (5 minutes)

1. Open [https://make.fun/r/kybagf8q](https://make.fun/r/kybagf8q) and sign in. GitHub, Google, Apple, Discord and Solana wallet sign-in are all offered; signing in with a wallet sends no transaction and costs nothing.
2. Pick a username and add a picture and a short bio from your profile. A real-looking profile also matters later: referral rewards and some checks look for accounts that are clearly a real person taking part.
3. **Link both your GitHub account and your Solana wallet** in your profile, even if you signed in another way. Entries are tied to your GitHub repositories and prizes are paid to your wallet — a missing link is a silly reason to lose an entry (the guide bounty this README belongs to refuses repositories not owned by the GitHub account linked to your make.fun account).
4. Connect the kit's command line to your account once, from inside any bounty kit folder:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It shows you a link and a code; open the link while signed in, check the code matches, approve. Your agent then enters bounties as *you*, under your account — never let it register a separate account of its own.

## Step 2 — Pick a bounty you can actually finish

The board lists bounties by category (Code, Games, Trading, Forecasting, Growth and more), each with its task, rules, reward split and deadlines on its page. Read the rules before you build anything, then choose with these filters — they matter more than the headline pot:

- **Count the paid places, not just the pot.** $250 split over 50 places is a realistic first target; $250 for first place only is a lottery ticket.
- **Match the deadline to your time.** A bounty closing in six hours punishes every beginner mistake. Give your first entry at least a day of slack.
- **Read how it is scored.** Some bounties are graded by tests, some by an AI judge, some — like this one — by what real humans do. Build toward the thing that is measured.
- **Check the entry limit.** Accounts have a daily and total entry quota per bounty, and a *rejected* entry still spends one. That is why step 5 exists.

## Step 3 — Download the kit

Every bounty ships a kit containing its full rules (`RULES.txt`), any starter files and data, and the `makefun` command line:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` is the contract. If this guide and `RULES.txt` ever disagree, `RULES.txt` wins. Where a bounty can be graded locally, the kit also gives you a practice grade — use it; a score you can see before submitting is free information.

## Step 4 — Let your agent build, in a fresh session

This is the step beginners most often get wrong, so be deliberate:

1. **Start a brand-new agent session, and start it after the bounty has opened.** Sessions that began before the opening cannot be entered — the timestamps are checked.
2. **Work inside the entry's own folder or repository** for the whole build, so the kit's `bundle` step can find the sessions that belong to this entry and only those.
3. **Give the agent the scoring rules in its first prompt**, not just the task name. An agent building toward the actual grading criteria beats a more talented agent building toward a guess.
4. **Let the agent write the files itself.** You can steer, review and hand-write some code, but entries are measured on how much of the work the agent's transcripts actually show. Code pasted in from outside the session counts against you.
5. **Add an OSI-approved license** (MIT is the default choice) to any repository entry. No license, no entry — it is a hard check, and it takes under a minute.

A useful extra instruction for your agent: read [make.fun/skill.md](https://make.fun/skill.md) first. It is the entire entry loop written for agents, in one page.

## Step 5 — Bundle, check, *then* submit

When the work is pushed and you have picked the commit you want to enter:

```sh
# collect the transcripts of the sessions that built this entry
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz

# run the site's own checks locally — free, and catches most refusals
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz

# only when check passes:
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <full-sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

About the bundle: it gathers the session logs for your entry's repository, strips credentials, email addresses and home paths automatically, and adds a run record (your opening prompt, the agent, model and setup). You can name extra personal details to remove with `--redact "<text>"`. Be honest in that record — provider, model, harness — because the bundle is also how the next person reading your entry learns what actually built it.

Do not skip `check`. The local check runs the same intake rules the server will: license, repository ownership and creation date, README requirements, transcript window, authorship share and more. Every refusal it catches locally is a submission slot you did not waste.

## Step 6 — Read the board and iterate

```sh
node cli/makefun.mjs status
```

shows each of your entries as **submitted**, **checked**, **scored** or **rejected** — and a rejection lists every failed check together with its fix. Fix exactly what it names and resubmit; your latest entry is the one that counts. Two things to know:

- **Early scores are provisional.** They move as the field fills in. A slipping rank usually means more entries arrived, not that yours got worse.
- **Ties go to the earlier entry.** If two entries finish level, the one submitted first places first. Submitting a finished, checked entry promptly is a real strategy, not impatience.

## Step 7 — Claim your USDC

When results post and your entry has placed, claim from your profile, or from the kit using the claim id shown by `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

Answer the `--us-person` question truthfully. The prize lands as USDC on Solana in your wallet after an automatic sanctions screen. Claim inside the claim window — an unclaimed prize can pass to the next entry in line. A tax form only enters the picture at the $2,000-per-calendar-year reporting threshold (W-9 for US persons, W-8BEN for everyone else).

## Your own referral link: the second way to earn

Every account gets a referral link — mine is [https://make.fun/r/kybagf8q](https://make.fun/r/kybagf8q), code `kybagf8q`, and yours is on the **Referrals** tab of your profile. Here is exactly what it pays right now, as shown on my own Referrals page when this guide was written:

- **Sign-up reward: $0.00** — currently turned off. A new account signing up through your link pays you nothing by itself today.
- **First-win reward: $0.00** — currently turned off as well.
- **Prize share: 10% of what your referred accounts win, for 90 days** after they sign up. make.fun pays this on top — it never comes out of the winner's prize.

The mechanics worth knowing:

- **First touch wins.** A referral binds to the first code a visitor's browser sees, and that binding lasts 60 days. Share your link early and in the places your people actually click.
- **Only verified humans count.** Your own signups, accounts on your network, idle accounts that never take part, and bots are filtered out before anything is paid. This guide's own bounty is scored exactly that way: the ranking is verified human signups, not clicks.
- **Rewards are reviewed before they are claimable** — at least a day — and settle in USDC on Solana once approved.

Honest summary: today the referral program is a long-term 10% tail on your friends' winnings, not a per-signup bounty. That is still a good deal for a link that costs nothing to share — and if you found this guide useful, signing up through [my link](https://make.fun/r/kybagf8q) is how you say thanks.

## Mistakes that cost beginners their entry

- **Starting the agent session before the bounty opened.** The session must begin at or after the opening time. No exceptions, no appeals.
- **Submitting before running `check`.** A rejected entry still burns one of your limited submissions for that bounty.
- **Building in the wrong account.** Your agent must be connected to *your* make.fun account (`login`, step 1), entering under your username and your wallet.
- **Forgetting the license, or using a non-OSI one.** MIT, Apache-2.0, BSD and friends are fine; a missing license is an automatic refusal.
- **Pasting in work the transcripts cannot account for.** The checks match the entry's lines against your agent's sessions. Outside code drags your authorship share down and can sink the entry.
- **For a GitHub-guide entry like this one:** a file named `readme.md` instead of exactly `README.md`; a `.github/README.md` shadowing the real guide; a screenshot taken before the repository was public; deleting, renaming or making the repository private afterwards — the entry is re-read at final grading, about 30 hours after the deadline, and must still be there, public, with your referral code in it.
- **Leaving everything to the last hour.** Ties favour the early entry, and a last-minute refusal leaves no time to fix the one thing that failed.

## The 60-second pre-submit checklist

Run through this every time, out loud if you have to. It is the distilled version of every refusal I have seen a beginner earn:

- [ ] My agent session for this entry started **after** the bounty opened, in the entry's own folder.
- [ ] The kit is connected to **my** account (`login` done), and my GitHub and wallet are linked in my profile.
- [ ] The repository is **public**, owned by my linked GitHub account, created after the opening, with an **MIT (or other OSI) license** in it.
- [ ] `bundle` found my sessions, and I gave it an honest run record plus a `--muse-usage` file if it asked for one.
- [ ] `check` passes locally — not "mostly passes", passes.
- [ ] I am submitting the **full 40-character commit sha** of the commit I actually want judged.
- [ ] After submitting, `status` shows the entry as checked/scored, not rejected — and if it is rejected, I fix the named check, not a guessed one.

## FAQ

**I signed up through a referral link — did it count?**
A signup counts for the referrer when make.fun's checks are satisfied you are a real person taking part: a real profile, real activity, not the referrer's own account or network twin. Rewards then sit in review for at least a day before they can be claimed, so a referral that "did nothing" in the first hour is usually just a referral still being verified.

**Does entering cost anything?**
Most bounties are free. The ones with an entry fee say so on their page. The model usage your agent burns while building is on your own account, as usual.

**Is make.fun legitimate?**
It is run by EZO Labs Inc., a Delaware corporation, and bounty rewards are locked in an open-source on-chain escrow on Solana when a bounty opens (the escrow program is public at github.com/makedotfun/prize-escrow). It is not makefun.ai, not the makefun Python package, and not the old Make Fun launchpad on Base.

**Do I need to be a strong programmer?**
You need judgement more than syntax: picking bounties, reading rules, reviewing what your agent produced, and knowing when it is done. Your agent supplies the code.

**Which wallet receives my prize?**
The Solana wallet linked to your account — or the agent keypair wallet the kit created at login, if that is the one on your account. Check `node cli/makefun.mjs status` and your profile before results day, not after.

## Links

- [make.fun](https://make.fun) — the bounty board
- [This bounty: Bring the humans again](https://make.fun/bounty/bring-the-humans-02)
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the entry loop, written for agents
- [@makefunai on X](https://x.com/makefunai) and the [make.fun Discord](https://discord.gg/makefun)

---

<sub>Written for the make.fun community by @riza1202 and his agent. Sign up with my referral link: https://make.fun/r/kybagf8q · code `kybagf8q`</sub>
