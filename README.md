# Tab Out

**Keep tabs on your tabs.**

[English](README.md) · [简体中文](README_CN.md)

Tab Out is a Chrome extension that replaces your new tab page with a dashboard of everything you have open. Tabs are grouped by domain (or by Chrome tab group), with homepages (Gmail, X, LinkedIn, etc.) pulled into their own card. Close tabs with a satisfying swoosh + confetti.

No server. No account. No external API calls. Just a Chrome extension.

> This is a feature-extended fork of [zarazhangrui/tab-out](https://github.com/zarazhangrui/tab-out) with bento layout, dark mode, search, Quick Access, Bing daily background, Chrome tab group view and more.

---

## Install with a coding agent

Send your coding agent (Claude Code, Codex, etc.) this repo and say **"install this"**:

```
https://github.com/arbing/tab-out
```

The agent will walk you through it. Takes about 1 minute.

---

## Features

### Tab management
- **See all your tabs at a glance** on a clean bento grid
- **Two grouping modes** switch between domain view and Chrome tab group view with one click
- **Homepages card** pulls Gmail inbox, X home, YouTube, LinkedIn, GitHub homepages into one place
- **Custom groups** define your own grouping rules for the domains you care about
- **Duplicate detection** flags when you have the same page open twice, with one-click cleanup
- **Click any tab to jump to it** across windows, no new tab opened
- **Localhost grouping** shows port numbers next to each tab so you can tell your local projects apart
- **Expandable groups** show the first N tabs with a clickable "+N more"
- **Protected tabs** pinned tabs and standalone-window tabs get a badge + dedicated close button so they don't get swept up by "Close all"

### Productivity
- **Search bar** filter open tabs by title or URL, with `/` shortcut to focus
- **Quick Access card** curate your favorite shortcuts at the top of the page
- **Bookmarks integration** browse your Chrome bookmarks alongside open tabs
- **Save for later** bookmark tabs to a checklist before closing them, archive view included

### Look & feel
- **Bento layout** flexible card-based grid that adapts to your tabs
- **Dark mode** theme toggle with auto persistence
- **Bing daily background** optional Bing image-of-the-day backdrop with credit
- **Close tabs with style** swoosh sound + confetti burst
- **Unified card styles** Not Grouped, Saved for Later and Bookmarks share a consistent look

### Privacy
- **100% local** your data never leaves your machine
- **Pure Chrome extension** no server, no Node.js, no npm, no setup beyond loading the extension

---

## Manual Setup

**1. Clone the repo**

```bash
git clone https://github.com/arbing/tab-out.git
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder inside the cloned repo and select it

**3. Open a new tab**

You'll see Tab Out.

---

## How it works

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain (or Chrome tab group)
  -> Quick Access shortcuts and Homepages sit at the top
  -> Click any tab title to jump to it
  -> Close groups you're done with (swoosh + confetti)
  -> Save tabs for later, or filter the grid with the search bar
```

Everything runs inside the Chrome extension. No external server, no API calls, no data sent anywhere. Saved tabs and personal config are stored in `chrome.storage.local`. The optional Bing background fetches only from `bing.com` (declared in `host_permissions`).

---

## Tech stack

| What             | How                                                                 |
|------------------|---------------------------------------------------------------------|
| Extension        | Chrome Manifest V3                                                  |
| Permissions      | `tabs`, `activeTab`, `storage`, `bookmarks`, `favicon`, `tabGroups` |
| Storage          | `chrome.storage.local`                                              |
| Sound            | Web Audio API (synthesized, no files)                               |
| Animations       | CSS transitions + JS confetti particles                             |
| Background image | Bing image-of-the-day (optional)                                    |

---

## License

MIT

---

Originally built by [Zara](https://x.com/zarazhangrui) · Extended fork maintained by [ArBing](https://github.com/arbing)
