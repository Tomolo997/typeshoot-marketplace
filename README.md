<p align="center">
  <img src="assets/typeshoot.png" alt="Typeshoot" width="80" height="80">
</p>

# Typeshoot for Claude Code

Make and edit images, video, voiceovers, music and sound effects with [Typeshoot](https://typeshoot.com), inside Claude Code.

This marketplace bundles the Typeshoot remote MCP connector and seven skills for choosing models, estimating credits and finishing creative work. It is a small plugin distribution: the hosted Typeshoot application and its backend are not included.

## Install

You need a current version of [Claude Code](https://code.claude.com/docs/en/overview), a Typeshoot account, and available Typeshoot credits for paid media tools.

Run these commands in your terminal:

```bash
claude plugin marketplace add Tomolo997/typeshoot-marketplace
claude plugin install typeshoot@typeshoot
```

Open Claude Code and run `/mcp`. Select the Typeshoot server, choose **Authenticate**, and complete the Typeshoot sign-in and authorization in your browser. Return to Claude Code and check the connection there.

The default MCP endpoint is `https://typeshoot.com/mcp`. No Typeshoot API key, media-provider API key or local Typeshoot server is required. Claude Code manages the OAuth login.

Start with a read-only request:

> Show my Typeshoot credit balance and list the available image models.

Media generation uses Typeshoot credits. The skills ask Claude to estimate work above 100 credits, get approval and avoid regenerating without asking. View your balance and credit packs in your [Typeshoot dashboard](https://typeshoot.com/dashboard/credits).

## Try it

- “Make a 4:5 product photo of my uploaded bottle on a warm cream background. Keep the label unchanged.”
- “Remove the background from this product photo and save the cut-out to my Typeshoot library.”
- “Estimate a six-second vertical video of this image with a slow camera push-in. Show me the model and credits before generating.”
- “Create a calm voiceover saying ‘A new way to make something great.’ Show me the credit estimate first.”
- “Save my brand colors and tone, then use that brand for my next image.”

## Included skills

| Skill | Purpose |
| --- | --- |
| `typeshoot` | Route creative requests, handle credits and reuse library assets |
| `typeshoot-image` | Generate/edit images, remove backgrounds and upscale |
| `typeshoot-video` | Choose a video model, estimate and generate clips |
| `typeshoot-swap` | Consent-based character replacement and motion workflows |
| `typeshoot-edit` | Trim, reframe, join, add audio and caption videos |
| `typeshoot-voice-music` | Voiceovers, music and sound effects |
| `typeshoot-brand` | Save and reuse brand kits |

Skills load automatically when relevant. You can also invoke a focused skill, for example `/typeshoot:typeshoot-image`.

## Update or uninstall

Refresh the catalog, then update the plugin:

```bash
claude plugin marketplace update typeshoot
claude plugin update typeshoot@typeshoot
```

Restart Claude Code after an update, or use `/reload-plugins` in a running session.

To remove the plugin and then its marketplace:

```bash
claude plugin uninstall typeshoot@typeshoot
claude plugin marketplace remove typeshoot
```

For account-side access management, review connected apps in your [Typeshoot dashboard](https://typeshoot.com/dashboard). Removing this plugin does not delete your Typeshoot account or media library.

## Troubleshooting

- **Plugin not found:** add the marketplace using the first install command, or refresh it with `claude plugin marketplace update typeshoot`, then retry installation.
- **Installed but tools are missing:** restart Claude Code, open `/mcp`, and check that the plugin is enabled and its server is authenticated.
- **Authentication required:** use the browser sign-in flow in `/mcp`. Do not paste passwords or API keys into a prompt.
- **Cannot connect:** confirm that your network can reach `https://typeshoot.com`. If you previously set `TYPESHOOT_MCP_URL`, unset it to restore the production default; an empty value is not a fallback.
- **Insufficient credits:** check your balance and credit packs in the Typeshoot dashboard.

Official references: [plugin commands](https://code.claude.com/docs/en/plugins/cli-reference), [MCP authentication and environment variables](https://code.claude.com/docs/en/mcp), and [plugin troubleshooting](https://code.claude.com/docs/en/plugins/troubleshooting).

## Repository layout

```text
.claude-plugin/marketplace.json   # marketplace name: typeshoot
plugin/
  .claude-plugin/plugin.json     # plugin name: typeshoot
  .mcp.json                     # remote HTTP connector, browser OAuth
  skills/                       # seven SKILL.md files
  README.md
  LICENSE
assets/typeshoot.png
LICENSE
README.md
```

The marketplace resolves its plugin from `./plugin`. Advanced/self-hosted users can set `TYPESHOOT_MCP_URL` to a complete MCP URL before launching Claude Code; ordinary users should leave it unset.

## Support and license

[Typeshoot website](https://typeshoot.com) · [Report a plugin issue](https://github.com/Tomolo997/typeshoot-marketplace/issues)

This repository's plugin package is licensed under the [MIT License](LICENSE), copyright Typeshoot, 2026. The hosted Typeshoot service and media-generation credits are separate from this package.
