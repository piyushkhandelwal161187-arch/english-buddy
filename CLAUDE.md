# Keesha's English Buddy — session handover / project state

Personal English-tutor PWA for Piyush's daughter Keesha (8, class 2, Indore). Wife (Hindi+English) is the parent operator. **All feature work is delegated to Codex** (`codex exec --dangerously-bypass-approvals-and-sandbox --skip-git-repo-check "<self-contained prompt>" < /dev/null`, run from THIS folder, backgrounded); Claude orchestrates, reviews, deploys.

## Live app + deploy

- **Live URL (wife's phone, installed as PWA):** https://piyushkhandelwal161187-arch.github.io/english-buddy/
- GitHub repo `english-buddy`, account `piyushkhandelwal161187-arch` (user's personal). `gh` CLI at `C:\Program Files\GitHub CLI\gh.exe` is authenticated on this laptop; git credential helper configured (`gh auth setup-git` done).
- **Deploy = commit + push from this folder** (identity: `-c user.name="Piyush Khandelwal" -c user.email="piyushkhandelwal161187-arch@users.noreply.github.com"`). GitHub Pages (legacy build, branch `master`, root) serves it ~30-60s after push.
- **🚨 EVERY deploy MUST bump the cache version in `sw.js`** (`english-buddy-vN` → vN+1) or installed phones keep the old cached app forever. Codex tasks are told to bump it; VERIFY before pushing.
- Phone update routine (tell user): close app fully → open → wait 10s → close → open. NEVER "Clear site data" (wipes API key/progress/localStorage).
- Verify deploy: `curl -s .../sw.js | grep english-buddy-vN`.

## Files

- `index.html` — the ENTIRE app (single file, vanilla JS, all inline; ~130KB). manifest.webmanifest, sw.js (cache-first, versioned), icon-192/512.png, HOW_TO_SETUP.md (bilingual guide, contains live URL).
- App calls Claude API DIRECT FROM BROWSER: `POST https://api.anthropic.com/v1/messages` headers `x-api-key`, `anthropic-version: 2023-06-01`, **`anthropic-dangerous-direct-browser-access: true`** (required for CORS). Key stored only in phone localStorage (Parents panel). Models: `claude-opus-4-8` default / `claude-haiku-4-5` economy. Never send temperature/top_p.
- CSP meta in index.html must keep `script-src 'self' 'unsafe-inline'; worker-src 'self'` (SW registration broke without 'self' — fixed once already).

## App structure (tabs)

Practice (listen/repeat/score drills, packs incl. custom + assignment-generated) · Talk to Buddy (voice chat w/ child-safe tutor persona, session timer w/ pause/finish, transcripts saved) · My Stars · Parents (PIN default 1234; bilingual; API key + test, model, recognition language en-IN/en-GB/en-US, topics, daily minutes + reset, child name/age/class settings, custom packs, **assignment photo upload** → Claude vision extracts spelling_words/read_aloud/questions → practice pack + Buddy coaching brief, image discarded, mark-done + history, **Mic diagnostics** (event log, Copy log, Mic Test)).

## Speech recognition — hard-won lessons (do NOT regress)

- `file://` on Android Chrome NEVER gets mic (that's why it's hosted). webkitSpeechRecognition lang from settings; needs internet.
- State machine wrapper (idle/starting/listening/stopping), shared by Practice/Buddy/MicTest. speechSynthesis.cancel() + ~250-500ms gap before start(). No double-start.
- Google's service often returns ZERO results for short single words (field-verified) → fixes: continuous=true + interimResults, manual stop after 1.8s silence / 12s cap, **auto-retry once on empty**, tolerant scoring.
- **v3 field bug:** accumulator concatenated per-event transcripts → massive duplication ("help help help me.... "). Fix (v4): rebuild transcript from cumulative `event.results[0..length-1]` each event, never append. 3-2-1 countdown (v3) was hated → removed in v4.
- User's phone: en-GB recognizes better than en-IN but needs close range; longer window should help.

## Version history (SW cache = deploy marker)

- v1: initial hosted PWA. v2: CSP fix (SW registration). v3: state machine, diagnostics, auto-retry, countdown (regression), continuous mode (dup bug). 
- **v4 DEPLOYED + verified live 16-Jul-2026:** fixed duplication (cumulative rebuild), removes countdown, adds **Spelling Test mode** (client-driven anti-cheat: app TTS speaks word, never displays it, child spells letter-by-letter, letter-homophone parsing bee→b etc., reveal+per-letter scoring after attempt, results in Parents, wrong words re-queued; entry: Practice card + Buddy chip when assignment/spelling pack exists). Awaiting user field-test feedback on v4 (esp. spelling-test letter recognition on the real phone).

## Pending / ideas

- User tests v4 on real phone → iterate on feedback (esp. spelling test recognition of letters).
- Sister deliverable (done): puppet-show kit in `C:\Temp\2026-07-13_keesha_puppet_show\`.
- MEMORY.md §1 (blitz_report project memory) has a pointer entry to this file — keep it in sync.
