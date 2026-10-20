# Changelog

What changed in each version of Autopen MoJo Active.

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
