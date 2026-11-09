# Typeshoot plugin

The Typeshoot remote MCP connector plus seven creative skills for Claude Code.

## Install and connect

```bash
claude plugin marketplace add Tomolo997/typeshoot-marketplace
claude plugin install typeshoot@typeshoot
```

Use Claude Code 2.1.281 or later and a Typeshoot account. Open `/mcp`, select the Typeshoot server, choose **Authenticate**, and sign in through your browser. The connector defaults to `https://typeshoot.com/mcp`; no API key or environment variable is needed.

Try: “Show my Typeshoot credit balance and list the available image models.” Paid media tools use your Typeshoot credits.

## Data handling

Using a connector tool sends its prompts, selected media and task parameters to Typeshoot. Generation requests use fal.ai and the selected model provider; results return to the assistant and Typeshoot library. No local executable or install script is bundled. See the [Privacy Policy](https://typeshoot.com/privacy) and [Terms](https://typeshoot.com/terms).

## Skills

| Skill | For |
| --- | --- |
| `typeshoot` | Routing, house rules, credits and library |
| `typeshoot-image` | Images, edits, cut-outs and upscales |
| `typeshoot-video` | Clips, animated images and video model selection |
| `typeshoot-swap` | Consent-based character replacement |
| `typeshoot-edit` | Trim, reframe, join, audio and captions |
| `typeshoot-voice-music` | Voiceovers, music and sound effects |
| `typeshoot-brand` | Save and reuse brand kits |

[Website](https://typeshoot.com) · [Full setup and troubleshooting](https://github.com/Tomolo997/typeshoot-marketplace#readme) · [Support](https://github.com/Tomolo997/typeshoot-marketplace/issues)

[MIT License](LICENSE), copyright Typeshoot, 2026.
