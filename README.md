# Sketch-in-URL

> **Proof of Concept. Do not use for real work.**

A p5.js editor that stores the whole sketch in the URL, so you can share a sketch without an account or a server.

Built to explore [processing/p5.js-web-editor#4331](https://github.com/processing/p5.js-web-editor/issues/4331): students whose school district blocks account creation can't share links to their work. The issue suggests encoding the code in the URL, like [strudel.cc](https://strudel.cc) does.

## How it works

- The sketch is UTF-8 encoded, then base64url encoded, and placed in the fragment: `index.html#sketch=<encoded>`.
- The URL fragment is never sent to a server, so the code stays in the browser until someone shares the link.
- Opening a link decodes the fragment back into the editor. The sketch only runs when you press play.
- Sketches run in a sandboxed iframe with p5.js 1.11.1 from jsDelivr.

## Usage

Open `index.html` in a browser (or serve the folder with any static server). Edit the code, then copy the share URL from the bar at the top.

- **Run / Stop**: play and stop buttons, or Ctrl/Cmd+Enter
- **Auto-refresh**: re-runs the sketch as you type (desktop only)
- On mobile, the editor and canvas share one view, toggled by the play/stop button

## Limitations

- Single file only: no assets, extra files, or library choice
- Long sketches make long URLs, and some browsers, chat apps, and link shorteners truncate them
- No compression yet
- Anyone with the link can read the code

## AI Disclosure

Though most of this project's code and documentation were written or edited with the help of LLM-based tools including Claude Code and OpenAI Codex, a real human (me, @SableRaf) made all the design decisions, tested the code, and verified that everything works as described.

If you ask me a question about this project, I will use my human brain to think about the answer, and type it out with my grubby little human fingers.