# Changelog

What changed in each version of Autopen MoJo Active.

## 0.1.56 (2026-11-04)

#### Photo libraries (Nextcloud) for everyone

- Connect a library and photo servers show in the Media tab and Settings for everyone, no early feature needed
- Agents see connected libraries in every run
- Early features stay ready for the next one; the admin section hides while there are none

#### The company can hand out an Openverse key

- Openverse joins the keys a company admin can set for everyone

#### scrollbars, opening links on the canvas, and editing fixes

- The board has thin scrollbars that grow on hover
- Resting on a link or a typed-out web address on the canvas offers to open it
- Unlinking a text's own link unlinks all of it; only valid web addresses count as links
- Double-clicking a selected frame's background crops its image
- Content section has an Edit on the canvas button
- Pasting next to a chip in the chat box pastes into the box
- The Export dialog is larger

#### What each board spent on images and voice, made against used

- Usage shows each board's and person's image and voice spend, with how much of it the board still uses
- Download the spend as a CSV

#### Footage on the MoJo relay, signed in by MoJo account

- The MoJo relay checks the board directory's own token for footage, so signing in to the directory signs footage in
- relay.toml gains the footage bucket, quota object and its migration

#### A company sign-in signs footage in on its own

- A directory provider can hand out a relay token; the desktop trades it for a footage ticket with no browser
- Signed in to the directory means signed in for footage; Apple stays the core sign-in

#### Clips reach the board while their uploader is offline

- Each desktop puts the clips it has on the relay in the background, two at a time, resuming after a quit
- Someone opening the board later gets a clip from the relay when nobody online has it
- The clip bar says Sharing N% while it goes up; nothing new to choose
- A board past 80% of its footage storage gets a notice, and a clear one when it's full
- Admins can change a board's footage limit (API only, Settings row to come)
- Sign in with Apple plumbing: asked only when a clip needs the relay

#### An in-app right-click menu for text you are editing

- Cut, copy, paste, bold, italic, underline, strikethrough, lists, case and links
- Spelling suggestions and Add to Dictionary in the same menu
- Italic is no longer greyed out before the font list loads
- Bold, italic and undo show at once, even in big frames
- Strikethrough on Shift+Cmd+X

#### Footage reaches people from the relay when nobody has it

- Shared copies upload to the relay in sealed 4 MB chunks, bound to the copy's hash and place
- Uploads resume where they stopped; two people uploading one file meet in the middle
- A clip nobody online has arrives from the relay in order, even while it's still uploading
- Peers stay the fast path; without sign-in footage stays peer to peer

#### Footage in R2, sealed, behind Sign in with Apple

- Rooms keep a ledger of their footage; sealed 4 MB chunks live in R2 under footage/<room>/<id>/<n>
- Every footage request needs a session ticket the relay signs after checking an Apple identity token
- Limits per board (100 GB, admins can change), per uploader per day, and for the whole relay
- Footage no board uses is deleted after 14 days; a board deleted for everyone takes its footage
- Local relay with real Workers runtime and local R2 for tests (packages/relay/src/local.ts)

#### Type settings, lists, and editing that matches the canvas

- Type settings popover from the Typography header: Basics and Details
- Decoration style, thickness, color and offset
- Small caps, number styles, ligatures and stylistic sets the font has
- Vertical trim, paragraph spacing and indent, truncate to max lines
- Bulleted and numbered lists; type "- " or "1. " to start one
- Editing text shows one copy, one outline, and wraps like the canvas
- Exports carry the new type settings to SVG, HTML and React

#### A shorter right-click menu with submenus

- Rows that don't fit the selection are left out instead of grayed
- Copy as › holds PNG, SVG and HTML; Copy link to layer stays in the main menu
- Arrange › holds Bring to front, Bring forward, Send backward and Send to back
- Transform › holds the flips and 90° turns; on a picture the turns keep it upright
- Image › holds crop, colors, background edits, vectorize, trim and save
- Select layer › starts with Go to layer and Select parent, then the layers under the cursor
- One Flatten row; Union, Subtract, Intersect and Exclude move into Boolean ›

#### AI image spend in Usage, an OpenAI cap, and limits on agents

- Every OpenAI image (Generate ai, replace background) records its cost on its board, priced from the tokens billed
- Settings > Usage gets an Images tile and column; the Board tab shows a board's AI image spend
- Voice and Images cells in the boards table show cost only
- The OpenAI key takes a monthly cap in Settings > Integrations; images stop before passing it
- Agents start at most 4 AI images a call and 20 per board an hour, and are told images cost money

#### Right-click menus, an empty start, and Openverse keys for the whole company

- The Media tab opens on an empty state and loads nothing until you search
- Right-click a result: Add to canvas, Fill selection or Replace image, About, Open original, Reveal in Finder; sounds get Play and Add at playhead
- The spinner on a playing sound's play button is white
- Admins can share their Openverse keys with everyone in the company; members can't connect their own
- Adjust colors… opens the image fill's picker on its sliders again
- The selection bar's export button opens the Export dialog on the selection, and clicks inside it no longer reset it
- New conversation and Cmd/Ctrl+N put the cursor in the composer
- The timeline clip style builds whole again

#### A cleaner fill picker that opens beside the panel

- The picker opens left of the right panel, level with the row, as in Figma
- Image fill: a preview to click or drop a file on, a Link field, Crop and Adjust groups with their resets
- Sliders line up in fixed columns; adjust sliders fill out from 0 and a double-click on a label resets one
- Gradients get Reverse stops beside the angle; mesh swatches fill the width
- Shader labels sit in a left column, Source says what the shader reads, and color opacity no longer clips

#### Controls for the CapCut extras

- Transition chip on every cut; a transition shows as a shaded band, half on each clip
- Picker anchored at its cut, with thumbnails of the two clips for every kind; Zoom blur, Whip, Spin, Glitch and Light leak tagged new
- Drag a transition's edges to set its length, stopping at a red line at half the shorter clip
- Transition section in the right panel: live preview, kind, length, direction, ease, Use on every cut, Back to a plain cut
- Clip menu: Freeze this frame (⇧F), Reverse and Replace clip, beside Split, Duplicate and Delete
- Playback section: Reverse switch, Freeze this frame and the hold length
- Holds show a snowflake badge, reversed clips a Reversed badge; their sound lane says why it's muted
- Beats section for music: Find beats, tempo and count, Snap to beats, Cut to the beat with every bar, beat or 2 bars
- Beat ticks on the Audio lane, taller on each bar; scene edge drags snap to beats with a tip
- Caption style: Animation tiles (None, Highlight, Pop, Both, Typewriter), Highlight color, a preview that plays
- Look row for clips and image fills: swatches of its own frame, amount, what it's built from, Use on every clip
- Look badge on clip bars; duplicated scenes start with a plain cut

#### Wikimedia Commons in the Media tab

- Free to use lists Wikimedia Commons next to Openverse, which stays the default
- Commons searches All, Images, Sounds and Video; Openverse's Video says it has images and sounds only
- Video results are poster tiles with their length, and drop on the canvas, a shape or the timeline with their credit
- Sound rows draw flat without a waveform; slow line and unavailable card name the source
- Window calls move to free:* and route by url; verify-commons.ts drives a fake Commons and --live

#### Wikimedia Commons as a public domain source

