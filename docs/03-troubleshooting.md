# yt-dlp — Troubleshooting Guide

This guide covers common `yt-dlp` and FFmpeg issues on Windows, including command errors, format problems, and download failures.

## 1. Command Not Found

**Possible error:**

```text
'yt-dlp' is not recognized as an internal or external command
```

**Possible causes:**

- `yt-dlp` is not installed.
- The terminal was opened before installation finished.
- The executable directory is missing from the system `PATH`.

**Solutions:**

1. Restart PowerShell or Command Prompt.

2. Verify the installation:

   ```powershell
   winget list --id yt-dlp.yt-dlp
   ```

3. Check whether Windows can locate the executable:

   ```powershell
   where.exe yt-dlp
   ```

4. If the executable cannot be found, check the installation location and ensure it is accessible through `PATH`.

## 2. FFmpeg Is Not Found

**Possible symptoms:**

`yt-dlp` cannot merge separate video and audio streams or convert downloaded audio.

**Possible causes:**

- FFmpeg is not installed.
- Its executable directory is not available through `PATH`.

**Solutions:**

1. Check whether FFmpeg is installed:

   ```powershell
   winget list --id Gyan.FFmpeg
   ```

2. Verify whether Windows can locate FFmpeg:

   ```powershell
   where.exe ffmpeg
   ```

3. Check the version:

   ```powershell
   ffmpeg -version
   ```

4. If the command fails, verify the installation and environment variables, then restart the terminal.

## 3. Requested Format Is Unavailable

**Possible error:**

```text
Requested format is not available
```

**Possible causes:**

- The selected format ID is no longer available.
- The video does not offer the requested resolution or format.

**Solutions:**

List the current available formats:

```powershell
yt-dlp -F "https://www.youtube.com/watch?v=VIDEO_ID"
```

Choose a valid format ID from the output, or allow `yt-dlp` to select a suitable format automatically.

## 4. HTTP 403 or Access Denied

**Possible causes:**

- The website restricts the request.
- The video requires an account or permission.
- The website has changed its access or authentication requirements.

**Solutions:**

1. Confirm that the video is accessible through your browser.
2. Update `yt-dlp` if a newer version is available.
3. Review the error message and the website's supported authentication options.
4. Do not attempt to bypass access restrictions or download content without authorization.

## 5. Video or Audio Download Fails

**Possible causes:**

- An unstable internet connection.
- Temporary server-side problems.
- An unavailable or restricted video.

**Solutions:**

1. Check your internet connection.
2. Retry the command after confirming the video is accessible.
3. Check whether the problem affects one video or multiple videos.
4. Review the terminal output to identify the specific error.

## 6. Audio Conversion Fails

**Possible symptoms:**

The audio download completes, but conversion to MP3 fails.

**Possible causes:**

- FFmpeg is unavailable.
- The source file is incomplete or unsupported.
- The conversion process encounters an error.

**Solutions:**

Verify FFmpeg:

```powershell
ffmpeg -version
```

Then retry the conversion command:

```powershell
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=VIDEO_ID"
```

If the error persists, inspect the full terminal output for the underlying cause.

## 7. Update yt-dlp

Some download failures may be related to an outdated version.

If you installed `yt-dlp` using `winget`, check for updates with:

```powershell
winget upgrade --id yt-dlp.yt-dlp -e
```

After updating, retry the original command.

## Troubleshooting Checklist

- [ ] Confirm that `yt-dlp` is installed.
- [ ] Confirm that FFmpeg is installed when required.
- [ ] Verify that both commands are accessible from the terminal.
- [ ] Check the video URL and available formats.
- [ ] Read the complete error message before changing settings.
- [ ] Update the tool if an update is available.
- [ ] Confirm that you have permission to access and download the content.

## Key Takeaway

Effective troubleshooting starts with identifying the exact error rather than changing multiple settings at once. Verify the installation, inspect the command output, and test one possible cause at a time.

