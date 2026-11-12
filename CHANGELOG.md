# Changelog

What changed in each release of Railset, newest first.

## 0.2.4, 12 November 2026

- **Fixed:** after the honest feedback on your idea, Railset went straight on to your roadmap, with
  no turn to work on what the feedback found. Now it asks "Ready for your roadmap?" and waits.
  Choose "Keep working on it" to make your plan stronger with Claude first: each change to your
  vision, strategy or lean canvas is shown before it's saved, and the question comes back after
  each.
- **Changed:** every draft you approve offers "Looks right", "Keep working on it" and "Start over",
  in place of "Change one part".
- **Changed:** Market research asks one question, "How deep should I look?", with "Later" to skip
  it, and says what it looks at and what a lean canvas is before you choose.

## 0.2.3, 7 November 2026

- **New:** setup can add Railset to a project you already have. Type `railset setup`, choose "A
  project that already exists", and pick it from the projects you've opened in Claude, or drag its
  folder in. Setup adds only Railset's lines, and everything you wrote stays as it is. Claude then
  reads your project while asking you about it, and drafts your plan from both.
- **Fixed:** on a Mac already set up to use GitHub from Terminal, setup could stop at "Make a
  private copy on GitHub". It now makes the copy.

## 0.2.2, 3 November 2026

- **New:** to remove Railset, type `railset uninstall` in Terminal. It shows what goes and what
  stays before anything changes, and everything you wrote stays.

## 0.2.1, 2 November 2026

- **New:** Railset can update itself. A line above the prompt in Claude says when a newer version
  is out, and saying "update Railset" gets it. Pasting the install line again also updates Railset,
  without starting setup over.

## 0.2.0, 30 October 2026

Railset's first release, for Macs with macOS 13 or later.

- One line pasted into Terminal installs it and starts setup, which makes a folder for your idea,
  connects GitHub, makes a private repository for the idea with its first save, and opens Claude
  there.
- In Claude, Railset guides you from your idea to a plan: your vision, how to get there and your
  bets, market research with your lean canvas, and your roadmap. Then building starts, with your
  first piece of work taken through to its close.
- At the start of each session, Claude gets Railset's way of working, and a line above the prompt
  shows where your project stands.
- Claude gets Railset's six roles as skills: product manager, product design, visual design,
  architect, quality and security.
- Railset shares usage data only after your yes. `railset data-sharing` shows or changes your
  answer, and `railset problem-report` sends the Railset team a report.