- commons.ts searches images, sounds and videos, CC0 or public domain only via structured data
- Licence and restrictions are checked at search and again at import, like Openverse
- Videos come from the largest VP9 WebM transcode up to 1080p and 500 MB, never the original
- ingestAsset takes commons: image and sound urls; find_media searches Commons by default and lists videos
- safeFetchAsset takes a user agent, for Wikimedia's client policy

#### WebM files get shared copies

- packages/doc webm.ts demuxes VP9/VP8 and Opus into the same movie the MP4 reader gives
- probeFileAsync reads WebM too, so the existing VP9-capable transcode makes its H.264 copy
- Laced blocks leave their track unread; agent snippets still refuse WebM by name

#### Folders for everyone, lit drop lanes, folder sound waveforms

- Your files and Add a folder… show in the Media tab for everyone; Nextcloud (Connect a library…) stays an early feature
- A sound dragged over the timeline lights the audio lane, where it lands, even over the Main track
- A clip or image dragged over the Main track or the audio lane lights the Main track
- The lit lane clears when the drag ends
- Sounds from a folder show their length and waveform

#### Agent calls, captions and beats for the CapCut extras

- SetTransition, UseTransition, FreezeFrame, DetectBeats and CutToBeat in execute
- DetectBeats decodes the music in the media window and lands beats, bpm and downbeat on the clip
- MP4 captions and the caption preview share one caption kernel; highlight, pop, both and typewriter burn in
- Motion, voiceover and execute guides document transitions, reverse, looks, freeze, beats and caption animation
- verify-extras.ts exports a composition with every extra and checks its frames

#### Decode reversed clips without starting over each frame

- ClipDecoder keeps the eight frames before a backward ask as bitmaps, freeing the decoder's own
- 90 reversed frames in GOPs of 30 decode 247 frames instead of 1395

#### Draw transitions, looks and reverse everywhere

- Canvas, screenshots and MP4 frames sample each scene's transition part at draw time
- Zoom blur and glitch run the scene through a runtime shader; light leak screens a warm glow; whip smears on one axis
- Looks join adjustments in one color matrix on image and video fills; image looks bake into HTML, SVG and React
- HTML export plays transitions with the runner's kernel and seeks reversed clips frame by frame
- Kitchen-sink composition gains a crossfade transition, a teal look and highlighted captions

#### CapCut extras data model

- Transitions stored once on the incoming scene (motion.transition), 11 kinds, sampled at draw time
- Main track keeps each transition cut overlapping by its length, capped at half the shorter scene
- Use one transition on every cut; legacy keyframe transitions read and upgraded
- Reverse flag on clips: source runs backwards, sound muted, splits stay continuous
- Freeze frame insert: split and hold the cut's moment (1 s, or a bar with beats)
- Beat detection from samples, beats on music clips, snap and cut to the beat
- Caption animations (highlight, pop, both, typewriter) with per-word timing and a shared caption kernel
- Eight looks built from image adjustments, with an amount

#### Double-click a marker to rename it

- Enter or a click away renames it, and every layer and clip timed to it follows, offsets kept, in one undo step
- Spaces become underscores; a name that's taken or can't be a marker stays red; Escape keeps the old name

#### Nudge a reframed clip's crop on the canvas

- Crop mode opens on a clip layer and shows the frame at the playhead
- On an Auto reframe clip a nudge pins that scene's crop, which reframing never moves
- verify-clip-editing.ts drives the clip editing UI over real footage, with throttled timeline timings

#### Clip bars, clip sound, the clip panel and Make it a video

- Clip bars show a filmstrip of the source moments they play, a speed badge (30×, 0.5×, Curve, Freeze) and Sharing 42% or Up next while a copy is made
- Trim a clip from either edge of its bar; the tip shows the new in or out point and the change, later clips move along
- A Clip sound lane under the Main track draws each clip's waveform, or why it plays silent
- The clip panel: start and length, in and out in the source, Speed (presets, custom, curves with an editable Custom curve), Sound (volume, mute, Duck under voiceover), Media (the file and whether everyone has it) and Fill the frame
- Auto reframe finds each scene's subject from stills and crops around it; crops nudged by hand stay
- Make it a video turns a frame into a composition at 16:9, 9:16 or 1:1, 1080p or 4K
- The Composition section picks its size from the same menu, or a custom one, and its frame rate as 30, 60 or Other
- Video files dropped on the canvas or the timeline land at once; their shared copies are made in the background
- A Split button in the timeline toolbar; narrow docks drop the frame number instead of cutting off the time; narrow clip bars keep their name

#### Clip editing data and media reads

- Trim, retime, speed curve editing and reframe crop helpers in packages/doc video.ts
- Speed curve presets tuned to keep about the clip's length; presets scale with a sped-up clip
- A person can unmute a sped-up clip (muted: false); duck: false keeps a clip's sound under voiceover
- Composition sizes: 16:9, 9:16 and 1:1 at 1080p or 4K (video-sizes.ts)
- Main reads filmstrip stills, a clip's file details and peer sharing progress, and imports dropped video files

#### See the work agents did, not just their tokens

- Runs in Autopen count their tool calls (subagents' too), how long they worked, and whether they failed
- Undoing a finished run counts it as undone
- New Tool calls tile, and a card for where the work happened: in Autopen beside outside sessions
- The chart shows tokens, runs or tool calls, split by person, where it happened, or model
- Agent runs card: how runs ended, agent time, average and longest run, cost per run, cache share and models
- People table: runs, calls in app and outside, tokens and agent time; open a person for their own page
- Boards table gets a Calls column; a board's page gets the chart, runs card and new people table
- Faces: each person's profile photo, else their Gravatar from the organization's list, else their initial

#### Timeline drops go through the Timeline's own drop API

- Sounds, folder videos and images dropped on the timeline are copied onto the board, then placed by dropOnTimeline
- The lanes light up under a drag from the Media tab
- A folder video dropped on the Main track becomes a scene
- A music clip's bar ends with a shorter sound unless it loops
- Agents' Openverse client and the Media tab follow keys connected in Settings

#### The 1080p note names clips whose originals aren't on this Mac

- The Export dialog asks main which clips in the export lack their original here, and shows the note above 1080p
- Who added a clip isn't recorded, so the note says another Mac

#### HTML exports play clips as <video> in step with the timeline

- A video fill becomes a muted <video> layer the motion runner plays at its speed, seeks while paused or past 16x, and stops outside its layer's window
- Speed curves are sampled across their layer; crops, Fill the frame and adjustments are warned about
- Clips' shared copies are written beside the page, or inside a one-file page up to 50 MB
- Layers with only a time window now come and go in HTML exports, as slideshow photos do on the canvas

#### Clips play on the canvas, and compositions keep only what is near the playhead

- A residency manager decodes the images and clip frames a composition draws from its playhead to half a second ahead, lets the rest go, and shows the exact frame when paused or sought
- A 300-photo slideshow past the image budget now plays sharp to the end, holding about 60 MB instead of every photo
- The canvas decodes each clip's shared copy with WebCodecs from samples main reads off disk; frames reach CanvasKit as GPU bitmaps
- A frame still decoding draws the nearest decoded one instead of a gap
- A clip's sound plays with canvas playback at its speed, ducked under voice
- Verify-clip-canvas checks frames on screen, sharpness, colors, sound, and measures playback at full speed and 4x throttled

#### exports, screenshots and filmstrips decode each clip's exact frames

- ClipDecoder (packages/viewer) decodes a clip's frames by index with WebCodecs, going on from the last frame and jumping to a later keyframe instead of decoding through
- Main's hidden media window keeps a decoder per clip for main's and the agent process's renderers; the original when this Mac has it, else the shared copy
- A clip's sound joins the export mix at its speed, ducked under voice; muted, frozen and sped-up clips stay silent
- The export result lists clips drawn from the 1080p shared copy, with a warning
- clipTrackOf, frameTimes, clipSounds and ADTS wrapping in packages/doc
- Verify-clips checks every exported and screenshot frame against the bars the test footage spells, 20 clips back to back and the timelapse scenario

#### Video fills draw the exact source frame

- A video fill paints like an image fill: mode, crop, adjust, opacity, blend, on any shape
- Fill the frame: reframe crops per shot, blur, color or image behind a fitted clip
- frameIndex picks the last frame shown at or before the source time sourceTime gives
- Decoded frames sit in the image cache by frame key; exports, screenshots and filmstrips decode only what each frame draws
- renderFrames names the clips drawn from a shared copy; a clip the device lacks is listed missing

#### The Media tab replaces Images

- Media tab for everyone: Your files, Free to use (Openverse) and Stock (Unsplash) in one grouped menu
- One search box and a type filter: All, Images, Sounds, Video (Video from your own folders)
- Public domain images with badge, credit and a details popover; sounds as rows with play, waveform and length
- Slow and timed-out states for Openverse, nothing found, and Unsplash needing a key
- Drag onto a shape, the canvas or the timeline; double-click adds in view or at the playhead
- Replace on an image fill and a music clip, keeping crop and timing; a Loop toggle for shorter sounds
- Credits from Openverse and Unsplash stay on the fill or clip

#### Openverse browses and draws waveforms; folders hold sounds and videos

- An Openverse search with no words lists popular public domain results
- Results keep their file and size for previews, and peaks() reads a sound's waveform
- Folder libraries list and search sounds and videos when asked, and give a video's file path
- Image fetches no longer get a 406 from Openverse previews

#### A music clip can loop its sound to fill the clip

- AudioClip.loop repeats the sound from its trim until the clip's length (or the composition's end)
- Without it a clip ends with its sound, so a shorter replacement ends the clip early
- Playback, MP4 export and the motion guide all follow the loop

