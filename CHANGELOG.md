# Changelog

What changed in each version of Autopen MoJo Active.

## 0.1.43 (2026-10-30)

#### Share links get a tab icon and the app's zoom keys

- The tab shows the app's icon, another app's from its own icon set
- ⌘/Ctrl + and − zoom, Shift+0 is 100%, Shift+1 fits

#### Duplicate a listed board you haven't joined

- Duplicate… shows on every board's right-click menu
- A board not yet on this computer is joined first, and the copy waits for its contents

#### Double-click a sticky note to edit it in place

- The note opens as it looks: bold stays bold, bullets stay bullets
- A bar above it does bold, italic, headings, bullets and numbers; ⌘B and ⌘I work
- Typing "- ", "1. " or "# " starts a list or heading
- Enter on a selected note opens it too; the note grows when its text outgrows it

#### The left sidebar folds to its rail

- A button at the bottom of the rail folds the sidebar to its icons and opens it again
- Any tab opens it back up; clicking the open tab folds it
- It stays folded across boards and restarts; ⌘\ still hides everything
- Help clips and the welcome film show the new button

#### Glass backdrops record instead of rasterizing on the CPU

- A backdrop is recorded as a picture shader, so the surface drawing it rasterizes it on the GPU
- A board of glass tiles over a noise shader no longer reruns that shader on the CPU per tile

## 0.1.42 (2026-10-29)

#### The usage card says how old its numbers are

- "Updated just now" or "Updated 6m ago" under the limits

#### People away from the board drop off its avatars

- Presence carries an away flag; avatars show others only while the board is their open, focused tab

#### Present always opens its setup

- With nothing selected it opens on Whole board; Selection is disabled until frames are selected
- Enter plays; Mod+Alt+Enter still plays at once

#### A setup popover for the selection

- order, tall pages, copy link

#### New Features

- One toast system, clear of the canvas toolbar
- Toasts on the canvas, and rows open their conversation
- Agents strip, inbox popover and tab dots
- Main keeps every board's agent runs for this device
- Settle a conversation from the header, the list and its menu
- Settled state and folded sub-agents in the thread model
- Settled conversations, per board in the doc
- The usage chip shows the 5-hour limit
- Usage chip and model gauge by Send
- View can show the frames selected on the canvas
- Shared links heads its scoped section Frame and layer links
- Links to selected frames, kept live in their saved slide order
- A frames scope for links, carrying the saved slide order
- A slide order saved on the board per set of frames
- Hide the bar (H) and fit tall pages to the width
- Present the selected frames
- Share is Edit and View, with a bar saying what each link needs

#### The app stays smooth while agents bulk edit

- Shadows under an opaque fill draw without a cut-out, so redrawing a page of shadowed cards no longer stalls a frame for 100-200ms
- Canvas tiles flush as they render, so the per-frame budget counts the GPU work and a big edit repaints over a few frames
- Agent layout keeps unchanged trees and Yoga nodes between calls, so growing a big frame no longer holds the main process (and every key and click) each edit
- bench-composer: typing latency, frame pacing and main-process stalls while an agent edits

#### Opening a listed board you haven't joined joins it first

- Picking it from the new-tab palette joins from the stored invite, then opens it
- A join that fails says why on Home

#### One-layer links draw layers holding instances of deleted components

- A View link to a screen with leftover copies of a deleted component showed "This layer is no longer on the board".
- Those leftovers are left out of the link, the way the board already leaves them out.

## 0.1.41 (2026-10-29)

#### Menu button on Windows and Linux

- A menu button at the left of the tab strip opens the app menu, which the hidden title bar leaves out

#### Present the board as slides in the app

- Present in the top bar plays the board as slides right in the window, starting on the selected slide.
- F goes full screen; Escape or the X brings you back to the canvas where you left it.
- Also starts from a frame's right-click menu, Option-Cmd-Enter, View > Present, or a narrated deck's slide strip.
- The browser Present link and the app share one slideshow.

#### Format tiles are all the same width

- Each group in the export dialog grows by its tile count, so every format tile matches

#### Dropped HTML files import the way the browser shows them

- Bundled exports that build their page in frames import whole, every section included
- Pills, buttons and labels inside frames stay where the page puts them
- Dropdowns show their chosen value and arrow; checkboxes and radios come along
- Input text aligns and clips like the page; textarea text starts at the top and wraps
- Fieldset borders break behind their legend
- Dashed and dotted borders stay dashed and dotted
- Pages wider than the window import at their full width

#### PDFs and SVGs match the board for logos, screenshots and borders

- Image fills with pen.dev's modes ("fit", "fill") export as contain and cover, as the canvas draws them, instead of at full size.
- Agents get a warning when they write those modes or a stroke as { fill, thickness }.
- SVG image fills on shapes are clipped images, not patterns, so PDFs keep them sharp.
- One-sided strokes and drop shadows in SVGs are vector clips, not masks.
- SVG ids are unique per export, so several SVGs on one page don't swap images.
- Double spaces in SVG text hold when the SVG sits in a web page.

## 0.1.40 (2026-10-29)

#### Your Gravatar becomes your profile photo

- Signing in to MoJo Active uses the Gravatar of your work email when you have no profile photo.

#### In-app help with guides and looping clips

- Help opens with Cmd+/ from Home or a board, and pressing it again shows the shortcuts.
- Guides cover each part of Autopen, most with a short looping clip.
- Sidebar tabs open with an intro card until you click Got it.
- Panel sections have an info button that explains them.
- Home search and board Find list matching guides and Settings pages.
- The agent answers how-to questions from the guides and shows the guide's card in the thread.
- Help's Ask agent opens a new conversation with the question filled in.
- Settings can turn intro cards off, show hidden ones again, or restart onboarding.
- Videos stream, so long clips play all the way through.

#### Claude required, welcome film, nothing made for you

- Onboarding is your profile, Claude setup and the welcome film, then Home.
- Claude setup has no skip, and Continue waits until Claude is signed in.
- Terminals are linked to Autopen on their own once Claude is ready.
- The welcome film plays once, then lives in Help.
- No sample board is created.

#### Open video scenes, drag out of auto layout, paste at pointer

