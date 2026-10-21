
# yt-dlp — Detailed Usage Guide

This guide explains how to use `yt-dlp` to download videos, audio, and media in different formats.

## 1. Basic Video Download

Download a video using its URL.

```powershell
yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"
```

Replace the URL with the link to the video you want to download.

By default, `yt-dlp` selects a suitable available format based on its configuration and the formats offered by the website.

## 2. List Available Formats

View the available video and audio formats before downloading.

```powershell
yt-dlp -F "https://www.youtube.com/watch?v=VIDEO_ID"
```

The output lists available format IDs, resolutions, codecs, and other format details.

Use this command to identify the format you want to download.

## 3. Download a Specific Format

Use `-f` followed by the format ID to select a specific format.

```powershell
yt-dlp -f FORMAT_ID "https://www.youtube.com/watch?v=VIDEO_ID"
```

Replace `FORMAT_ID` with an available format ID shown by the previous command.

**Note:** Some websites provide video and audio as separate streams. You may need FFmpeg to merge them.

## 4. Download the Best Available Quality

Request the best available video and audio combination.

```powershell
yt-dlp -f "bv*+ba/b" "https://www.youtube.com/watch?v=VIDEO_ID"
```

- `bv*` selects the best available video format, which may include audio.
- `ba` selects the best available audio-only format.
- `+` combines the selected streams when necessary.
- `/b` provides a fallback to the best combined format.

FFmpeg may be required to merge separate streams.

## 5. Extract Audio

Download audio and convert it to MP3.

```powershell
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=VIDEO_ID"
```

- `-x` extracts audio from the downloaded media.
- `--audio-format mp3` requests conversion to MP3.
- FFmpeg is required for audio extraction and conversion.

## 6. Choose the Output Filename

Specify a custom filename for the downloaded file.

```powershell
yt-dlp -o "my_video.%(ext)s" "https://www.youtube.com/watch?v=VIDEO_ID"
```

The `-o` option defines the output filename template.

The `%(ext)s` placeholder is replaced with the appropriate file extension.

## 7. Download a Playlist

Download videos from a playlist.

```powershell
yt-dlp "https://www.youtube.com/playlist?list=PLAYLIST_ID"
```

Replace the URL with the playlist link.

**Note:** This command may download multiple videos. Make sure you have sufficient storage space and permission to download the content.

## 8. Limit the Download to a Playlist Item

Download a specific item or range of items from a playlist.

```powershell
yt-dlp --playlist-items 1,3,5 "https://www.youtube.com/playlist?list=PLAYLIST_ID"
```

This example selects playlist items 1, 3, and 5.

You can also specify a range, such as `1-5`, to select the first five items.

## 9. Update yt-dlp

Update `yt-dlp` when installed through `winget`.

```powershell
winget upgrade --id yt-dlp.yt-dlp -e
```

This command checks for an available package upgrade through Windows Package Manager.

## 10. Troubleshooting

### Command Not Found

If PowerShell cannot recognize `yt-dlp` or `ffmpeg`, restart the terminal and verify that the installation directory is available in your system's PATH.

### Format or Download Errors

List the available formats again and check whether the selected format ID exists.

```powershell
yt-dlp -F "https://www.youtube.com/watch?v=VIDEO_ID"
```

### Audio and Video Are Not Merged

If the video and audio download as separate files, verify that FFmpeg is installed and accessible.

```powershell
ffmpeg -version
```

## Key Takeaway

`yt-dlp` supports more than basic video downloads. By using format selection, audio extraction, output templates, and playlist options, users can control how media is downloaded.

Always respect copyright, the website's terms of service, and applicable laws when downloading media.