#### One Timeline with the Main track, overlay lanes and rows that open in place

- The motion dock is Timeline | Transcript; Scenes, Layers and the Ripple toggle are gone
- Main track: always ripples (trim, reorder, insert, delete), Alt on a scene's edge runs it into the next, + adds a scene
- The composition grows when the Main track runs past its end; it never shortens by itself
- Overlays sit in lanes packed by stacking order, pinned to the clip under their start, with a pin dot and line
- Dragging an overlay re-pins it to the clip it lands on, or moves it to another lane or New overlay lane
- Scenes and overlays open in place to their layers, animation chips (In, Out, Loop) and keyframe rows, several at once
- Animated only filter; an open scene shows 8 rows then scrolls inside itself ("N more layers · scroll")
- A layer picked on the canvas opens its rows and scrolls to them; double-clicking a scene zooms to it
- ⌘B splits the selected scene or overlay (or the scene under the playhead); a clip's footage starts at the cut
- Scene menu: Duplicate ⌘D, Split at playhead ⌘B, Add scene after, Transition in…, Ask about this scene ⌘J, Delete
- ⌘D and Delete on a selected scene ripple while the dock is open
- The Timing panel shows "Attached to <clip> · Starts 1.0s into it; moves with it" with Detach
- dropOnTimeline and the application/x-autopen-media drag type put sounds, clips and images on a lane
- Pure helpers in sequence.ts: insertScene, deleteScene, clipAt, pinTo, detachPin, packLanes, stackIndexFor, splitLayer, pinsAfterSplit
- Spans resolve pins and are cached per edit; playing redraws only the playhead and time, not the lanes
- verify-timeline.ts and perf-timeline.ts; verify-motion, verify-video-layers and verify-voiceover-ui follow the new dock

#### Agents ask to read a folder, and Settings › Claude lists the folders

- When ImportMedia can't read a folder, the agent asks in the pane: Allow this folder, Only for this request, or Don't allow
- The card shows the folder, its drive and what's in it; your answer applies before the agent tries again
- Settings › Claude lists folders agents can read, every board's, with who allowed each and when, a board filter and Remove
- Agents never ask for a whole disk or home folder

#### Connect your own Openverse keys in Integrations

- An Openverse card in Integrations: works without a key, fewer results until connected
- Connect registers an app with Openverse from your email, then flips to Connected on its own once the emailed link is clicked
- Resend and Cancel while waiting; Replace and Disconnect once connected; paste keys you already have
- Keys are sealed in the keychain and every Openverse search uses them, agents' too; no keys are built into Autopen

#### Music on the timeline, and markers you can delete

- Add music drops a track at the playhead on its own audio lane; drag clips to move them, and Backspace removes one
- The music panel has a Remove button
- A selected marker can be deleted; layers and clips that started at it keep their moment

#### Emoji draw in color

- Text with emoji draws them with Noto Color Emoji on the canvas, in exports and on the phone and web viewers
- The emoji font loads only once some text on the board has emoji

#### Shared copies of videos made in a hidden window

- ImportMedia's videos become 1080p H.264 with AAC: decoded, turned upright and scaled, hardware encoded, muxed to disk as they go
- H.264 that already fits is copied without decoding; PCM and Opus sound become AAC; the recording date carries over
- Stills for ExtractFrames decode each keyframe stretch once, from the original when this desktop has it
- Each board keeps its copies in a media folder, fetches the clips it uses in the background, and takes another board's copy by hard link
- Per-board allowed folders, with IPC and window.autopen calls for Settings › Claude to list, add and remove them
- Verify-media checks it all in the app against ffmpeg's view of the originals

#### Footage syncs peer to peer in windows straight to disk

- MediaExchange asks for 4 MB windows, two in flight, answered in 192 KB chunks read from disk
- The whole file is checked against its hash; a bad one is dropped and asked for again
- One holder answers each window on a relay room; viewers ask but never answer
- The relay passes media frames along and keeps none

#### ImportMedia, VideoInfo and ExtractFrames for agents

- ImportMedia brings images, sound and video from allowed folders by path, glob or list, one entry per file in name order
- Images and sound land as assets at once; videos and images maxSide shrinks get pending urls that become their copies
- A folder outside the allowed ones is refused by its spelling alone and names the folder to allow in Settings › Claude; inside, every failure reads the same
- Allowed folders can differ per board; a local path or http(s) link in a video fill becomes its shared copy
- VideoInfo reads a path, a pending import or a copy on this device; ExtractFrames queues stills
- MediaStore, the originals index and MediaHost for hosts that can decode

#### Video sniffing and an MP4/MOV reader

- sniffVideoType tells MP4, MOV and WebM from images, songs and HEIF stills
- packages/doc/mp4.ts reads the movie box before or after the media: tracks, WebCodecs codec strings and decoder descriptions, sample tables, edit list start, rotation, recording date
- VideoInfo shape and the shared copy's size (long side at most 1920, never larger, even)
- Video fills' urls count as asset urls; videoUrlsOf lists them so footage can sync apart
- Tiny fixture clips: H.264 with AAC, HEVC turned in a MOV, movie box at the end, WebM, M4A

#### Video size, frame rate, codec and quality