- Double-click a scene of a video to work inside it, and press Escape or Done to leave.
- A video's label shows a play mark and its length.
- Hovering a video shows its play bar.
- Right-click Select layer reaches layers under others or off screen at the playhead.
- Timeline rows select on the canvas and follow the canvas selection.
- Drag auto layout children to reorder them or move them into another container.
- Paste lands at the pointer.
- Copied layers no longer show up in clipboard history apps.
- Double-click a frame's name on the canvas to rename it.
- Ask on selection stays centered on the selection.
- Videos play from the start when shown at their poster, and stop at their full length.

#### Your organization account photo becomes your profile photo

- Signing in to the organization uses your account picture when you have no profile photo.
- It is offered once per account, so a photo you removed stays removed.

#### A single file export asks where to save it

- Exporting one file opens a save dialog, so you can rename it.
- Exporting several files still asks for a folder.

#### Hover tips on usage charts and bars

- Hovering a chart day shows its total and each person's share.
- Hovering a bar slice shows its tokens and percent.
- Tooltips can span several lines.

#### What's new reads as bullets

- What's new lists each change as its own bullet, under a short heading per feature.
- Commits write a short subject and one body bullet per change.

#### Pacing in the Claude usage popover

- A mark on each bar where even use would be
- Where the window lands at this rate (~42% at reset, or Full in 2 hr 46 min)
- Amber and red like the bars
- Held for the first 5% of a window

#### Large boards open and edit without stalls

- Undo history no longer keeps deleted content in memory and saved boards forever.
- Saving collects deleted content off the main thread, so boards open faster.
- New tabs read their board before main loads it.
- A board with an unreadable key no longer keeps the window from opening.
- Panels re-read the board only when it changes, not on every selection.
- Typing in the agent pane no longer lags while an agent edits.
- Agent edits lay out only what they touched.
- Screenshots and videos render only the part they need.

#### New board always defaults to the organization

- New boards go to the organization's folder, or its Drafts, whenever there is one.
- This computer is used only when there is no organization, or when you pick one of its folders.

## 0.1.39 (2026-10-28)

#### New Features

