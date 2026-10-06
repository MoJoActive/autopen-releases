# Changelog

What changed in each version of Autopen MoJo Active.

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