- Size: Frame size, 720p, 1080p, 1440p or 4K, drawn at scale so a 1080p composition is sharp at 4K
- Frame rate: 24, 25, 30, 50 or 60
- Codec: H.264, or HEVC where this computer encodes it, at the right level (4K60 H.264 is 5.2)
- Quality: Draft, Good or Best instead of a bitrate
- MP4s are written to disk as they encode, with their index up front; cancel leaves nothing
- The Export dialog remembers your last video settings; quick export and deck export use them
- Agents: Export(comp, 'mp4', path, { size, fps, codec, quality, captions, voice, music }), checked with clear errors

#### Animation cards and a key toggle on every animatable field

- The right panel's Motion section lists one card per animation: grip to reorder, name, In/Out/Loop, length, eye to turn it off, delete on hover
- A card opens to At, Length, Distance, Direction (wipe reads From Left/Right/Top/Bottom), Ease with spring Bounce and Stiffness
- Type cards pick by letter or word; Count cards edit From, To, Decimals, Before/After text and the thousands separator
- The + menu adds animations grouped In, Out (with Untype and Count down) and Loop, plus Ask an agent
- A group's card staggers its children; a child shows it read only with a link back to the group
- X, Y, Rotation, a new Scale field, Opacity, Corner radius, Fill, Stroke, Shadow and Blur each get a key toggle
- Editing an animated property keys it at the playhead; Record keys is gone from the timeline toolbar

#### clips, speed curves, overlay pins and animation switches in the data model

- A video fill puts footage on any shape, with in, speed or a speed curve, volume, loop and Fill the frame
- Speed curve presets (Montage, Hero, Bullet, Flash) keep the whole clip and change its length; sound mutes above 2x
- A freeze frame is the same clip held at one moment, so it keeps its look and exports exactly
- Titles and stickers pin to the clip under them and follow it when the Main track moves, on the canvas and in HTML export
- Animations can be turned off without deleting them, and Count starts from any number and counts down on the way out
- Agents get clear warnings for a bad clip, a pin that can't play, and a freeze frame with no length

#### Agents find and place public domain images and sounds

- find_media searches Openverse for CC0 and public domain images and sounds from sources that review licences
- Agents place openverse: urls in image fills and audio clips; each is checked again and copied onto the board with its credit
- Stock photos without an Unsplash key come from public domain Openverse photos
- Audio clips from a web address now land on the board instead of staying pending

#### Animations stay editable after they are applied

- Layers keep named animations (rise, pop, wipe, pulse and more) with their timing, distance and direction, worked out when drawn instead of baked into keyframes
- Entrances, exits and loops combine on one layer; a stagger on a group plays on each child in turn
- The canvas, video export and HTML export all play them
- Agents write animations by name, and get a clear warning for one that can't play

#### New Features

- Keep track of who signs in
- Admins see everyone who signed in

#### A call that only reads no longer copies the whole board

- A call reads the live board and makes its staging replica only at its first write
- Get visitors, screenshots, Print, Pages and exports on a new session copy nothing
- On a 97k-node synthetic board, a read-only call in a new session went from 1.2 s and 410 MB of heap to 0.3 s and under 1 MB

#### Copied text pastes into other apps, pictures paste into the selected box

- Copying a text layer copies its words too, linked words followed by where they go
- Pasting a picture with an image box selected fills the box at its size, keeping its crop

#### A clip that arrives late plays without reopening the board

- The canvas now decodes a clip that lands after its composition was drawn, peer to peer or from the relay
- verify-footage.ts: two desktops and a local relay with local R2, end to end

#### Look row lays out, Replace clip for everyone

- Look name and Amount slider sit on one line instead of stacking
- Replace clip… shows whenever you have a folder library

#### Text keeps its exact look while you edit it

- The canvas draws the words as you type; the editor shows only the caret and highlight
- Clicking into a text no longer changes its weight or shifts it
- Typing past the panel edge no longer scrolls the canvas aside
- Japanese and Chinese composition still shows while composing

#### Editing breaks lines exactly where the canvas does

- Clicking into a text no longer moves a word to another line
- The editor loads the same font file the canvas draws with, uploaded fonts too
- The editor no longer picks up the interface's font features

#### Only known decoration styles reach exported CSS

- A made-up decorationStyle on a board can no longer inject CSS or markup into HTML and SVG exports

#### A clip after a transition opens again

- A transition's drag edge covered the next clip's open triangle and name; it now sits over the filmstrip only

#### The app's stylesheet builds again

- A pressed-toggle selector had landed inside the bound-field rule, which broke the CSS build; it's back with the other pressed toggles

#### Typography card back to two sentences

- Drops the note about the dimmed Italic button

#### Follow pages, steady text editing, real font faces

- Following someone takes you to the page they are on
- Editing text no longer opens an empty, collapsed box
- Black and other heavy weights draw the font's real face
- Font style picker lists every face the font has, italics included
- Italic toggle next to Underline and Strikethrough
- Text toggles show when they are on
- Agents lay out posters, posts, slides and ads freely, auto layout for UI

#### The clip panel's length note sits inline again

- "later clips move" after a speed change no longer shows as an empty box on its own line

#### A video dropped on the board plays

- Dropped anywhere but inside a video, a clip becomes a video of its own, the clip's size and frame rate, so it shows its frame, plays and exports instead of sitting there blank
- Several files dropped together play one after another in that video

#### The Ask box is styled again

- Its text box had lost its look when the agent's message box moved to a formatted editor; it sits in the frame like the agent's again

#### Extras verified end to end in the app

- Zoom blur and glitch sample the scene where it sits, not at the board origin
- MP4 captions run the caption kernel, so highlight, pop and typewriter burn in
- Freeze frame settles the next transition against the rest of the clip
- Cut to the beat leaves room for both transitions in every scene
- verify-extras.ts passes: reverse exact, looks, freeze, transitions, captions, screenshot equals MP4

#### Board compaction can no longer crash the app

- Compaction collects in its own utility process, not a worker thread: the worker shared main's 4 GB V8 heap and aborted the whole app with "young object promotion failed" on big boards
- If the compaction process dies, the board is saved as it is and a line goes to main.log
- Closing a board with nothing new since its snapshot skips compaction
- scripts/verify-compaction.ts compacts a board while main's heap is nearly full

#### The transition picker closes when you click away

- A click outside the picker or Escape closes it, like the timeline's menus; clicking another cut still switches to it

#### The transition picker opens at the cut you clicked

- It sat above the whole dock, far from the Main track now that the track is at the bottom; it now opens at its cut, above or below as the window has room

#### Exports check where a folder really is

- /private/tmp is accepted like /tmp, since it's the same folder
- A symlink inside an allowed folder can no longer lead an export outside it

#### The play bar runs the whole video when the Main track is shorter

- Time no scene covers, such as overlays playing on after the last scene, shows as a plain stretch of the bar you can scrub, instead of empty space

#### Add voiceover keeps its text white on hover

- The lane's border and tint still turn the voice color; the label stays readable like Add music's

#### A scene's or overlay's menu opens where you right-click

- At an interface size above 100% the menu opened down and to the right of the pointer

#### The environment note stays with the Claude settings it explains

- On Settings › Claude, "Some of these are set by environment variables" sits above Folders agents can read instead of under it

#### Every video setting fits its column

- The Captions choices no longer run off the edge of the Export dialog; the segment labels shrink to fit

#### A frame's stagger can be edited in the panel

- A frame's animation card has a Stagger field, so a frame an agent staggered can be retimed
- On a frame it plays on the frame itself until a stagger above 0 is set; a group still staggers by default

#### Folders are added and removed in the Images tab