- Cloud voices from any provider: a speech provider registry with per-model capabilities, dated prices in any unit and a cost ledger with monthly key caps, Gemini 3.8 Flash TTS and ElevenLabs Eleven v4 (21 premade voices, its audio tags, direction as a leading tag, stability for expressiveness, word pins from character timestamps, billed by its character-cost header) beside Phonon, bundled samples (ElevenLabs' free previews) measured for pitch, pace, delivery and tone, a Change voice picker with provider logos, price tiers, a Pricing dialog and every filter covering every provider, preferred voices shared on the board or the organization's list, a Voice studio and script editor with tags; plus image adjust, crop, background replace and edit, profile photos, and page exports
- An outside Claude Code session moves itself onto a board: hand_off_conversation finds the session by its tool_use id and opens a conversation in the agent pane with the summary it wrote, titled, and the next message there resumes that session with its whole history, forked so the outside app's transcript is never written to
- Lines hold exact pauses between words (say.pauses, a click between two words in the panel), each take reads differently in pace, liveliness and phrasing, a full-size line editor gathers words, pauses, direction, delivery and takes, Match my reading records you saying a line and the voice follows your pauses and pace, the voice picker searches and filters by gender, pitch, accent and age, and the all-lines settings lead back to the line; faint text meets 4.5:1 contrast and no interface text is under 11px

## 0.1.38 (2026-10-27)

#### New Features

- Html exports play a composition's motion, sampled by the same kernel as the canvas; a reader who prefers reduced motion sees the poster, autopenMotion.seek and play drive it, and what the page can't play holds still with a warning naming the node and channel
- File paths an agent writes are links: a click opens documents and media in their own app and shows anything else in its folder, never running it
- A frame exports as a page a site builder can rebuild without guessing: Export(frame, 'page') writes page.html, page.json (autopen.page/1: roles, hug/fill/fixed sizing, single-line text, 12-column spans, links, components, tokens, page settings) and report.json with lint problems
- Voice and notes are findable: a composition with no lines shows an empty Voiceover section with Add voiceover…, a frame inside a board section takes speaker notes and plays in Present, and a frame's menu offers Speaker notes… or Voiceover…; a composition is always one slide, never split into its scenes
- One slide rule for Present, narrated deck export and speaker notes: top-level frames in reading order, a board section (context 'Board section') giving its frames instead, in reading order, opening one level of nested sections; the editor's slides, Present and deck export all read slideOrder
- Every selected line offers wording suggestions: shorter ones when it runs long, same-length alternatives when it fits
- A simpler line panel and a composition panel: a line shows its words, Voice / Delivery / Take chips that open popovers, one timing row with the fit bar, its status with Play line, and a link to the composition; the composition shows Narrator, Voice sound (Before / After, Polish, Loudness, Adjust… for tone and compression), Music under voice and Captions as one-line rows that open in place. Delivery and tone apply to all lines or one; a line keeping its own shows a purple dot with Use for all and Match. Reads of a line's recording go through recordingOf
- The engine writes only board.recordings; playback, Present, export, shared links, asset sync and agents read lines' audio from it, a composition plays until its last line ends, and agents see spoken lengths as read-only spoken
- Recordings live apart from what people edit: board.recordings keyed by speech key holds each spoken line's src, length and words; lines carry only their words; readers resolve through recordingOf, clipSource and playLength; moveRecordings migrates older boards
- Polish is off by default; turning it on uses the approved sound, and Before / After compares raw with polished
- Composition delivery and line overrides: timeline.delivery sets pace and expressiveness for every line and say.polish lets one line keep its own finish, mirroring narrator and say.voice; phononSettings resolves line over composition over default, both are validated, and the voiceover guide says to set the composition's and override only deliberately
- Copied layers paste whole on another board or another Autopen: a copy carries its images' bytes, and instances of components left behind land as plain layers where the component cannot be found
- Export a board as a .autopen file (File > Export Board, Home's board menu) and import it in any Autopen (File > Import Autopen Board, Home's Import); it carries the content, every image and audio file, and the thumbnail, without members, share links or requests
- Sub-agents in the conversations list start collapsed under one row that says how many and how many are working; open groups stay open across opening a conversation
- Agent activity in the motion editor: every quick action shows a live status pill with its steps and Stop, outlines the line, scene or slide it changes with the agent's badge, and reports a result above the dock with Undo, Show change and Continue in a conversation that fades after 8s unless hovered; failures stay. The fake claude can call tools and take its time
- Narrated deck export: Whole deck exports every slide as one MP4 in reading order, and the export dialog offers One video or One per slide for several frames, each with how long still slides hold; both send ExportRequest.deck
- Music clips select from their lane into a Music section (volume, fade in, fade out); Music under voice gains Fade, writing timeline.duckFade
- Caption style popover from the export dialog and the Captions section: preview drawn with the encoder's math on the composition at the playhead, position, size, font and weight, text color, box, outline or none, box color and opacity, Reset; writes timeline.captions
- The play bar scrubs by scene: one segment per scene with gaps at the cuts, voiceover lines as amber ticks, the scene named while you scrub, and arrows step frames instead of a Next frame button
- Voice sound section for a composition or line: polish switch, Before/After by ear, loudness, tone and compression sliders that commit on release, Reset; Settings > Voices sets the polish new compositions start with
- Every spoken line is finished in TypeScript before it is stored: EQ, compressor, windowed-sinc upsample to 48 kHz and BS.1770 loudness under a -2 dBTP ceiling, matching the approved ffmpeg chain; tested against its reference
- Timeline.polish (loudness, EQ, compression) is part of each line's speech key; speechKey, needsSpeaking and phononSettings take the composition's voicing instead of its narrator, callers migrated
- Export(ids, 'mp4', path, { deck }) makes one narrated video of slides; voiceover guide covers duckFade, caption style and deck export
- Styled captions (position, size, font, weight, color, box or outline, two rows at a time), duckFade in the export mix, and narrated deck export: slides in order as one MP4, still slides held, letterboxed to the first slide's size
- ReadingOrder and srtCues for decks; music dips over timeline.duckFade on the canvas
- Ducking fade, caption style and narrated deck export in the voiceover contract
- Voiceover guide and /voiceover skill: script, cast, timing lines to scenes, pins, fitting, narrated slides; motion guide points to it
- Edited lines measure by their words until spoken again, a line drag is one undo step, and the verify script drives every screen
- Caption preview on the canvas, slide speaker notes that narrate, Settings > Voices, export sound and captions remembered per board
- Agent help menu, word pins, transcript view with cast, lanes stack overlapping lines, audition plays through Web Audio
- Voiceover lane in Scenes view, voice line panel with delivery, takes, music and captions, voice picker, Add voiceover dialog and agent review
- Agents write voiceover lines as say clips with no src; the Motion guide's Voiceover section covers say, narrator, duck, present, pins, fitting lines to scenes by voiced.length, and the 25 English voices
- Narrated slides in Present: present.start 'click' waits for a click or the next key before playing, and present.advance moves on that many seconds after the composition ends
- MP4 export picks voice and music, ducks music under the voiceover, and draws captions on the video, writes a .srt beside it, or both
- Voiceover plays where its pins put it, and music ducks under it
- Speak voiceover with Phonon on this computer: open boards speak edited lines in the background, store the WAV as a board asset and set the clip's src and voiced; voice library, audition and voice import over IPC
- MotionStarts times each layer on its composition's clock, for pins; duckCurve draws ducking as gain ramps; tests for the voiceover functions
- Voiceover line model, sync prompt, engine wrapper and clip selection in the motion store
- Timeline.present for narrated slides
- Voiceover data shape: speech on timeline audio clips, narrator, ducking, transcript and .srt; voice IPC contract

#### Fixes

- The feedback widget's region select, annotate and highlight layers undo the interface zoom, so above 100% the region box stays under the cursor
- The voice picker is 400 px wide so descriptions read and the footer fits on one line
- Panel popovers open beside the panel, not over it, and the line's chips show their full names
- Quick slider presses all count: a press made before the board echoes the previous one builds on that pending value, and the echo no longer resets a newer one; the verify step holds each press across a frame, which failed every time before
- Agent results render their markdown and fold long replies to four lines with Show more; voiceover runs reply in three short lines
- Clicking a scene hands the right panel back from a selected line, even when the line sits in that scene
- Number fields pass their scrub through as live writes, so a scrubbed length, start, overlap, delay, fade or wait is one undo step instead of one per pixel
- Panel and timeline edits undo by value: Yjs undo skips a map value something newer replaced, and the speech engine replaces a timeline with its recordings a moment after each edit, so undoing a line edit did nothing; each commit is now one step that writes the person's value back (keeping recordings that still fit), a scrub or drag is one step however long it pauses, and these steps interleave with Yjs's canvas steps by time
- Copying a layer works again: the copy handler takes payloads up to 100M characters, since a copy carries its images' bytes, and says when one is too large; a failed copy says so instead of leaving the old clipboard to be pasted
- The motion dock's Play, Space and ruler seeks start sound at once, as the play bar's do; Present follows playback the same way
- Sound follows play, pause and seek as they happen: the scene reports playback changes and Soundtracks.follow starts the clips inside the same click; drift is judged on one clock so playing no longer restarts sound 0.2 s in; decoded clips stay for the session in a bounded cache
- Settings > Voices lists one line per voice, descriptions ellipsized with the full text on hover, Default aligned
- Previews play once and the latest click wins: a click stops what plays, is spoken ahead of the picker's background length checks, and a slower earlier preview never plays late; applies to voice auditions, takes, Before / After and Settings > Voices samples
- A line due just after the playhead plays from its first word: sound decodes once a composition is selected, shown or open in the dock, not on the first Play
- Space plays and pauses after clicking a scene or line: the dock takes focus before its clips cancel the pointer to drag
- A slide's length is written only on the person's notes edits, Read aloud, and the engine's voice:status done for its notes, never on selection; films with scenes, music or several lines are never slides. Builds the reported design gaps: review outlines and badges on changed scenes and link pins on pinned lines, agent-suggested wordings for long lines, Applies to all slides, a Whole deck section, a slide strip dock, and a caption preview in the MP4 export. verify-voiceover-ui runs on the real engine and catalog, waits on voice:status, and checks popovers at a 125% interface size
- The help menu and voice picker open where they belong at any interface size, placing in interface pixels like the app's other popovers
- Speaker notes size only a slide whose sound is just its notes; selecting a composition with more lines or music no longer cuts it to the first line's length
- Speaker notes render from the panel, keeping the properties section table free of window globals for its tests

## 0.1.37 (2026-10-27)

#### New Features

- Layout grid and space and Text setting guides, read for nearly every design task, and the composer stops suggesting skills as people type
- A presented slide zooms: Ctrl+wheel at the pointer, the bar's buttons, drag and the wheel to pan, 0 to fit again, and a click on a zoomed slide stays on it; Shift+wheel pans sideways in every scroll mode
- Usage counts terminal work by reading the transcripts of sessions that called Autopen's tools, matched by tool_use id whatever the server is named, instead of a Stop hook in Claude Code's settings that ran in every session; launching removes the old hook and leaves the person's own

#### Improvements

- Runs spend less of the plan: they compact at 200k tokens, board skills are listed and read when needed instead of sent whole, tool results are compact JSON with repeated warnings folded and Print capped, get_app_state details only the run's board, screenshots top out at 1000px, and spawn_agents can put a sub-agent on opus, sonnet or haiku

#### Fixes

- A text measure that throws no longer breaks layout for the whole process: the error is held until Yoga finishes instead of unwinding through its wasm, which leaked its stack until every insert and screenshot failed; a Yoga instance that traps is replaced with a fresh one, sessions free by node so a repeated id can't free a node still in use, and an unknown text alignment draws as left

## 0.1.36 (2026-10-26)

#### Fixes

- The browser viewer's security policy allows Sprout's widget script, so watch and present links show the feedback button again

## 0.1.35 (2026-10-26)

#### New Features

- Usage counts outside Claude sessions: tokens include them, runs show + N external sessions, a Where the tokens came from card splits runs in Autopen from external sessions with the tool calls from outside, board rows and people say how many sessions came from outside, and the Board tab shows runs and how many outside
- Settings > Claude has a Count that work in Usage switch under Use Claude in my terminal too, on unless turned off, which adds a Stop hook to Claude Code's settings beside its own and removes only that hook when off
- Tool calls from Claude sessions outside the app count on their board, and a finished turn reported by Claude Code files its tokens under the boards it touched, split evenly, with each session counted once per board and day
- The MCP server tells the app about every finished tool call, which board it worked on and whether it came from outside or from one of the app's own runs
- A board's usage counter can hold work from outside the app, kept apart from runs, with the tool calls and sessions it took, and builds from before still read their own keys
- The Share popover's Sprout row links a project in the browser instead of asking for a key
- The Sprout widget's screenshot handler lives in MoJo, so core can drop it
- One-layer share links carry the board's Sprout project, so their viewer shows the feedback widget too
- Share says a one-frame link sends only that frame and makes it on first copy, and a Shared links entry with a count opens a list of the board's links where any editor can copy or delete a one-layer link after a confirm, beside the whole-board links and invite that can't be deleted
- A scoped link opens only its layer's signed copy with the board name and Live or Owner offline, says when it was last updated with no editor online, and a deleted link says it no longer works; board-perf --scoped measures it
- Every editor's app keeps a board's one-layer links live in a signed copy of their own, a one-layer View or Present link is that copy's link and the same one each time, and deleting a link empties its copy and clears it from the relay
- A scoped share link has its own key derived from the board key and its id, a v2 link format that carries only that key and a verify key, and its writers sign every frame and kept entry so a viewer can't write into the copy
- A one-layer copy holds only that layer, hoisted to where the board lays it out with its inherited theme, opacity and clip, instances and library components expanded, and only the variables and images it uses
- A board keeps a list of its scoped share links, one per layer and mode, and a scoped copy is brought up to date with only the writes that differ

#### Fixes

- The app starts again: outside work is set up once this device's id is known
- Closing a board connection sends the frames it was still sealing, so the last edit and the goodbye reach the room before the socket goes

## 0.1.34 (2026-10-26)

#### New Features

- A one-layer link draws only that layer, loading shows real progress, and a corner zoom control with a first-visit hint
- Settings has a Usage section with Claude tokens, agent runs and storage for the boards on this computer, a page per board, and the Board tab shows the board's last 30 days with a Details link
- Every finished Claude run adds its tokens to its board's usage counter, phone requests included, and each board's usage and storage, here and on the relay, can be read for Settings
- The relay answers how many sealed bytes it keeps for a board, edit history and images, and the net client asks on a socket of its own so an older relay just reads as unknown
- A finished run reports the tokens it used per model, input, output, cache reads and cache writes, summed over every turn, and the feed leaves them out
- Each board keeps a grow-only usage counter of Claude tokens and runs per device, day and model, with API list prices to estimate cost
- Share is one link: pick Edit, View or Present, choose the whole board or one frame, then copy it or scan its QR code

#### Fixes

- An unpriced model and an unknown online size read as n/a in the Usage tables
- The Usage tables lay out in rows beside the plan usage meter's styles, the period switch lines up with the tiles, the Board tab rereads storage as the board grows, and empty periods say so
- One-frame share copy says the link still carries the board key
- One-frame share copy promises what the link does today, until scoped links stop sending the rest

## 0.1.33 (2026-10-26)

#### New Features

- Boards name a Sprout project in the Share menu, and their browser watch and present links show its feedback widget

## 0.1.32 (2026-10-23)

#### New Features

- The Milestones tab drops milestones whose layers were all deleted, since there is nothing to go to
- The empty Skills tab explains that built-ins need no adding and offers to add the team's own, and every tab header gets a bottom border
- A Code tab on the rail links this board's code folder on this device, out of Device memory
- The sidebar rail's tooltips show at once, beside the icon instead of under it
- Memory's rail icon is a brain, so it no longer reads as a second book beside Skills
- The usage badge is smaller and names the plan's size, Pro, 5x Max or 20x Max, from the tier the Claude CLI keeps in its config
- The skill dialog and the Skills home say agents use built-in skills on their own when a task needs one, so nobody adds them out of habit
- A new conversation asks what we are making, with eight kinds of work that each add their built-in skill, instead of a sparkle and two fixed examples
- The left sidebar opens 400px wide
- The left sidebar's tabs move into a 44px icon rail on its inside edge, Skills gets its own tab, every tab but Agent gets a titled header, the Agent item shows the open agent's avatar with a dot when one needs you, and Option+1 to 8 switch tabs on a Mac
- On a board with no style, an agent starting new design work offers three fitting styles with ask_question and designs in the one picked
- A question offering styles shows each as a specimen row, with Three others, Browse all styles and Use for this board, which sets the picked style in one undo step before answering
- Ask_question takes a style key on an option to show that catalog style's preview, dropping a key the catalog doesn't have instead of failing
- A question's option can carry a catalog style key, kept through validation when well formed, and an answer that saved the picked style tells the agent so
- The Board tab sets an optional style from a gallery of 67, searchable by name or feel, applied in one undoable step, and every agent run on the board follows it
- Get_style takes hallmark: and autopen: keys and lists Hallmark's themes, and get_app_state reports each board's style
- Every run hears the board's style, to design new work in it and read its brief first, or that it has none and should choose a look itself
- A board can carry one style, and applying it writes its variables without touching ones the board already had, removing the previous style's own
- A style catalog lists Autopen's 26 styles and Hallmark's 41 themes as cards with swatches, fonts and moods, and gives each one's board variables and brief
- New agent work in the Board tab lets you choose Add to board or Review first, and Review first says once where it put Final, Drafts and Archive, with Show on board and Undo
- Hallmark ships as two built-ins, designing a page in Website design and an anti-slop review in Craft
- Hallmark.md translates Hallmark for the canvas, the way craft.md does for the craft skills
- Wireframes and low-fi exploration is a built-in guide, three arrangements at the real screen size
- UX audit is a built-in guide, Nielsen's ten heuristics as a board of findings with the evidence pinned
- Android screens is a built-in guide, with the Material 3 metrics an iOS guide cannot stand in for
- A built-in's folder path starts with "Built in", so Autopen's Animation folder and your team's never read alike
- Opening a built-in skill says so and offers Duplicate, instead of a Save it can never do
- Built-in skills get a section of their own on the Skills home, as smaller cards under the folders your team wrote
- Empty and error states is a built-in guide, because six different screens get called the empty state
- Onboarding flows is a built-in guide, where the deliverable is the flow laid out left to right
- Forms is a built-in guide, opening with which fields to delete rather than how to lay them out
- Icon sets is a built-in guide, where the work is choosing names rather than drawing marks
- Brand guidelines sheet is a built-in guide, eight sheets whose content is the board's own tokens
- Logo and wordmark is a built-in guide, in a new Brand folder, built around never drawing a logo from primitives
- Pricing pages is a built-in guide, for the whole page rather than the band landing-page.md covers
- Social posts and ads is a built-in guide, for feed posts, stories, carousels and display ads
- Email campaigns is a built-in guide, in a new Marketing folder, for email that survives Outlook, blocked images and a preview pane
- The seven vendored craft skills are built in, in a Craft folder, each headed by the line that says its CSS rules are canvas properties here
- Shortcuts dialog, embed widget capture and hiding layers (work in progress committed before merging Skills and Brainstorm)
- Skills is one Home page with folder cards, a folder page and an editor without a tile, and the composer gets one skill menu with the merged model control
- The Board tab and the canvas menu call the middle frame Drafts, and a review heads the menu on a Brainstorm board
- Get_app_state names the Drafts frame, so an agent reading the Brainstorm rule builds where the board says
- The Brainstorm layout's middle frame is Drafts, and a board laid out before the rename has its WIP frame taken over and renamed
- The Home sidebar lists the skill folders under Skills, opens one and takes a skill dropped on it
- Approving or archiving a frame reads as one line with the button as a pill, and the agent gets the rules behind it
- The composer's skill menus check off several skills at once, and the chips wrap above the message
- The Skills page drops Most used, and skills stop recording their own use
- A folder's skills read as cards, and the Skills page takes the find keys
- The Skills page is folder cards, most used and a table, and a skill opens as a document with its history
- Home has a Skills page with folders and an editor, boards get a Skills section, and the composer picks skills per message
- List_skills shows an outside agent the skills people keep here, and read_skill reads one by id
- Skills get folders, a version history and an icon, and every injected skill says who wrote it
- The Notes tab becomes Memory, holding the board's shared memory and this device's, with the same wording in what agents read
- A Board tab carries the Brainstorm switch, and approving or setting aside a WIP frame from the canvas menu starts an agent run that does the move
- The Brainstorm rule leaves the moves to the agent, which knows where in Final a screen belongs and what it replaces, so the layout module only finds and creates the three frames
- Skills live in three places, the organization's list, this computer and built in, behind one typed store
- A run starts with the skills its board attached, and with the ones the person picked for that message
- A board carries the skills its people attached, so every device's agents follow the same ones
- A Brainstorm switch in the Notes tab lays the board out as Final, WIP and Archive, and the canvas menu approves a WIP frame into Final or archives it
- An in-app run's prompt carries the board's layout rule next to its notes, so a Brainstorm board binds the agent it starts
- Get_app_state hands every agent the Brainstorm rule and the ids of the Final, WIP and Archive frames when a board runs the layout
- The Brainstorm layout, a board setting with Final, WIP and Archive frames, where approving a WIP frame moves it into Final and what it replaces goes to Archive

#### Fixes

- The milestone badge in chat and the Milestones tab use the rail's map-pin-check
- Menus and popovers sit darker than the panel in dark mode, so they no longer blend into the sidebar
- The agent composer rounds like the sidebar instead of squaring off at 0px
- The skill menu stops offering Autopen's old /commands beside the built-ins they duplicate; a pasted /command still runs
- The Agent tab's header names the agent without repeating the rail's avatar, and sits on the rail's centre line at 40px like every other tab
- Switching or clearing a board style keeps any of its variables a layer still uses, and the note's Undo takes back only the style change
- Undo on the Review first note keeps any Final, Drafts or Archive frame that has work in it, removing only the ones still empty
- Geist and Mona Sans are on Google Fonts, so Lumen, Specimen, Studio and Midnight need no substitute
- The model popover spans the agent panel instead of running off it, its model list scrolls on its own so effort and usage stay in view, and Extra high no longer wraps
- A folder's tint keeps its hue in both themes, a skill's instructions read as a document, and the skill and folder menus carry their icons
- A skill's card grows with its instructions, so the count line sits below them instead of over them
- Windows saves wait out a briefly locked meta.json, so a board opens and stops saying Joining once it has loaded
- The slash menu keeps naming autopen's own skills first, and verify-usage drives the merged model control
- The Brainstorm frames take a tint that stands out from the canvas, so the three zones read at a glance behind white screens
- A canvas menu taller than the window scrolls in the room it has, instead of running off the bottom where the last rows cannot be clicked

## 0.1.31 (2026-10-23)

#### New Features

- List_milestones gives an agent the board's milestones, newest first, so it can find where earlier work finished or pick up where someone left off
- Get_presence tells an agent who else is on a board, people and other agents, and which layers each has selected or is working on
- Get_invite_link hands out a board's share links and join_board takes one, so an agent can bring a shared board onto this device and work on it

## 0.1.30 (2026-10-21)

#### New Features

- Home gets one sidebar on every page, with Favorites grouped by account and every account's folders as a tree that takes drags, and pages with one header band and folders as tiles
- A Home drop target can refuse and say why, so the drag pill explains instead of just not landing
- Home's New board takes a place, so a folder's menu can make a board right there
- Home-model groups favorites by account, finds a folder's account and sorts boards by day, for the new Home sidebar and Recent page

#### Fixes

- Opening a board by its hash works again after leaving it for Home, which the window ignored as its own write

## 0.1.29 (2026-10-21)

#### New Features

- Right-click a frame to use it as the board preview, so Home's card shows that frame instead of the whole board
- Boards you open become tabs in the top bar
- Main keeps each window's tabs loaded and hands a board to the window that has it
- The rules for a window's board tabs live in one place
- An Agents dialog sets up the board's agents (name, instructions, their conversations, reset), the composer picks who a new conversation is with, and right-click offers Edit <agent> and Rename conversation; scripts/verify-board-agents.ts checks it in the app
- A board can set up its agents, each with its own name and instructions every conversation with it starts from, and its conversations can run side by side; conversations can carry a title; the feed reads both, so desktop, phone and cursors all show the board's names
- Background sub-agents show once, in the thread, and the Still running tray becomes one line above the composer that counts them, with Show to scroll to their cards and Stop all

#### Fixes

- The top bar's tab list leaves room for the active tab's ring and shadow, which its scroll box clipped
- Sidebar tabs drop to icons when their labels stop fitting, measured instead of a 400px breakpoint, so the row never runs past the panel
- Tabs keep the strip, the hash and the menus to themselves
- A closed board lets go of its WebGL context instead of waiting to be collected

## 0.1.28 (2026-10-20)

#### New Features

- The agent sheet shows sub-agents as cards that open into their run, and keeps working while background ones run
- Sub-agents show as live cards where the agent started them, open into their own run, and background ones stay in a Still running tray with Stop until they report
- Keep sub-agents and background tasks in the feed: task_started/task_ended events, runs stay open while background work runs, stopTask

#### Improvements

- An edit marks the parts of raster tiles it drew over instead of throwing the tiles away, and they are painted again from the picture clipped to those parts, so zoomed out a small edit no longer replays a whole frame; check-reuse can run a chosen list of edits in turn
- A relay link says hello once the room's copy is in, so peers send only what it lacks instead of the whole board again, and readers don't listen for updates, which made Yjs encode a whole board as it arrived; the canvas stops forgetting kept trees at the first one it has none for, and a frame's first picture records without breaks
- The Components tab reads which nodes are reusable off their maps instead of copying every node of the board on each edit
- A rebuild redoes only what an edit changed: trees keep the objects of unchanged subtrees, which expand and resolve once, each frame keeps its Yoga tree so layout touches only changed paths and reads back only what Yoga laid out again, scenes hide nodes through a set instead of changing the shared tree, and an edit throws away only the raster tiles it drew over; check-reuse also compares tiled views, variable edits and moves of top-level frames
- An edit lays out and records only the fixed-size frames it touched: their children's boxes and their pictures are kept between builds and reused where nothing inside changed, recording yields to input between frames, components expand once per instance chain, and resolving variables copies only what holds one; packages/viewer/scripts/check-reuse.ts checks every box and pixel against a fresh build after random edits to a real board
- Text measures find their paragraph by node instead of rebuilding its key on every call, and Yoga's defaults are left unset; packages/viewer/scripts/bench-build.ts times building a real board's largest frame
- Board thumbnails draw one board at a time once it has been still a few seconds, drop each board's layout once the picture is taken, and pause while a board is open, so the list never holds big boards twice; phones keep 256MB of decoded images instead of 768MB
- An image that arrives after its frame was built records the frame again from the same layout instead of laying out the whole frame again, and a burst of arrivals records once; apps/web/scripts/board-perf.ts measures a real board in the browser viewer as a phone
- Boards open and rebuild faster: one text cache per renderer outlives builds and remembers layouts and measures, fonts count as new only when a face really registers, and a window loads the board from disk while main opens it instead of waiting for main to encode it
- Only the animated parts of a section redraw each frame, so a looping composition inside a big frame no longer re-lays-out and repaints the whole section every frame or keeps the app from idling; the play bar finds compositions once per board change instead of on every camera move

#### Fixes

- Only the time spent rendering raster tiles counts against a frame's tile budget, so drawing the rest of the frame (other frames' tiles, live shaders) can no longer leave a tile waiting forever with a blurry stand-in
- An update too big for one relay message goes out in parts the size the room keeps the board in, so a big paste or a whole board for a new peer gets through instead of the relay closing the sender's socket and it never arriving; older clients ignore parts, which never reached them anyway
- A turn that ends on background shells alone says so instead of 0 still running

