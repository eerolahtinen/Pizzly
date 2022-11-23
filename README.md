<div align="center">
  
  ![Nango Logo](https://uploads-ssl.webflow.com/62a9f4a7a5a3d9ef1439982a/6311c3a48ebd85d6ed8f8f05_logo-background.png)

</div>

<h1 align="center">The simplest & fastest way to get OAuth tokens for 50+ APIs</h1>

<div align="center">
Pizzly takes care of the OAuth dance for you and makes sure your access tokens always stay fresh.
</div>

<p align="center">
    <br />
    <a href="https://docs.nango.dev" rel="dofollow"><strong>Explore the docs »</strong></a>
    <br />

  <br/>
    <a href="https://docs.nango.dev/">All supported APIs</a>
    ·
    <a href="https://github.com/nangohq/nango/issues">Contribute an API</a>
    ·
    <a href="https://github.com/nangohq/nango/issues">Report Bug</a>
    ·
    <a href="https://nango.dev/slack">Community Slack</a>
</p>

## ⭐ Pizzly at a glance
Pizzly is:
- a full OAuth 2 and OAuth 1.0a dance implementation
- with pre-built configurations for 50+ APIs
- language agnostic, it runs in a Docker container and works with backends written in any language
- easy to try in 5 minutes and can be deployed in 10

Start a **new OAuth flow with 2 lines of code in your frontend**:
```ts
var pizzly = new Pizzly();

// Trigger an OAuth flow for the user to authenticate with Slack
let result = await pizzly.connect('slack', '<user-id>');
```

Then **get and use the current access token in your backend** (with our SDK or a simple REST API):
```ts
var slackAccessToken = await Nango.getCurrentAccessToken('slack', '<user-id>'); // Always fresh & ready to use
```

## 👾 Out of the box support for 50+ APIs

More than 50 APIs are preconfigured to work out-of-the-box. Including:

- **Communication**: Gmail, Microsoft Teams, Slack, Zoom;
- **CRM**: Front, Hubspot, Salesforce, etc.
- **Developer tools**: GitHub, GitLab, BitBucket, Jira etc.
- **Accounting**: Xero, Sellsy, Zoho Books, etc.
- **Productivity**: Asana, Airtable, Google Drive, Google Calendar, Trello, Google sheets etc.
- **Social**: Twitter, LinkedIn, Reddit, Facebook etc.
- [and more...]()

If your favorite API is missing we [open a GitHub issue]() or [contribute it right away](): The API configurations are just simple [JSON files in a folder]().

## 🛡️ Small, self-contained & ready for production
We built Pizzly because we wanted a simple and fast way to get (fresh) access tokens for any API that requires OAuth.

On purpose Pizzly is small, focused on its one task and easy to deploy in production:
- It runs as a single docker container in your stack (or use our free [cloud version]())
- Updating it is as simple as `docker pull` and restarting the container
- [Securing it for production]() is quick & easy with only a minimal interface exposed publicly
- Our [CLI]() helps you with all admin tasks (such as setting scopes, enabling APIs etc.)

Last but not least, Pizzly's active community continuously expands & updates the 50+ blueprints. So your OAuth flows & tokens will keep on working even 5 years down the road.


## 🚀 Quickstart

Clone the repo and start Pizzly (comes with a postgres DB for local testing):
```bash
git clone https://github.com/NangoHQ/Pizzly.git
cd Pizzly
docker compose up
```

Make sure you have a client ID & secret ready for the API you want to use, e.g. for GitHub [register it here](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app). Use `http://localhost:3005/oauth/callback` as the callback URL.

Enable the GitHub API and add your OAuth client id & secret with the CLI (if you don't have one yet get one [here]()):
```bash
npx pizzly add-api github <client-id> <client-secret> "public_repo"
```

Open the demo page in your browser at [http://localhost:3005/demo](http://localhost:3005/demo) and try the OAuth flow!


## ♻️ Easily sync data with Nango.Sync
Pizzly gets you OAuth tokens so you can start making API calls.

If you need to continuously sync data from the external API (e.g. syncing in contacts, users, notes, tasks, issues, repos etc.) take a look at our sister project [Nango.Sync](https://github.com/NangoHQ/nango) (works with Pizzly tokens out of the box):
```ts
Nango.sync('https://any.rest.api/any/endpoint', options); // Sync data from endpoint to your DB & keep it fresh
```
Nango make syncing data from APIs to your database fast, simple & scaleable whilst giving you full access to the power of the API.

## 🔍 Where to learn more

⭐  Follow our development by starring us here on GitHub ⭐

-   Explore some [the full list of supported APIs](https://docs.nango.dev)
-   Easily sync data from any API with [`Nango.sync`](https://github.com/NangoHQ/nango)
-   [Contribute a new API]()
-   Share feedback or ask questions on the [Slack community](https://nango.dev/slack)
-   Check our [blog on native integrations](https://www.nango.dev/blog)