- Each folder in the Images tab's source menu has an × to remove it, and Delete removes the highlighted one
- Settings, Integrations lists photo servers only

#### Conversation files open from the agent's menu

- The paperclip button in the agent pane's header is gone; Files… is in the menu on the agent's name

#### Plan names follow the Max and Ultra rename

- 5x Max shows as Max and 20x Max as Ultra

#### Video frames always go through the canvas

- Raw-byte VideoFrames used 230 MB more at 4K for the same speed
- The dialog keeps HEVC picked while it checks this computer can encode it

#### A board main lets go of is freed, instead of a whole copy kept per reopen

- Closing a board destroys the awareness it made, whose renewal timer kept the doc alive
- Closing a board drops main's layouts of it, held by an export or a share link's copy
- A background agent working on a board no window shows has main reopen it when calls are over 6 s apart: on the 97k-node Autopen board main kept 340 MB per call (379 MB to 3.1 GB in 8 calls) and ran out of heap; now it holds 38 MB between calls

#### A slow Openverse gives up cleanly instead of hanging

- A search gives up after 20 s with a clear error to try again or use another source
- A gateway error is tried once more while time is left
- Recent searches come back from memory, and the same search running twice is asked once

#### Staging replicas no longer pile up until the agent process runs out of memory

- A session lets go of its staging replicas when it ends, and a failed call's at once
- The layout cache drops a replica's or mirror's layout when it goes, instead of holding the last 8 whole boards
- On the 97k-node Autopen board, 24 per-call MCP sessions held the agent heap at 339 MB, where it climbed 310 MB per edit to an OOM

#### A composition's end shows its last frame

- A layer that runs to the end of a composition still shows when the playhead or a filmstrip sits at the end

#### Agents can export to temp folders

- Export writes under the temp folder and /tmp as well as home, so an agent can check its own output

#### Long slideshows export sharp

- Export, screenshots and filmstrips decode only the images each frame draws, so hundreds of photos stay inside the image budget
- Export says how many images it drew below full resolution when one frame alone runs the budget out

#### Unknown fill types are refused

- Insert and Update refuse a fill or stroke type nothing draws, like video, and list the ones that work

#### Agents stop asking which style on a new board

- A board with no style gets plain, neutral designs without a question
- The style card shows only when someone asks for help choosing

## 0.1.55 (2026-11-03)

#### Figma stroke settings, layout guides, new effects and panel polish

