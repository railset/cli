# Railset

**Build better software with Claude.**

Railset guides you from your idea to software that works, step by step, the way the best teams build it. You don't need to know how to code.

An early version, being tested. The page to install from is https://railset.app.

## Install

One line, pasted into Terminal on your Mac. Setup takes it from there, in about 15 minutes.

```sh
curl -fsSL https://github.com/railset/cli/releases/latest/download/install.sh | sh
```

1. **Open Terminal.** Press Command and Space, type Terminal and press Return. It's an app your Mac already has.
2. **Paste the line.** Press Command and V, then Return.
3. **Setup takes over.** It installs a small command-line program and a Claude plugin, makes a folder for your idea, connects GitHub and opens Claude there.

If Terminal says it couldn't connect, check your connection and paste the line again.

### What to have ready

- **A Mac** with macOS 13 or newer.
- **Claude:** the Claude app and a paid Claude plan.
- **A GitHub account.** It's free, and you can make one during setup, in about 10 minutes.

## What Railset adds to Claude

- **Build what people want.** Railset helps you build the way the best software products are built. You learn from the market with battle-proven\* methods and start small, building only what solves a real problem for your users. You don't spend months on software nobody needs.
- **Your idea becomes a plan.** Tell Claude your idea the way you'd tell a friend. In about 20 minutes, before anything gets built, you have a vision and a roadmap for how to build it.
- **You work in Claude.** Railset runs in the background and knows the best practices, so you don't have to. Your code and plans stay in your own private GitHub repository, in files Claude can read with or without Railset.
- **Continuous security and quality checks.** Railset builds security and testing into the plan before any work starts. Then separate AI reviewers read each change, again and again until nothing important is left.
- **You approve the work.** You say yes to the plan before Claude starts, and you try the result yourself before it joins your product.
- **You always know what's next.** Railset shows where your project stands and recommends what to do next. When there's a decision to make, you get the options in plain words, and you choose.
- **Build several things at the same time.** Railset keeps it structured and easy to follow: every piece of work goes through the same steps, and you always see where it is.

\* Railset's approach to deciding what to build comes from Marty Cagan and the Silicon Valley Product Group (SVPG).

## What the line does

It downloads `install.sh` from this repository's latest release and runs it. The script:

- stops, changing nothing, on anything but a Mac with macOS 13 or newer, or when run with `sudo`, since Railset installs for your account alone and never needs your password;
- downloads the program over HTTPS and checks it against the release's checksum, installing nothing if they differ;
- puts it at `~/.railset/bin/railset`, one file for both Apple's chips and Intel's;
- runs `railset install`, which adds one line to your shell's settings so new Terminal windows find Railset;
- then starts `railset setup` in the same window.

## What setup does

Setup looks at what your Mac already has before it asks you anything. Then it:

- installs Apple's developer tools, which include git, if they're missing, after your yes, in Apple's own window;
- never installs Claude for you: if the Claude app is missing, it tells you where to get it;
- asks your idea folder's name, and whether to share usage data;
- asks a name and email for your saves only if git has none, and sets them for your whole Mac;
- signs you in to GitHub through Railset's own GitHub App, or helps you make a free account, and keeps the sign-in in your Mac's keychain;
- makes your idea's folder and a private GitHub repository for it, and pushes the first save;
- puts the Claude plugin in `~/.railset/plugin` and turns it on in that folder alone, in the folder's own Claude Code settings, so your other projects and your own Claude settings stay as they were;
- opens Claude in the folder.

From then on, in that folder:

- at the start of each Claude session, the plugin hands Claude Railset's way of working, which is built into the program, and shows above the prompt where your project stands;
- Claude gets Railset's six roles as skills: product manager, product design, visual design, architect, quality and security;
- git asks Railset for your GitHub sign-in on every push;
- Railset records each of its runs on your Mac, in `~/.railset`, which `railset log` reads back.

## Commands

What `railset help` prints in version 0.2.4:

```text
▗▛━━━▜▖  railset
Railset gives your coding agent a disciplined way to build software.

For you:
  railset setup                 Set up an idea, or a project that already exists
  railset github sign-in        Sign in to GitHub again when saving there stops
  railset update                Get the newest Railset
  railset uninstall             Remove Railset, keeping your work as it is
  railset data-sharing          See or change whether you share usage data
  railset problem-report [...]  Send the Railset team a problem report
  railset log                   Check that Railset is working, and see its runs
  railset --version             See which version of Railset you have
  railset help                  See this list

For your coding agent, to read Railset's way of working:
  railset pack list             List the files of Railset's way of working
  railset pack show <file>      Print one of those files

For your coding agent, to set up a project:
  railset init                  Give this project Railset's part of AGENTS.md

For your coding agent, to see what is planned:
  railset work                  List the epics planned in this project

For your coding agent, to open, check and merge a pull request:
  railset pull-request open     Open this branch's pull request: --title, --body
  railset pull-request checks   See the checks on this pull request, or main's
  railset pull-request merge    Squash-merge the pull request once checks pass

Run by Claude Code itself at the start of each session:
  railset hook session-start    Tells Claude Code that Railset is working
  railset hook show             Tells Claude Code what to show above the prompt
  railset hook marks            Tells Claude Code what to show in place of marks

Run by git itself, in a project setup made, for each push:
  railset git-credential        Hands git the GitHub sign-in for a push

Run by Railset itself, in the background, after a yes to Data sharing:
  railset send                  Sends usage data to the Railset team

Run by Railset itself, in the background, about once a day:
  railset check-for-update      Asks GitHub whether a new Railset is out

Run by the line that installs Railset:
  railset install               Readies new windows and updates the plugin
```

## What Railset shares, and how to stop it

Setup asks you first, and no answer means no. With your yes, Railset sends usage data to PostHog, in Europe, so I can find and fix problems: which steps ran on your Mac, how long they took and what, if anything, went wrong. It's sent under a random code for your Mac, and a yes includes what Railset recorded before you answered. It never includes your code, your files or their names, what you type, or your name or email. Each send shows PostHog your Mac's internet address as it arrives, and it keeps none. PostHog keeps the rest for up to seven years, unless you ask me to delete it sooner.

The full list: which command or setup step ran, when, how long it took, how it ended and the kind of failure from Railset's own list; which of Railset's files Claude read; which agent started it; which step of getting started was under way; the kind of computer and its chip; Railset's version and the short id of the save a release was built from; whether the run had a terminal, ran in CI or was a test build; a number for each run; and Railset's housekeeping, such as how far a send got. If you send a problem report, it also holds the last day of this, and the words you wrote.

To stop, type `railset data-sharing off` in Terminal, or ask Claude to. Data already sent can't be taken back from your side, so to have it deleted, send me what this line prints: `grep ^computer ~/.railset/settings.toml` to hello@railset.app
