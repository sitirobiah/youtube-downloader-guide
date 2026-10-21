# Installation & Quick Setup Guide

This guide covers the step-by-step process of installing `yt-dlp` and `FFmpeg` on Windows using the Windows Package Manager (`winget`).

---

## 🛠️ Step 1: Install `yt-dlp`

Open your terminal (Command Prompt, PowerShell, or Git Bash) and run the following command to install `yt-dlp`:

```bash
winget install --id yt-dlp.yt-dlp -e



🎬 Step 2: Install FFmpeg
FFmpeg is required for processing, merging high-quality video and audio tracks, and converting formats. Install it by running:

```bash
winget install --id Gyan.FFmpeg -e
Note: After installing, restart your terminal window so the system recognizes the new environment variables for yt-dlp and ffmpeg.

✅ Step 3: Verify Installation
Check if both tools are correctly installed by running:

```bash
yt-dlp --version
ffmpeg -version
If both commands return version numbers, you are ready to go!


🚀 Step 4: Testing Your First Download
To test the installation, run yt-dlp followed by any YouTube video URL enclosed in double quotes:

```bash
yt-dlp "[URL YOUTOBE)"

