# Changelog

What changed in each version of Autopen MoJo Active.

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