## 0.1.27 (2026-10-19)

#### New Features

- Milestones tab lists where agents finished work with a live thumbnail of each layer and zooms there on click; agents mark them with mark_milestone, a run that marks none gets an Auto one for the frames it edited, and the done message carries Worked on chips on desktop and iOS
- Calls that name no board go to the session's own or last-used board, or the only open one, and refuse to guess among several; agents open closed boards in the background by id and keep the boards they work on loaded until they disconnect
- Sideload publishing and the in-app update banner

## 0.1.26 (2026-10-15)

#### New Features

- Ask on the selection names who it reaches and hands off to that agent's conversation in the pane, quick edits report beside the selection with Undo, and agents ask the person through an ask_question card in the thread instead of notes on the canvas
- Rotation sits under Position as in Figma, a degrees field beside Rotate 90° right, Flip horizontal and Flip vertical buttons
- Copy as SVG in the right-click menu and the quick export's Copy group puts the selection on the clipboard as SVG markup and as the system's SVG image type, and the Export dialog writes an .svg file with its fonts inside
- Export(ids, "svg", outPath) writes the nodes as one SVG drawn as on the canvas, to a folder or a .svg file
- ToSvg draws picked nodes as one SVG that matches the canvas pixel for pixel (layout boxes, Skia-shaped text with every glyph placed, strokes, shadows, blurs, gradients, images, icons), with fonts embedded on request and an svg format for exportNodes
- One Share button opens a popover with a link per audience (edit in the app, watch live in a browser, present as slides) that can open at the selected layer; Present and View link leave the top bar, and connection status shows only when the board is not connected
- Sixteen cursor colors to pick from in Settings > Profile, wrapping to a second row; a name's default color still comes from the first eight, so nobody's default changes
- Copy link to layer in the right-click menu copies a link that opens the board with that layer selected and zoomed to; a board this computer already has opens straight there, any other asks to join first

