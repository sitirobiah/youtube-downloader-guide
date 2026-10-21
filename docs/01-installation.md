# Installation & Quick Setup Guide

This guide covers the step-by-step process of installing `yt-dlp` and `FFmpeg` on Windows using the Windows Package Manager (`winget`).

## 🛠️ Step 1: Install `yt-dlp`

Open PowerShell or Command Prompt and run the following command to install `yt-dlp`.

```powershell
winget install --id yt-dlp.yt-dlp -e
```

## 🎬 Step 2: Install FFmpeg

FFmpeg is required for processing video and audio, merging separate audio and video streams, and converting media formats. Install it by running:

```powershell
winget install --id Gyan.FFmpeg -e
```

**Note:** After installation, restart your terminal so the system can recognize the installed tools and their environment variables.

## ✅ Step 3: Verify Installation

Check whether both tools are installed correctly by running:

```powershell
yt-dlp --version
ffmpeg -version
```

If both commands return version information, the tools are available in your terminal.

## 🚀 Step 4: Test Your First Download

To test the installation, run `yt-dlp` followed by the URL of a YouTube video enclosed in double quotes.

```powershell
yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"
```

Replace `VIDEO_ID` with the actual video ID from the YouTube URL.
