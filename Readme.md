# Cruss

**The collaborative API development workspace for engineering teams.**

Build, test, document and collaborate on APIs without leaving your editor. Work against localhost, connect to your team's shared workspaces, and keep requests, environments and documentation in one place.

Works with **VS Code**, **VS Code Insiders**, **Antigravity**, **Cursor**, **Windsurf** and **VSCodium**.

---

## Install

**VS Code / VS Code Insiders** — search `Cruss` in the Extensions panel, or install from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=CrussHQ.crusshq).

**Antigravity, Cursor, Windsurf, VSCodium** — search `Cruss` in your editor's extensions panel. These editors install from the [Open VSX Registry](https://open-vsx.org/extension/CrussHQ/crusshq).

**Manually** — download the `.vsix` from either registry, then drag it onto the Extensions panel, or:

```bash
code --install-extension crusshq-<version>.vsix       # VS Code
cursor --install-extension crusshq-<version>.vsix     # Cursor
windsurf --install-extension crusshq-<version>.vsix   # Windsurf
codium --install-extension crusshq-<version>.vsix     # VSCodium
```

---

## Start locally

Open the Cruss panel in the activity bar and create a local collection. Local collections are stored on your machine, require no sign-in, and work offline.

Requests are sent from the extension host rather than a browser, so **localhost works without CORS configuration**. For example, point a request at `http://localhost:3000` and run it directly from your editor.

---

## Connect your Cruss workspace

Click **Connect account** in the panel. Your browser opens to complete the connection, then returns you to your editor.

Once connected, your team's workspaces, collections and environments are available from the sidebar.

The connection works across all supported editors. Cruss detects which editor initiated the connection and returns you to it.

If your browser blocks the handoff, the connection page provides a token that you can paste into the extension instead.

---

## The sidebar

The sidebar has three segments you can switch between without losing your place.

**Collections** — local and team collections, with coloured HTTP methods, filtering, hover actions, context menus and keyboard navigation.

**Environments** — every environment in the connected workspace, with the active one marked. Switch with a click, or create and delete from here.

**History** — requests you've sent, and a **Team** view of requests sent by anyone in the workspace. Click any entry to open it as a new request.

Environments and history load when you open their segment, not before.

---

## What you can do

**Requests** — configure query parameters, headers and request bodies using JSON, raw text, form data, URL-encoded data or GraphQL. Authentication supports bearer tokens, basic auth and API keys.

**Environments** — reference variables such as `{{baseUrl}}` anywhere in a request. In the URL bar each variable is highlighted: tinted when the active environment defines it, amber when it doesn't, so a typo is visible before you send. Your environment selection is remembered per workspace, and unresolved variables are caught before a request goes out.

**Docs** — document requests in Markdown from the Docs tab alongside Params, Headers, Body and Auth. Documentation written in the web workspace is available in the extension, and changes made in the extension are reflected on the web.

**Responses** — inspect status, timing and response size, with JSON syntax highlighting, response headers and the last 20 responses for each request in the response History tab.

**cURL** — copy any request as a cURL command, or import cURL to create a request.

**Export** — export a local collection as Postman v2.1 JSON.

**Run in Output** — send a request directly to the editor's Output panel when you want the result alongside your logs.

---

## Working with your team

Connected workspaces use the roles assigned to you in Cruss.

**Admins and editors** can edit and save requests. **Viewers** can send requests but cannot modify them, with the extension indicating their access level before they attempt to save changes.

Workspaces belonging to an organisation are grouped under that organisation in the workspace switcher, with the organisation's plan shown alongside them.

---

## Settings

| Setting                  | Default                | What it does                                                             |
| ------------------------ | ---------------------- | ------------------------------------------------------------------------ |
| `cruss.workerUrl`        | `https://api.cruss.io` | API endpoint. Change only when self-hosting.                             |
| `cruss.webAppUrl`        | `https://cruss.io`     | Web app URL used for account connection and opening requests on the web. |
| `cruss.requestTimeoutMs` | `30000`                | How long to wait before aborting a request.                              |

---

## Privacy

Your account token is stored in your editor's **SecretStorage**, the same secure storage used for other editor credentials. It is never stored in settings or project files.

Local collections are stored in the extension's global storage and are not uploaded unless you attach them to a connected workspace.

Requests go directly from your machine to the URL you specify. Cruss does not proxy or inspect them.

---

## Support

For questions and bug reports, use the **Q&A** tab on the extension listing or visit [cruss.io/support](https://cruss.io/support).

---

## Licence

MIT