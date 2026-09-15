# Cruss

**The collaborative API development workspace for engineering teams.**

Build, test, document and collaborate on APIs without leaving your editor. Work against localhost, sync your team's shared workspaces, and keep requests, environments and documentation in one place.

Works in **VS Code**, **VS Code Insiders**, **Antigravity**, **Cursor**, **Windsurf** and **VSCodium**.

---

## Install

**VS Code / VS Code Insiders** — search `Cruss` in the Extensions panel, or install from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=CrussHQ.crusshq).

**Antigravity, Cursor, Windsurf, VSCodium** — search `Cruss` in your editor's extensions panel. These editors install from the [Open VSX Registry](https://open-vsx.org/extension/CrussHQ/crusshq).

**Manually** — download the `.vsix` from either registry, then drag it onto the Extensions panel, or:

```bash
code --install-extension crusshq-0.5.5.vsix       # VS Code
cursor --install-extension crusshq-0.5.5.vsix     # Cursor
windsurf --install-extension crusshq-0.5.5.vsix   # Windsurf
codium --install-extension crusshq-0.5.5.vsix     # VSCodium
```

---

## Start without an account

Open the Cruss panel in the activity bar and create a local collection. Local collections are stored on your machine, need no sign-in, and work offline.

Requests are sent from the extension host, not a browser, so **localhost works with no CORS configuration** — point a request at `http://localhost:3000` and it just runs.

---

## Connect your Cruss account

Click **Connect account** in the panel. Your browser opens, you approve, and you're returned to your editor. Your team's workspaces, collections and environments appear in the sidebar.

This works in every supported editor — the extension detects which one is asking and returns you to it.

If your browser blocks the handoff, the connect page shows a token you can paste instead.

---

## What you can do

**Collections** — browse local and team collections in a sidebar with coloured HTTP methods, a filter box, hover actions, right-click menus and full keyboard navigation.

**Requests** — set query params, headers, and a body as JSON, raw text, form data, URL encoded or GraphQL. Auth supports bearer tokens, basic auth and API keys.

**Environments** — a connected workspace's environments load automatically. Reference them as `{{baseUrl}}` anywhere in a request. Your selection is remembered per workspace, and an unresolved variable is caught before the request is sent rather than failing against a literal URL.

**Docs** — document any request in Markdown from the Docs tab, alongside Params, Headers, Body and Auth. Descriptions written on the web appear here and vice versa.

**Responses** — status, timing and size, with JSON syntax highlighting, response headers, and the last 20 responses per request in a History tab.

**cURL** — copy any request as a cURL command, or import one to create a request.

**Export** — export a local collection as Postman v2.1 JSON.

**Run in Output** — send a request straight to the Output panel when you want the result in your log rather than a tab.

---

## Working with a team

Connected workspaces carry your role. Admins and editors can edit and save requests; viewers can send them but not change them, and the panel says so rather than failing on save.

Workspaces belonging to an organisation are grouped under it in the switcher, with the organisation's plan shown.

---

## Settings

| Setting | Default | What it does |
| --- | --- | --- |
| `cruss.workerUrl` | `https://api.cruss.io` | API endpoint. Change only when self-hosting. |
| `cruss.webAppUrl` | `https://cruss.io` | Web app URL, used for connect and for opening requests on the web. |
| `cruss.requestTimeoutMs` | `30000` | How long to wait before aborting a request. |

---

## Privacy

Your account token is stored in your editor's **SecretStorage**, the same place it keeps your other credentials — never in settings or a file in your project.

Local collections live in the extension's global storage and are never uploaded unless you attach them to a connected workspace.

Requests go directly from your machine to the URL you enter. Cruss does not proxy or inspect them.

---

## Support

Questions and bug reports: the **Q&A** tab on the extension listing, or [cruss.io/support](https://cruss.io/support).

---

## Licence

MIT