#### Fixes

- Layers turn about their center as in Figma, from the rotation field, Rotate 90° right and the corner drag; a multi-selection orbits its shared center
- The rail's accounts button on Home goes straight to the accounts list instead of opening the switcher

## 0.1.25 (2026-10-15)

#### New Features

- Deleted boards go to Recently deleted on Home for 30 days, where they can be restored or deleted forever, and a delete's toast offers Undo; a board its sharer deleted for everyone still leaves joined computers for good

#### Fixes

- HTML files up to 50 MB import when dropped on the canvas, written into a blank page instead of a data URL that Chromium caps at 2 MB; images a page makes from blobs are kept as data URLs, so bundled exports import with their pictures

## 0.1.24 (2026-10-15)

#### New Features

- Images and files sent to the agent show with the message in the thread, as thumbnails and name chips; the feed keeps a stored image's url and a file's name, never bytes or full paths

#### Fixes

- A stroke with a zero-width side no longer leaves a faint hairline along that side on the canvas

## 0.1.23 (2026-10-14)

#### New Features

- Home calls the directory's top folders accounts
- Home gets a rail (Go to, Home, top folders, This computer), a landing page with search, Jump back in and starred Favorites, a table of the directory's top folders, a quick switcher that reopens the folder last open in each, and a tree beside a folder's contents with a list or grid layout; favorites replace pins, and a directory provider can name its top folders

