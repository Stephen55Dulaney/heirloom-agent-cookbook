# Recipe: A Short From a Raw Clip

### Everything but the Publish button, and nothing leaves the machine until you say so

A Short is where most people will meet you, and it's fed by cadence. A channel we measured did almost
all of its views in the weeks it posted and almost none in the weeks it didn't. The bottleneck was never
the filming. It was the forty small chores between a raw clip and a posted one. This recipe does those
chores and stops one step short of public.

---

## What you're building

Two stages with a wall between them.

**Stage 1, prep (touches no outside service):** a folder containing the graded, captioned, vertical video;
a thumbnail; a title and description; tags; a caption file; a privacy report; and a manifest that says
*private, do not publish*.

**Stage 2, upload:** the bundle goes up as a **private draft**, every field filled from the manifest, and
the process stops. A person looks at it and makes it public.

A private draft can be deleted. A public post can't be taken back. That asymmetry is the design.

---

## The contract

Given one raw vertical take, Stage 1 MUST:

1. **Optionally make a rough cut from the transcript** (off by default): a local speech-to-text model gives
   word timings; dead air, filler words, and literal restarts are marked in an edit list; the kept pieces
   are joined in one frame-accurate step so sound and picture stay in sync. The edit list is written down
   and **always reviewed**: it's the audit trail for every cut, not a clearance.
2. **Level the sound** to a standard loudness, and normalize the picture to vertical.
3. **Burn in captions** from a caption file. The best source is the person's own script, which spells
   names right; next best is local speech-to-text with names corrected. Say so plainly when there's
   neither.
4. **Run a privacy pre-scan.** Pull frames and *look* at them for readable private text: a person's name,
   a health term, an address, a key. It raises flags; it doesn't clear anything. The human owns the final
   look.
5. **Write the manifest locked to private.** Name the video file after the title (the filename is a signal
   to the platform too).

Stage 2 MUST: upload only when the human asked for it in this session (never from a schedule or a message
someone else sent), fill every field from the manifest, and **stop** at the first unexpected screen
(a login wall, a verification prompt, a flagged check).

It MUST NEVER set the video public, unlisted, or scheduled, never press Publish, and never sign in on the
person's behalf.

---

## How you know it worked

- [ ] **Captions spell the names right**, on the frames where a name is spoken.
- [ ] **The rough cut kept the meaning.** Read the edit list: nothing marked "filler" was a real word.
- [ ] **The privacy report lists what it saw**, including "nothing flagged" when that's the result.
- [ ] **The upload is private, verified two ways:** the visibility shown in the platform's own list of
      videos, *and* an anonymous request for the video being refused.
- [ ] **No false success.** A green "upload complete" notice isn't proof. Read the video's state back.

| Measure | Minimum | Target |
|---|---|---|
| Minutes of human work per Short | < 15 | < 5 |
| Words wrongly cut by the rough cut | 0 in review | 0 |
| Private-text flags missed (found later by the human) | 0 | 0 |

---

## Known hard parts (the scars)

**1. "Filler" words that weren't.** "Like" is too often a real word; it isn't in the default filler list.
Restarts are only cut when the repeated wording is nearly identical. A different wording of a fresh start
is left alone on purpose, so a good take never gets butchered.

**2. Caption placement numbers mean something other than what they look like.** One subtitle renderer
reads alignment codes in an old format: the value that looks like "top" put the captions in the *middle*
of the frame, on the speaker's forehead. Test the placement on a real frame.

**3. The success notice lied.** An upload notice said done while the video's visibility wasn't what we
asked for. Verify by reading the page and asking the platform, never by the notice.

**4. A private upload still lives on someone else's server.** Run the privacy scan before *any* upload,
not only before publishing.
