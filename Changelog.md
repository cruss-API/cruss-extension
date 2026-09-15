# Changelog

All notable changes to the Cruss extension are recorded here.
This project follows [Semantic Versioning](https://semver.org/).

## [0.5.5]

### Changed
- Rewritten listing and readme. Cruss runs in Antigravity, Cursor, Windsurf and
  VSCodium as well as VS Code, and the description now says so.
- Removed two features from the listing that the extension does not have: a
  collection runner and AI-generated documentation. Both exist on the web app,
  neither shipped here.

## [0.5.4]

### Fixed
- **Form Data and URL Encoded bodies now load.** A request saved on the web with
  form fields opened with a single blank row in the editor. The stored body was
  never read into the form table — it is now parsed whether it was saved as an
  object, as key/value pairs, or as an encoded string, and disabled fields stay
  disabled.

### Changed
- Published under the `CrussHQ` publisher. The connect flow reads the extension
  identifier at runtime, so this rename requires no action from you.

## [0.5.3]

### Added
- **Docs tab on every request.** Document a request alongside its Params,
  Headers, Body and Auth — Markdown, with an Edit/Preview toggle, a formatting
  toolbar and a dot on the tab when a request is documented. Descriptions
  written on the web appear here, and vice versa.
- **Works beyond VS Code.** Connect Account now detects the host editor at
  runtime, so the one-click sign-in works in Antigravity, Cursor, Windsurf and
  VSCodium as well as VS Code.
- Pasted tokens are checked for completeness. A truncated copy used to be
  accepted and then fail on every request, which looked like an expired session.

## [0.5.2]

### Added
- **Environments load per workspace.** A workspace's environments now populate
  the ENV selector, your choice is remembered per workspace, and a workspace
  with exactly one environment selects it automatically.
- **Unresolved variables are caught before sending.** A URL still containing
  `{{baseUrl}}` names the missing variable instead of failing against a literal
  URL. There is a "Send anyway" override.

### Fixed
- The New Environment dialog appeared every time a request was opened.
- Response tabs appeared before anything had been sent.
- The response pane stays collapsed until the first response, so the request
  editor gets the space.
- Saved bodies, headers, params and auth now load for requests from a connected
  workspace.
- Requests time out instead of hanging indefinitely.
- Sending a request no longer silently overwrites the saved version — saving is
  an explicit action.

## [0.5.1]

### Added
- **Rewritten Collections sidebar.** Requests show their HTTP method in colour,
  names align, and there is a filter box, hover actions, right-click menus and
  full keyboard navigation.
- **Workspace switcher in the sidebar.** Workspaces are grouped by organisation
  and switch in place rather than through the command palette.
- **Connect Account is always visible** while signed out.

### Fixed
- The Collections panel never finished loading. It was declared as a webview but
  registered as a tree, so it waited forever for a provider that never arrived.
- Team workspaces appeared as "no workspaces yet" while still loading, and a
  failed load was indistinguishable from an empty account.
- `Copy as cURL` produced a command no shell could parse when the body contained
  an apostrophe.
- `Open in Cruss Web App` opened the app root instead of the request.
- Every request added a duplicate "Cruss" entry to the Output panel.
- `multipart/form-data` requests were sent as JSON with no boundary, so they
  always failed.
- Basic auth broke on non-ASCII credentials.
- Very large responses no longer freeze the panel.