#### Fixes

- Home's list/grid toggle uses the app's segmented control, with even padding and a selected state that shows in dark mode

## 0.1.22 (2026-10-13)

#### New Features

- The agent composer shows how much of the Claude plan is used, as session and weekly bars at the end of the model row with a popover for exact numbers and reset times; at a limit, new sends wait with a notice saying when they resume

## 0.1.21 (2026-10-13)

#### Fixes

- The user's window is always a board or Home window, never a hidden browser parking or export window, so an agent using the user's browser no longer loses its page mid-navigation
- A section the capture cannot read imports as a blank placeholder instead of failing the import; ids and tags are read from attributes and the prototype, so a form whose inputs are named id or tagName no longer breaks it

## 0.1.20 (2026-10-13)

#### New Features

- Drop an HTML file on the canvas to import it like a browser page, laid out offscreen at the browser panel's viewport and placed at the drop point

## 0.1.19 (2026-10-12)

#### New Features

- Variables manager with grouped table, detail and bulk edit, themes page, health checks, and export (CSS, Tailwind v4, W3C tokens, Figma, Autopen JSON) and import with a diff
- Collapse layers out of the way to labelled chips (Cmd+Shift+C, the layers row, the panel or the context menu); collapsed nodes keep their place and contents but aren't drawn or exported
- Phosphor (six weights) and Material Symbols (outlined, rounded, sharp) icon libraries alongside lucide, drawn, laid out and exported from their official SVGs; an unknown icon draws a dashed placeholder and is reported to agents
- Motion editor, a timeline dock for compositions with scene and keyframe editing, panel sections, record keys and scoped asks
- Timeline edits as pure functions (scenes, cuts, ripple, reorder, keyframes, transitions) and a motion focus block runs can carry

