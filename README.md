# VideoBatcher — Batch Video & Image Editing for Windows and Mac

**Turn your videos and images into multiple ready-to-post variations, with your own effects, captions, audio and watermarks.**

VideoBatcher is a desktop app for content creators, marketers and social media teams who want to repurpose content without editing every version by hand. Choose your source files, save the settings you like, and generate new exports on your own computer.

**[Download VideoBatcher](https://videobatcher.com/download)** · **[Features & pricing](https://videobatcher.com/#pricing)** · **[Agency & AI automation](https://videobatcher.com/agency)** · **[Setup guide](https://videobatcher.com/agency/automation)**

## What you can do

- **Batch-edit videos and images.** Apply variations in brightness, contrast, saturation, rotation and other supported effects within ranges you choose. Video effects also include trim, speed and audio pitch adjustments.
- **Add different captions to your exports.** Reuse a caption pool with fonts, colors, outlines, shadows, backgrounds, positioning and color-emoji support.
- **Vary the soundtrack.** Pick tracks from your audio pool, replace or mix with the original audio, adjust volume and preview the mix before rendering.
- **Apply your branding.** Add saved logo and text watermarks, and reuse your preferred placement and style.
- **Save time with presets.** Reuse editing settings for future batches and inspect detailed processing logs.
- **Control export metadata.** Clean source metadata and use supported Device Metadata Profiles. Metadata does not establish which device actually captured a file.
- **Render locally.** VideoBatcher creates the finished files on your computer and leaves source files unchanged. Parallel processing and supported hardware encoding can help reduce rendering time; performance depends on your computer and settings.

Supported source formats include MP4, MOV, AVI, MKV, JPG, PNG, WEBP and BMP.

## Agency: connect your own AI and repurpose social videos

Agency adds AI-assisted batch workflows and downloads of supported public Instagram posts/Reels and TikTok videos. Use only content you own or have permission to reuse.

### Connect Claude, ChatGPT, Gemini or Perplexity

VideoBatcher 3.10.0 provides one setup screen on Windows and Mac:

**AI Automation → AI Connection → Connect your AI**

- **Claude Desktop:** create and install a VideoBatcher extension for a direct local connection. This option is for the desktop app, not Claude on the web or phone.
- **ChatGPT:** add your private VideoBatcher link through Developer mode using an eligible account.
- **Gemini:** add the private link as a custom app, where Google's account and region requirements allow it.
- **Perplexity:** add the private link as a custom connector; organization restrictions may apply.

You bring your own AI account. VideoBatcher does not include an AI subscription or run an AI model. Advanced **MCP (Model Context Protocol)** configurations and **CLI** workflows are also available.

Once connected, ask your AI to find media in approved folders, write captions, prepare variations with approved presets, submit batches, check progress or cancel jobs. Choose **Review first** to approve each job yourself, or **Automatic** to run valid jobs within the permissions you have granted.

Example requests:

> “Check my VideoBatcher connection and tell me which folders and saved settings I can use.”
>
> “Make 5 variations of each video in my Clips folder with my Reels settings and a different caption about our summer sale.”
>
> “Show me the status of my last job and where the finished files were saved.”

**[Read the connection steps and account requirements](https://videobatcher.com/agency/automation#connect-ai).** AI workflows are still being tested; automated checks do not guarantee compatibility with every provider account, plan or region.

### Download and repurpose Instagram & TikTok videos

Use the **Downloads** tab to find supported public videos, browse results, choose what to download and send completed files to the editor. Standalone downloading requires Agency but **does not require an AI connection**.

Platform restrictions can block downloads. Private content and whole-Instagram-account discovery are not supported; TikTok profile discovery is best effort.

## Local rendering and privacy

Your source files and rendering stay on your computer. Cloud AI providers may process prompts, filenames, captions and tool results under their own terms. Optional frame sharing is off by default and requires your approval.

ChatGPT, Gemini and Perplexity exchange requests and tool results through VideoBatcher's encrypted private-link service. Keep VideoBatcher open while using those connections. Treat the link like a password: anyone holding it can use the VideoBatcher tools you have approved. Replace or revoke it in the desktop app if needed.

Connecting an AI does not grant it unrestricted filesystem or shell access, let it change your permissions, or unlock a subscription.

## Download and get started

1. Download the installer from **[videobatcher.com/download](https://videobatcher.com/download)** or the **[latest GitHub release](https://github.com/oneshoterick/VideoBatcherPro/releases/latest)**.
2. Choose `VideoBatcher_Setup.exe` for **Windows 10/11**, or `VideoBatcher-macOS.dmg` for **macOS (Apple Silicon & Intel)**.
3. Install and launch. The packaged app includes its processing tools; you do not need to install Python or FFmpeg separately.
4. Start the **Standard free trial: 30 generations, no credit card required**, or activate your existing license.
5. Add media, choose your settings and generate a small batch first. Review the output before scaling up.

**This repository hosts official installers and release information, not the application's source code.** GitHub's automatic “Source code” ZIP and TAR archives are not the desktop installers.

## Plans

| Plan | Price | Main use |
| --- | --- | --- |
| Standard Monthly | $99/month | Manual desktop video and image editing |
| Standard Yearly | $990/year | The Standard desktop workflow, billed yearly |
| Agency | $250 USD/month | Desktop license, AI-assisted automation and supported social downloads |

The Standard free trial does **not** include Agency features. Eligible existing monthly Standard subscribers can review a separate seven-day Agency upgrade trial: Standard stays paid during the trial, then Agency replaces it at $250/month unless they choose **Stay on Standard** before the deadline. New Agency subscriptions do not include that seven-day trial.

Subscriptions renew until cancelled. Check **[current pricing](https://videobatcher.com/#pricing)**, **[Agency eligibility and billing terms](https://videobatcher.com/agency)** and the **[refund policy](https://videobatcher.com/refund-policy)** before purchasing.

## Help and useful links

- [VideoBatcher website](https://videobatcher.com/)
- [AI connection & MCP guide](https://videobatcher.com/agency/automation)
- [Contact support](https://videobatcher.com/contact)
- [Manage your subscription](https://videobatcher.com/manage-subscription)
- [Terms of service](https://videobatcher.com/terms-of-service)

VideoBatcher is commercial, proprietary software. A public download repository does not make the application open-source or grant permission to redistribute it.