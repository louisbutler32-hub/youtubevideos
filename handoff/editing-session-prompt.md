# Prompt for the local Claude Code editing session

Copy everything below the line into Claude Code on your computer, started inside the folder where your footage is (or the cloned repo).

---

You're helping me edit YouTube videos for my new Roblox channel. Another Claude session handles research and scripting. **Your job is editing: turning my raw recordings into finished videos and Shorts.** Work on my computer, with my files.

## Where the plan lives
My planning repo is on GitHub: `louisbutler32-hub/youtubevideos`, branch `claude/kind-gauss-cl5p1j`. If it isn't already on this computer, clone it and check out that branch. Read these first:
- `videos/003-steal-an-egg-asked-100-players/script-outline.md`: the easy-read structure of the video
- `videos/003-steal-an-egg-asked-100-players/script.md`: the full script skeleton with lines and on-screen notes
- `videos/003-steal-an-egg-asked-100-players/recording-plan.md`: what I was told to record
- `videos/003-steal-an-egg-asked-100-players/brief.md`: title, thumbnail idea, why the video exists
- `research/steal-an-egg/trick-list-for-003.md`: the tricks I tested
- `playbook/editing.md`: editing rules and checklist
- `playbook/script-writing.md`: voice rules (needed if you write any captions or on-screen text)

Don't change files in the repo's `research/`, `strategy/` or `playbook/` folders. If you finalise a script from my footage, save it as `videos/003-steal-an-egg-asked-100-players/script-final.md`.

## The channel
- Roblox videos in the style of WOLF Roblox (5M-view myth videos), but our own format. MrBeast-style: big number, a ladder that keeps getting bigger, the best thing saved for the end.
- Audience: kids roughly 9–16. Keep it family-friendly.
- I'm new to Roblox, and that's part of the story.

## The video we're editing now
**Title:** I Asked 100 Steal An Egg Players For Their Best Trick
**A/B test title:** I Asked The #1 Steal An Egg Player For His Secret
**Length:** 16–20 minutes
**Thumbnail:** my noob avatar asking "what's your best trick?", a big #1 player whispering back, a glowing egg between us. Text: "HE TOLD ME".

### Structure
| Section | Time | What's in it |
|---|---|---|
| Cold open | 0:00–0:18 | 3 clips: a trick that WORKS, a funny FAIL, a rich player showing off (cut before the result) |
| Promise | 0:18–0:30 | Me alone at spawn. "I'm new… asked 100 players… noobs first, then trillions of speed… the #1 on the leaderboard told me one that actually worked." |
| Tier 1: Noobs | players 1–30, to ~4:00 | Fast and funny. 5–10 sec per player. Ignore montages, trolls. Ends on one surprise trick that works. |
| Tier 2: Mid players | 31–70, to ~10:00 | Good tricks get mini stories (try → fail → figure out → works). A twist around 7:00. |
| Tier 3: Rich players | 71–99, to ~15:00 | Show their speed every time. Around 14:00: I combine every working trick to steal my biggest egg. |
| Finale | #100, to ~18:00 | Server-hopping to find the #1 leaderboard player, asking, testing his trick, slow-mo replay. |
| Ending | under 15 sec | Final count, my speed before vs after, "comment a trick I missed". |

Re-hook lines go at the end of each tier. They're in `script.md`.

### Things on screen the whole video
- **Top-left counter:** players asked, `0/100` → `100/100`. Ticks up every time I ask someone.
- **Top-right counter:** my speed, going up as I use tricks that work.
- **Verdict stamps** after every test: **WORKS ✅** (green), **FAKE ❌** (red), **KINDA 🤷** (yellow). Big, punchy, with a sound effect.
- **Tier title cards:** "TIER 1: NOOBS", "TIER 2: MILLIONS OF SPEED", "TIER 3: TRILLIONS", "PLAYER 100". Each tier gets different music.
- **Player chat answers** shown big and readable on screen (zoom in or recreate as a text bubble).
- **Rich players' speed numbers** zoomed in.
- **Blur all usernames**, especially the #1 player, unless I tell you otherwise.

### Editing style (from `playbook/editing.md`)
- If nothing changes on screen for about 3 seconds, something's wrong. Cut, zoom, caption, sound effect or new angle.
- Cut all dead air, loading screens and walking (unless it's funny). Cut harder than feels natural.
- Punch-in zooms (110–130%) on reactions and results.
- Sound effects on cuts, stamps and fails, but quiet.
- Music under voice at about -20 to -25 dB. Voice always loudest. **Only copyright-free music** (YouTube Audio Library / Pixabay).
- First frame is action. No logo, no "hey guys".
- Ending under 10–15 seconds after the last payoff.
- Export 1080p (or 1440p), 60fps, H.264, high bitrate.
- Check the final mix on phone speakers.

### Rules
- **Never show WiFi-off / duping / script / auto-clicker tricks being done.** If a player suggests one, keep me saying "nah, that's how you get banned" and cut away.
- No personal info on screen.
- **Never delete or overwrite my original recordings.** Work on copies or with references. Ask before deleting anything.
- If the #1 player's trick flopped, don't fake it. Use the backup ending in `script.md`.

## Shorts (after the main video)
Cut 3–5 Shorts from the best single tricks:
- 9:16 vertical, cropped on the action, captions on everything
- Start on the claim ("This kid told me…"), end right after the verdict. 20–45 seconds.
- Last line/caption: "I asked 99 more. Full video on my channel."

## How I'd like you to work
1. **Check my setup first.** See what's installed (ffmpeg, Python, Whisper or faster-whisper, Node, DaVinci Resolve / CapCut) and tell me what's missing before installing anything. Ask me which editor I want to finish in.
2. **Set up a project folder:**
   ```
   003-edit/
     raw/        (my original recordings, read-only)
     proxies/    (smaller copies if needed for speed)
     audio/      (extracted voice tracks)
     transcripts/
     selects/    (clips we're using)
     assets/     (stamps, counters, music, sfx)
     exports/
   ```
3. **Log the footage.** Transcribe my mic audio with timestamps, then build `footage-log.md` with one row per player: `player # | file | timestamp | their speed | trick | WORKS/FAKE/KINDA | funny moment?` My own notes file (if I give you one) comes first. Use the transcript to fill gaps.
4. **Pick the selects.** Propose the 3 cold-open clips, the ~7:00 twist, the 14:00 big moment and the finale, with timestamps. Wait for my OK.
5. **Rough cut.** Assemble in ladder order with ffmpeg (or as a timeline/EDL/FCPXML I can open in my editor). Tighten every pause.
6. **Overlays.** Build the counters, stamps and tier cards as reusable assets (PNG/MOV with alpha, or Remotion components if I want everything done in code).
7. **Voiceover gaps.** Where explanation is missing, write short VO lines in my voice (rules in `playbook/script-writing.md`: short sentences, no AI phrases). I'll record them.
8. **Final pass** using the checklist in `playbook/editing.md`, then exports.
9. **Shorts.**

Explain what you're doing in plain language. I'm new to editing. When there's a choice (e.g. finish in DaVinci vs fully automated), recommend one and tell me why.

Start with step 1.