#### Fixes

- A drag's final commit restores what its live steps moved, marker-timed scenes stay put, transitions only replace their own keys

## 0.1.18 (2026-10-12)

#### Fixes

- The Mac smoke test runs on a self-hosted runner, using a throwaway default keychain since the login keychain is locked without a GUI login

## 0.1.16 (2026-10-09)

#### New Features

- Copy as PNG and Copy as HTML from the selection's quick export menu and the right-click menu; right-clicking a selected artboard's background keeps it selected

## 0.1.15 (2026-10-09)

#### New Features

- Agents start in the board's linked code folder, so its settings, CLAUDE.md, skills and MCP servers load as if opened there; resumes start where their session did

## 0.1.14 (2026-10-08)

#### Fixes

- Cmd+F puts the cursor in the find bar's input, so typing searches right away

## 0.1.13 (2026-10-08)

#### New Features

- Cmd+F finds text on the canvas, highlights every match and steps through them with Enter
- A button in the top bar checks for updates on demand and says how the check went

## 0.1.12 (2026-10-08)

#### New Features

- The Agent panel explains failures in plain words and offers Continue for runs Autopen closed on
- Sticky notes render markdown: titles, bullets, numbered lists, bold, italic and code
- A formats guide gives agents the sizes for devices, social posts, ads, emails, print and store assets
- The board's side panels float, inset and rounded, with the canvas running beneath them
- The Agent composer starts taller, text across the full width with + and send underneath
- The composer's + is a menu: attach files, or use a skill (/)
- An execute call can wait for its Generate jobs to land with WaitForGenerate, so its screenshots show them
- A count can show as a clock (1:12) or zero-padded with countFormat time and pad
- A node riding a path can start part way round with along.offset and lap forever
- Motion can stretch a node on one axis with scaleX and scaleY tracks
- Reference skills anywhere in a prompt, yours included, as inline badges

#### Improvements

- Animated screenshots, filmstrips and video export render up to 18x faster and stop freezing the app

#### Fixes

- Clicking and dragging layers on the canvas works like Figma
- Background blur and blend modes draw on the board instead of nothing
- An imported page matches the browser pixel for pixel, SVGs, icons and gradient text included
- Floating panel and composer corners nest concentrically (16px panel, 8px inset, 8px input)
- The Agent composer asks you to describe what you want
- The Agent composer's placeholder doesn't name a model
- The Agent composer's placeholder fits on one line
- A shader inside a composition runs on the composition's clock, so its poster frame and screenshots match the video
- An unknown prop warning says which prop to use instead, like effect for shadow
- An agent's full reply shows in the run view instead of stopping at 2,000 characters
- A working sub-agent's card shows the step it is on instead of the brief it was given
- A middle-button pan that leaves the canvas ends instead of staying stuck to the pointer