- Stroke: Position and Weight row, settings popover with Basic (dash, cap, join,
- Layout guides: grid, columns and rows per frame, drawn in the editor only, ^G toggles.
- Effects: noise, texture, glass and shader, in Figma's menu order. Glass
- Panel: Artboard is its own section with a checkbox, speaker notes under

#### Org view shows cloud voices and everyone, non-admins see only their own

- Voice tile, column and note in the organization's view
- People list of everyone in the organization's view, the same table as a board's page
- Someone at a company who isn't an admin sees only their own devices' usage, from every computer they use

#### Team usage merges reports and keeps voice and key costs

- PUT /usage merges into stored totals, keeping the larger of each field, so a report may carry only some keys
- Reports may carry voice costs and per-key dollars alongside Claude counts, each checked against the device and board
- Totals live one row per key in usage_entries; the usage row keeps only the device's name, boards and report time
- GET /usage/mine shows anyone signed in their own devices; GET /usage stays admins only
- Rows stored whole by older clients move into entries at startup
- Desktop directory client gains usage.mine

#### Figma-style right panel

- One row per paint and effect, effect popover, short nothing-selected panel
- Nothing selected: Board name, one Variables row that opens the manager, Export.
- Frame head with align row and artboard toggle; Position with rotation and turns; Auto layout with
- Fill and Stroke: one row per paint (the color picker's paint field, then eye and minus). The swatch
- Effects: one row per effect; the row opens a popover with type, blend, position, blur, spread and a
- Export opens the Export dialog on the selection or the page; the dialog loads on first open.
- Help cards: Frame, Appearance and Export replace Layer, Artboard and Corner radius.
- scripts/verify-right-panel.ts covers the new panel; verify-properties, verify-themes, verify-help-panel,

#### Files sent in a conversation open again from the thread

- A file dropped or attached in an agent chat is now kept with the board on your computer, so it still opens after the original is moved or deleted
- Click an attachment in a sent message to open it, or an image to see it large; right-click for Open, Show in Finder or Explorer, and Save as
- Attachments waiting in the composer open or preview on click too
- New Files list in the conversation header (and its right-click menu) shows everything sent in that conversation
- Sent attachments only ever open files Autopen kept or that you picked yourself, never a path written into a message

#### Link words inside a text

- Highlight words while typing in a text and press Ctrl+K, or right-click and pick Add Link, to link them to a web page or to a frame or page on the board
- The link field suggests the board's frames and pages, and turns allbulkfoods.com/flours into a full web address
- With the caret in linked words, a bar shows where they go, with Open, Edit and Remove
- Linked words look the same as the words around them, as in Figma; hovering them on the canvas names the link
- Clicking a link while presenting, or in a shared view link, opens the web page or goes to the frame
- HTML, React and SVG exports keep the links
- Figma imports keep links on part of a text, and a link on a whole text layer
- Agents can link words with StyleText's href

#### Style part of a text layer, as in Figma

- Highlight words while typing in a text and press Ctrl+B, Ctrl+I or Ctrl+U to bold, italicize or underline just them
- With words highlighted, the properties panel sets font, weight, size, letter spacing, underline, strikethrough and color on those words only; the text stays open and the words stay highlighted
- The panel shows Mixed where the highlighted words, or a whole text, differ
- A style set on a whole text layer applies everywhere in it, as in Figma
- Each style change is one undo step, and undo while typing steps back through them
- Typing, pasting and Change Case keep each word's style where it is
- Text with mixed styles draws, wraps and sizes itself correctly on the canvas, and exports as styled spans to HTML, React and SVG
- Figma imports keep mixed text styles instead of flattening them to one
- Agents can style part of a text with StyleText
- New help guide: Style part of a text

#### Format your message as you type it

- The agent message box takes formatting: Ctrl+B bold, Ctrl+I italic, Ctrl+E or backticks for inline code, Ctrl+K to link selected text (Cmd on Mac)
- Typing "- " or "* " starts a bullet list, "1. " a numbered one, "> " a quote and ``` a code block
- In a list, Enter adds the next item, Enter on an empty item ends the list, and Tab or Shift+Tab indents
- Pasting from a web page or document keeps bold, italic, lists, links and code; pasted markdown keeps its formatting too
- Your sent messages show formatted in the conversation, and the agent receives them as markdown

#### Every Google font, your installed fonts, and Upload font, kept with the board

- The font picker lists the whole Google Fonts catalog, searchable, and stays quick by drawing only the rows in view
- Fonts installed on your computer show in the picker too, each in its own face; picking one stores it with the board so everyone sees it
- Upload font in the picker adds TTF, OTF, TTC, WOFF or WOFF2 files to the board and sets the selected text in it
- Drop font files on the board to add them; selected text switches to the new font
- Collaborators, view links, shared links and exports draw text in the board's own fonts
- The weight list follows the weights each font actually has

#### Place images from a network share, a file or a web address

- Place image (toolbar, File menu, right-click menu, Ctrl+Shift+U) opens the file picker, network locations included; with a shape selected the image fills it
- The Images tab can add a folder on this computer or a network share (\\server\share, mapped drives) as a library to browse, search and drag from
- Settings, Integrations adds a folder by picker or by typing its path
- Pasting an image's web address or a file's path, such as Explorer's Copy as path, places the image
- Dropping one image file on a shape fills it; a link dragged out of a web page places its image

#### Pop the agent conversation out into its own window

- Pop out in the conversation header moves a board's chat into a window of its own, to keep on another screen while the board stays in view
- The sidebar folds to its rail while the chat is out; the Agent tab says where it went, with Show window and Bring back
- Closing that window, or Dock in it, puts the chat back in the sidebar
- The popped-out chat stays live: messages stream in, sending and attachments work, it offers the layers selected on the board and anchors to the page open there
- Clicking work an agent did in it goes there on the board
- It reopens at the size and place it was left, on whichever screen

#### Layer blend modes, as in Figma

- Blend mode now works on any layer: Multiply, Screen, Overlay, Color burn, Color and the rest blend the whole layer with what is beneath it
- The blend mode menu sits beside Opacity in the Layer section, in Figma's order and names, and shows Mixed across a selection
- Frames and groups pass their children's blending through by default; set one to Normal to keep that blending inside it
- Layers that blend on the board blend with each other, never with the canvas behind them
- SVG and HTML exports keep layer blend modes, and Figma and web imports bring them in on the layer instead of its fills

#### Change letter case from the panel or a text selection

- Typography has a case control: UPPERCASE, lowercase, Title Case and Sentence case, for one or many text layers at once, one undo step
- Highlight words while editing text and right-click for Change Case to convert just those words
- Alignment icons in the properties panel no longer shrink to dots in a narrow panel

#### Drag several layers at once in the Layers panel

- Dragging a selected row in Layers carries every selected layer, keeping their order, with a count while you drag
- Dropped into a frame or group they keep their place on the canvas, unless it uses auto layout
- The whole move undoes in one step
- Bring forward, send backward, to front and to back keep several layers in their order
- Ctrl+Shift+] and Ctrl+Shift+[ also bring to front and send to back

#### Preview an image before exporting it

- Export has a Preview row for PNG and SVG that shows exactly what the file will hold, hidden layers, masks and effects included
- The preview follows the chosen format and scale, and redraws a moment after the design changes
- With several layers, it shows the first and says how many there are

#### A milestone shows the person it was made for

- A milestone with no agent on it, such as one marked from your own terminal, now shows the person's avatar and name in the Milestones tab
- New milestones record who they were made for and sync that to everyone on the board; older ones show as before
- list_milestones names that person, so agents can tell whose work a milestone was

#### New Features

- One color picker for every swatch, with paint types and variables, as in Figma
- Video is greyed out on a page with no timelines
- Export dialog with Image, Document, Video and Code tabs
- Every font in the picker is drawn in its own face, as is the family in the field

#### Stroke and Speaker notes info cards stay two sentences

- The right panel's Stroke and Speaker notes info cards fit the two-sentence limit again

#### Every signed-in device reports usage, voices and key spend as merged deltas

- Non-admins report too: sending uses Directory.reportScope, viewing keeps teamScope
- Reports merge per key at the most of each number (mergeDeviceUsage), so usage on deleted boards stays counted
- Only changed keys go, at most 3000 a request, remembered in team-usage-sent.json; a new account sends everything
- A failed report is logged and tried again soon
- Reports go when this device's own usage or voice costs change on a board, and on sign-in
- Reports carry cloud voice costs and what each key paid for per board and month
- Outside tool calls count on boards that aren't open
- Company key caps count the person's spend on all their devices (DirectoryUsage.mine)
- usage:mine gives non-admins their own devices' usage

#### Hidden frames stay out of exports, and one bad frame no longer fails the batch

- Hidden frames, and layers inside hidden ones, are left out of PNG, JPEG, video, SVG, PDF and code exports, with a note naming them
- Hidden artboards inside a section no longer show up in the Export list, Present or PDF pages
- A frame that can't be drawn is skipped and named; the rest of the export still saves
- Notes about what was left out show after the export finishes

#### A board opens centered on its content the first time

- Opening a board you were invited to waits for its layers to arrive, then zooms to fit them, including ones that land a moment later
- A page's view is only remembered once its layers have loaded, so an empty first look is never brought back
- A remembered view that shows none of the page zooms to fit instead
- Switching to a page for the first time fits its content the same way

#### Frames set apart inside a holder frame show their names

- Frames spaced apart inside a top-level frame with no auto layout, clear of its edges and of each other, show name labels like screens in a section
- Click one of these names to select the frame, double-click to rename it; the names hide when zoomed out too far to fit
- The agent and the Artboards guide now explain which frames show a name on the canvas

#### Exported pages and SVGs never carry a script link

- HTML, React and SVG exports drop any link that isn't a web, mail or phone address, a relative path, or a place on the board, such as a javascript: link

#### Annotate toolbar clears the Windows window buttons

- On Windows the annotate toolbar's buttons sit below the minimize, maximize and close buttons instead of under them

#### Favorites stays open unless you shut it

- Favorites in the Home sidebar starts open on every page, including inside an account
- Shutting it is remembered on this computer until you open it again

#### New conversation is always the last button in the conversation header

- Pop out and Dock sit just before New conversation

#### A link dragged out of a web page only reaches the public internet

- An image link dragged in from a web page can no longer point at the office network or a file path
- Pasted addresses and paths, the file picker and dropped files still reach network shares

#### PNG files come out at the full size of the picked scale

- A PNG export is now as large as the scale asks, so a 1920 px frame at 2x is 3840 px wide; it was never more than 1000 px
- Copy as PNG is full size too
- An image too big to make (over 16384 px a side or 64 megapixels) says so and asks for a smaller scale

#### Every action undoes in one Ctrl+Z

- Ctrl+Z, Ctrl+Y and Ctrl+Shift+Z on Windows and Linux are handled by the board itself, so undo always reaches it
- Undo still works on the board when a checkbox, slider or color swatch has focus
- Each command is exactly one undo step, however quickly the next one follows
- A drag, resize or rotate stays one undo step even when you pause mid-drag
- Dropping a layer into a frame, and an Alt-drag copy, undo in one step with their move
- Holding an arrow key nudges as one undo step
- Dragging a color picker on the canvas bar, a mesh gradient or a color variable is one undo step

#### Right-click menus near the bottom of the window open upward

- A right-click menu opened low in the window flips up so every option shows, instead of running off the bottom
- Applies to every menu: Home folders and boards, the canvas and layers, pages, tabs, and agent conversations
- Submenus move up to stay on screen, and a menu taller than the window scrolls

#### Mouse back and forward step through library folders

- The mouse's back and forward buttons (and Alt+Left/Right, or a keyboard's Back and Forward keys) now go back and forward through the folders you opened in the Images panel
- They step the in-app browser's pages too while it's open
- They never send the whole window away from the board you're on

#### Grouping layers from an auto layout frame keeps them intact

- Images and rows that fill an auto layout frame keep their size when grouped instead of collapsing or reflowing
- Ungrouping them puts them back filling the frame, as they were before

#### Fixes

- Swatch edge rings follow the swatch's rounded corners
- The Fill card stays two sentences
- Tabs sit centered in the header with their icons, as designed
- Setting segments fit their labels, so the text sits centered

## 0.1.54 (2026-11-03)

#### A person's cursor shows only on the page they're on

- Someone on another page no longer leaves a cursor on yours, so a duplicated page can't look like a shared one that stopped syncing
- People on older apps, which don't say their page, still show as before

## 0.1.53 (2026-11-03)

#### Clipping masks, as in Figma

- Use as mask (⌥⌘M, or right-click) wraps the selection in a Mask group; its bottom layer masks the rest
- One layer selected becomes a mask over the layers above it; Remove mask turns it off
- Masks clip by their opacity, so any shape works and soft fills give soft edges
- What a mask hides can't be clicked, and the mask has its own icon in Layers
- SVG export keeps masks; HTML export clips to rectangle and ellipse masks
- Masks come through from Figma files, and agents can make them

#### Autopen links itself into Claude Code and the Claude app

- Every start adds Autopen to Claude Code and the Claude desktop app, no clicks
- Claude desktop app chats can see and edit your open boards
- One Settings switch covers both; turning it off unlinks them and stays off
- Someone else's server named autopen is never replaced unasked

#### A chat stays on the page it was sent from

- Each run is anchored to the page open when its latest message was sent; get_app_state reports it as homePage
- Execute calls start on that page every time; UsePage lasts one call unless sticky, and WithPage runs a step elsewhere then comes back
- A message sent from another page moves the chat there, and the agent is told
- An agent's cursor shows only on the page it is working on

## 0.1.52 (2026-11-03)

#### A board reaches the agent process from its files, not a copy of the whole doc

- When an agent first opens a board, main sends what is stored on disk and then only what is newer, instead of encoding the whole board

#### An edit redraws only the frames it touched, even beside animated slides

- One animated slide no longer makes every edit in its section redraw the whole section
- Frames from 16 layers up get a picture of their own, so an edit to one slide leaves the others alone
- A paused animation keeps its picture through edits elsewhere instead of recording again
- A change to a parent frame, such as its theme, now redraws the frames inside it instead of leaving them stale
- Play bars read only each composition's timeline, not the whole layer, on every frame

## 0.1.51 (2026-11-03)

#### Agents run in their own process, so their work never freezes the app

- The MCP server and every agent session run in a utility process; the app's main process only applies their edits
- Clicks, typing and window drags stay responsive while an agent reads or edits a big board
- Undoing an agent's run, streamed edits and their rollback work as before
- If the agent process stops, the app starts it again and the next agent call works

#### A run's end waits for streamed pieces still loading their board

- A piece that arrives while its board is still loading can no longer land after the run ended and stay on the board

#### A cached Google font is written whole before anyone reads it

- Main and the agent process share the font cache, so a font lands under its name only once fully written

## 0.1.50 (2026-11-03)

#### Record Performance Trace, for when Autopen is slow

- Help > Record Performance Trace records every process for up to a minute, then Stop saves one zip to Downloads
- The zip holds a Chrome trace, a main-process CPU profile, and a report of the machine, GPU, memory, frame times and open boards
- Autopen now keeps a log of its own (main.log, two files at most), sent along in the zip
- profile-board.ts takes --src and --throttle to profile a real board from any app's data on a slowed CPU

#### MoJo Active brand leads the agent's style offer

- Agents ask MoJo Active first, then Built-in styles, then No style
- MoJo Active is first in the style gallery, under Company
- Colors, fonts, logo links and voice saved from the Cultivate brand guide

#### Fixed style offer, Built-in styles or No style

- Agents on a board with no style ask the same offer every time: Built-in styles or No style
- Built-in styles opens the style gallery, and the style picked there answers the agent
- No style lets the agent design plain and neutral without setting a board style
- The agent now hears the picked style's key with the answer
- Builds can add company styles (content/styles/company), offered first and listed first in the gallery

#### Side panels stop rereading the whole board on each edit

- The canvas stays smoother on big boards while an agent works
- Milestones does nothing while its tab is hidden, and formats dates without making a formatter per card
- The page row counts archived layers from an index instead of walking every layer
- The play bar reads only each composition's timeline, and finds their boxes once per redraw, not on every pan frame

#### Bullets right under the subject stay bullets

- What's new splits a commit at its first line, so bullets written with no blank line under the subject still show as bullets

#### A middle-button pan follows the pointer past the canvas edge

- Panning with the middle button keeps going when the pointer leaves the canvas or the window

#### Company style options survive the question check

- A company style offered to the agent keeps its preview instead of showing as a plain option

## 0.1.49 (2026-11-02)

#### Drafts grouped in a Drafts frame, and Cmd+P to go to a page

- Each page's drafts sit together in its Drafts frame, labeled "Drafts" with how many it holds
- Approve and Set aside work on drafts in the Drafts frame; Show archived reveals hidden ones there
- Cmd+P (Ctrl+P) opens the page picker from any tab with search ready

#### Milestone cards, and a Drafts frame on each page

- A run that marks a milestone ends with a card: a picture of the work, a short title and a two-line description
- Runs with several milestones, and the Milestones tab, show compact cards; click one to open its page and zoom to the work
- Agents give each milestone a short title
- On boards that review work, each page keeps its drafts together in one Drafts frame
- Approving a new screen moves it out of the Drafts frame onto the page

#### No special pages; drafts sit beside your work

- New boards start with one page holding the cover frame as their thumbnail; there is no Cover page
- Review first adds no pages: agents put drafts beside the screens they change, labeled Draft
- Approve swaps a draft into the old screen's place and hides the old one as archived
- Set aside hides a draft; Show archived on the page row reveals hidden screens, and Restore brings one back
- Figma files set the frame on their Cover page as the board's thumbnail
- Agents leave variables that approved screens use alone on boards that review work

#### Pages on boards

- A board holds pages; only the open page loads onto the canvas, so big boards stay fast
- The page menu above Layers opens a picker with folders on the left and pages on the right, plus search
- New page, new folder, rename, duplicate, delete, drag to reorder or into a folder
- Move layers to another page from the right-click menu, or drag them onto the page menu
- Cmd+Option+Up and Down step through pages; each page keeps its own view
- New boards start with a Cover page; its 2:1 cover is the board's thumbnail on Home
- Home cards are 2:1, and frames say Set as thumbnail
- Figma files import with their pages, divider pages become folders, and Cover becomes the cover
- Agents work on the page you have open, can switch pages, and can make, move and delete pages and folders
- Find can search all pages; Share and Present links open on your page; the web viewer and phone get a page menu
- Review boards use Drafts and Archive pages: Approve puts a draft in its place, Set aside and Restore move it to and from Archive
- Boards made with the Final, Drafts and Archive frames can be split into pages
- A board opened in a newer Autopen asks to update instead of risking edits

#### New Features

- Quick edits report in the stack, not beside the selection
- Stack of the board's agents at the canvas's bottom right
- Toolbar clearance on either side, toasts can skip a board
- Model of the agents working on a board
- An (i) beside each sidebar tab title opens its clip and guide

#### One card per page

- A milestone whose work is on several pages shows a card for each page, and each card opens its own page
- Worked out as the cards show, so work moved to another page later still lands on the right card

#### Fixes

- A quick edit's hover actions fit on its card

## 0.1.48 (2026-11-02)

#### One Integrations page for every outside service

- Images and Voices fold into Integrations: a grid of cards with each service's logo, grouped by what it powers
- Open a card for its key, monthly cap, this month's spend and on switch; connecting a key turns the service on
- Unsplash and Brandfetch can be turned off on this computer
- With a company, admins set keys from the same cards and everyone else sees them read only
- Phonon's page holds the default voice and Import voice file

## 0.1.47 (2026-11-02)

#### Admins turn early features on per person

- The directory keeps who each early feature is on for; only admins change it
- Everyone reads the features on for them; admins also see who has each one

#### Company keys, early features per person, and photo libraries

- Signed in to a company directory, the app runs only on the company's keys; admins set each key and a monthly cap per person in Integrations, and manage admins on the directory page
- Everyone else sees Integrations, Images and Voices as managed by the company, and only their own usage
- Admins turn early features on per person under Early features on the directory page; they are off for everyone else
- Photo libraries (early feature): an Images tab to browse and search a Nextcloud library, drag photos onto layers or the canvas, and agent tools to find them
- AI images use OpenAI gpt-image-2 only; Gemini is now for voices only, and stock photos need an Unsplash key
- Voice spending caps move to Integrations; Voices links there when a key is missing
- Rename a tab from its right-click menu without switching to it
- Help clips re-recorded

#### Edit links open in the app from chat and mail

- Copy link on Edit now gives a web link (autopen.tlok.dev/join/...) that chat and mail apps keep intact, instead of an autopen:// link they mangled into a broken web address
- Opening it in a browser hands the board to the app, with an Open in Autopen button if the browser asks first
- Join a board, Copy link to layer and agents take both the new link and the old autopen:// one

#### Shift-click in Layers selects the run at that level

- Shift-click adds every layer between the last one clicked and this one, at the clicked layer's level, skipping open children
- Ctrl-click (Cmd-click on Mac) still adds or removes one layer

#### Usage card hides a limit the plan doesn't report

- Plans without a 5-hour limit show only the Weekly row, not an Unknown one
- The chip by Send reads the week when there is no 5-hour limit

## 0.1.46 (2026-11-02)

#### A release never publishes without both update feeds - v0.2.23 shipped Mac-only

- Its Windows build artifact expired before a Mac rerun published
- So Windows update checks failed - Build artifacts keep for 7 days so a later rerun still has both - Publish fails if latest.yml or latest-mac.yml is missing

#### Release smoke tests take turns on the shared Mac

- Core and MoJo releases ran their DMG smoke tests at once on the mini and swapped each other's default keychain, so both failed
- A machine-wide lock now runs one smoke test at a time

## 0.1.45 (2026-11-02)

#### Edit an instance's texts, and Go to layer

- Instance content section lists an instance's texts to edit, with a reset arrow per text
- Double-click a text inside an instance to edit it in place for that instance only
- Go to layer in the right-click menu opens Layers on that layer
- Layers scrolls to the selection; instances and components wear the component icon

#### Present setup is a big dialog with titled slides

- Present opens a dialog over the board, up to 1080x760, instead of a small popover
- Slides show large, numbered and titled, grouped by section, each in its own shape
- "Drag slides to change the order" says how to reorder; Reset shows once it changed
- Escape, the close button or a click outside closes it; Enter still plays
- Snapshots take a margin, 0 for slides so neighbors don't show
- Fix the usage pace tick's CSS comment left out of the last commit

#### The usage pace tick marks where use lands by the reset

- The pace text above each bar is gone; the tick says it on hover
- The tick sits at the projected use at reset, amber when that is close to the limit
- Tooltip: "At your current pace, you'll be at 56% in 3h 4m, when it resets."
- Usage guide and clip updated

#### Shift holds a drag level until it strays far across

- Held on the line it mostly runs along, so small nudges stay level; a big stray moves freely
- Snaps only along the held line; Shift pressed or let go mid-drag applies right away
- A Shift-press on a selected layer drags the selection; a Shift-click drops the layer

#### A selected layer shows dashed lines to its frame's edges

- Like Figma: from the frame's left and top edges to the layer, through its middle
- Only for one selected layer inside a frame that places children freely
- Hidden while measuring or editing points or a crop

#### A click anywhere on an empty Fill, Stroke or Effects row adds one

- As in Figma; the + still works, and rows that already have entries ignore the click
- Verify-section-add checks each row in the app

#### A marquee from the canvas selects inside artboards it only partly covers

- Like Figma: the layers it touches inside the artboard, not the artboard; the artboard only when fully covered
- Frames holding artboards pass through the same way

#### Present and PDF export play only artboards

- An artboard is one slide or page, never split into its cards
- A frame holding artboards plays them under its title, never itself
- Export drops the option to split section frames into pages

#### Drop a layer on a frame to move it inside

- Dragging on the canvas lands layers in the frame under the pointer, outlined while you drag
- Dragged off their frame onto empty canvas, they go to the top level
- An artboard dropped into another becomes a plain frame there
- Verify-artboards drags a frame into an artboard and back out

#### A frame dropped into an artboard becomes a plain frame

- Moving into an artboard clears its Artboard setting and any inside it
- Moving into a plain holder keeps it an artboard

#### An Artboards clip for the guide and its info card

- Miles shows turning on Use as artboard for a frame inside another

#### Drop the size menu from the Artboard section

- Artboard section is the toggle and its note, no size presets
- Artboard tool still places 1440 x 1024

#### An Artboard tool, panel section and menu rows

- Artboard tool (B) in the toolbar, white fill, Desktop size on click
- Right panel Artboard section: on/off and size presets
- Frames drawn inside an artboard start with no fill
- Layers shows artboards with the corner marks icon
- Right-click Flatten, Make artboard / Make plain frame
- Export, Present and Share pick from artboards

#### Agents mark artboards and keep the tree shallow

- Flatten(id) removes wrappers that draw nothing, on request
- ctx.problems flags a redundant wrapper the call just made
- Warning when an artboard is marked inside another one
- Skill: depth budget artboard › section › row › element, no groups
- Brainstorm holders are plain frames; screens inside are artboards

#### Clicks and labels follow artboards at any depth

- Clicks pass through plain holders to the artboard inside
- Artboards inside a holder get their own name label
- Marquee starts inside the artboard under the pointer

#### Flatten removes wrappers that do nothing

- A wrapper is a frame or group with one child filling it exactly and nothing drawn
- Flatten removes them innermost first and keeps the look; artboards and components stay

#### Any frame can be an artboard

- Frames take artboard: true to be one anywhere, false to make a top-level frame a plain holder
- Top-level frames stay artboards by default; holding a marked frame makes them a holder
- Artboards don't nest: the outer one wins
- Present and PDF give a holder one page per artboard inside it

#### A component edit relays out and repaints only its instances

- Layout keeps nodes whose change only affects paint, like a component's fill
- A component edit marks just its instances and the frames above them as changed
- perf-component-edit.ts times a component edit across hundreds of instances

#### Pasted instances keep their copied component

- Instances pasted with their component on another board stayed empty: the paste dropped the new ids they pointed at
- Verify-paste-instances copies a component and its instances to a new board

## 0.1.44 (2026-10-30)

#### The directory keeps everyone's Claude usage

- PUT /usage keeps one report per account and device; GET /usage lists them all
- The MoJo directory provider reports and reads team usage for Settings > Usage

#### See the whole team's usage, and numbers stay current

- Signed in to an organization that keeps usage, Usage opens on everyone's, boards you never joined included; a picker narrows it to this computer
- Each device sends its own usage to the organization a minute after start and after runs
- Opening Usage catches closed boards up with the relay first, so teammates' recent runs show
- Token counts read in billions and trillions (1.1B, not 1120.9M)
- Claude Code terminal work that used Autopen always counts; the switch for it is gone
- Closing a board no longer risks saving older usage numbers over newer ones

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