## 0.1.11 (2026-10-08)

#### Fixes

- An embedded script's popups open in the person's browser like every other link

## 0.1.10 (2026-10-08)

#### New Features

- AUTOPEN_EMBED_SCRIPT puts a build's third-party script, such as a feedback widget, on every page

#### Fixes

- Typing in a field inside a shadow root no longer fires canvas shortcuts
- Code an agent writes follows that project's CLAUDE.md and skills through to done, release notes included
- Menus and popovers over the browser page show above it, with a still of the page in its place

## 0.1.9 (2026-10-08)

#### New Features

- The relay keeps an encrypted copy of every board and its images, so a board opens with nobody else online

## 0.1.8 (2026-10-07)

#### Fixes

- Agents browse in their own pages signed in where the user is, and take turns on the user's tab

## 0.1.7 (2026-10-07)

#### Fixes

- Browser connects realtime backends over WebSockets, and pasted images reach the agent as board assets

## 0.1.6 (2026-10-07)

#### New Features

- The directory server keeps Drafts named Drafts at the top, refusing a rename or a folder inside it
- Home is organized around spaces, pins and a Move popover that says what a move will do
- Home remembers the rows you pinned to the sidebar and the folders you moved boards into lately
- A new board can be made straight into a folder, and a board on this computer can be renamed or duplicated
- A board records which computers have it, so Home can tell when a shared board is still only yours
- New boards have a home: Drafts sits at the top of the shared list, where it can't be renamed, moved or deleted

#### Fixes

- Claude setup shows signed in after a sign-in that finished while a check was still reading the old state
- New board lays its fields out like Settings, the Move popover stays in the window as it grows, and the level you are at is a destination in the folder picker

## 0.1.5 (2026-10-06)

#### New Features

- A frame an agent grows into its neighbours pushes everything past its old edge aside in the same update, so nothing is ever designed underneath another frame

#### Fixes

- An image whose bytes arrive while its frame is still building draws without a reload

## 0.1.4 (2026-10-06)

#### New Features

- Anyone in the tenant can rename a listed board, keeping its invite and owner, so a rename reaches every Home
- Renaming a listed board renames it on the list for everyone, whoever renames it, and Home shows the list's name
- Opening a board says Opening board…, and a big one says Loading board… until its first draw settles
- Home opens with Recent, the boards last opened on this computer, as many as fill one row

#### Fixes

- The toolbar sits above a selection's quick actions when they reach the bottom of the canvas
- The viewer draws a board's Google fonts, served by the relay as the same TTFs the desktop app uses, instead of falling back to Inter
- A board being joined keeps the name it was listed under and says Joining… with a spinner, instead of being renamed Joining…

## 0.1.3 (2026-10-06)

#### New Features

- The directory keeps folders anyone in the tenant can organize, files shared boards in them, and refuses a cycle or a non-empty delete with the app's own rules
- Home files boards in nested folders, in a Personal tree on this computer and the directory's tree for everyone signed in; Move to…, drag and drop, a breadcrumb, folder search, and delete only when empty
- The deletion marker is a hint to re-read the list, never the licence to delete
- The person who shared a board to the directory can delete it for everyone
- The directory deletes a board for everyone, and lists deletions so every device drops its copy

#### Fixes

- A board's first owner is remembered after unsharing, so no one else can list it or delete it for everyone

## 0.1.2 (2026-10-06)

#### New Features

- Releases cut themselves: once CI passes on main with a feat, fix or perf since the last tag and main has settled for 15 minutes, auto-release tags the next version and starts the release
- Importing a Figma file says how far it has got, and what landed
- The directory has its own Entra app registration, Autopen MoJo Active
- The directory uses Cultivate's Entra app registration
- The desktop app signs in to the directory with a work account
- Deploy.sh takes a directory target, and checks only that target's CHANGE-ME values
- A company board directory Worker, one row per shared board, behind an Entra token
- Home lists the directory beside Personal boards, and Settings shows the account
- Windows read the directory, sign in and share through ipc, and hear every change
- A board directory a fork fills in, which lists an organization's boards behind sign-in

#### Fixes

- A board is republished to the directory only when renamed on this device, so a second device never publishes a joining placeholder or brings back an unshared board
- A big board opens fitted to what has built so far, instead of at 100% until every image decodes
- One import note per kind, with how many layers it happened to
- A Figma file imports every layer, not the first 5,000
- One board letting go of an image no longer takes it from another
- A canvas keeps photos at screen size, and gives them back when the board closes
- A board of big photos no longer takes the canvas down
- Directory.toml's comment no longer trips deploy.sh's CHANGE-ME check
- Sign-in uses its own localhost/autopen redirect and accepts the shared registration's v1 tokens
- Builds leave the directory off until the Entra app registration is filled in
- The directory names a sharer by sign-in name, so the desktop can tell its own boards
- A directory that could not be read says so above its boards

## 0.1.1 (2026-10-06)

#### New Features

- MoJo Active icons, a Primary Orange nib on Dark Blue
- APP_ICONS points a build at its own icon set, and scripts/icons.ts --out draws one recolored and named for that app
- Verify:figma checks the import against Figma's own render
- File > Import Figma File… opens a .fig as a new board
- Paste a Figma selection, or drop a .fig file, on the canvas
- Turn a Figma scene into editable layers
- Read Figma files and copied Figma selections

#### Fixes

- Publishing to a releases repository without a CHANGELOG creates one; the README and CHANGELOG carry the app's name, and the README leaves out TestFlight when SKIP_IOS is set
- Read Figma's order keys by their bytes, and guard untrusted parents
- A zero-width Figma stroke draws nothing, and one effect per layer
- Place Figma pages from the boxes Figma measured
- A paste with html but no text still reads the system clipboard

## 0.1.0 (2026-10-06)

#### New Features

- APP_NAME, APP_ID, APP_SCHEME and APP_MCP_PORT make a separate app that installs and runs beside Autopen, with its own data, keychain entry, invite links, MCP port and updater cache
- The SKIP_IOS variable leaves the iPhone build out of a release
- RELAY_URL and VIEW_ORIGIN variables point a build at another relay and browser viewer
- The releases repository comes from the RELEASES_REPO variable, so a downstream copy publishes and updates from its own

#### Fixes

- The drift check fetches upstream with UPSTREAM_TOKEN, not checkout's token
