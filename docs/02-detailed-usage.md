# yt-dlp — Detailed Usage Guide

This guide explains how to use `yt-dlp` to download videos, select media formats, extract audio, and manage output files on Windows.

## 1. Basic Video Download

Download a video using its URL.

```powershell
yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"
```

Replace the example URL with the actual video URL.

## 2. List Available Formats

View the available video and audio formats before downloading.

```powershell
yt-dlp -F "https://www.youtube.com/watch?v=VIDEO_ID"
```

The output displays available format IDs, resolutions, and codecs.

## 3. Select a Specific Format

Download a format using its ID from the available formats list.

```powershell
yt-dlp -f FORMAT_ID "https://www.youtube.com/watch?v=VIDEO_ID"
```

Replace `FORMAT_ID` with a valid format ID.

## 4. Download the Best Available Quality

Select the best available video and audio combination.

```powershell
yt-dlp -f "bv*+ba/b" "https://www.youtube.com/watch?v=VIDEO_ID"
```

- `bv*` selects the best video format, potentially including audio.
- `ba` selects the best audio-only format.
- `+` combines the selected formats when necessary.
- `/b` provides a fallback to the best combined format.

FFmpeg may be required to merge separate streams.

## 5. Extract Audio as MP3

Download audio and convert it to MP3.

```powershell
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=VIDEO_ID"
```

- `-x` extracts audio.
- `--audio-format mp3` specifies the output audio format.
- FFmpeg is required for conversion.

## 6. Customize the Output Filename

Choose a filename template for the downloaded file.

```powershell
yt-dlp -o "my_video.%(ext)s" "https://www.youtube.com/watch?v=VIDEO_ID"
```

The `-o` option controls the output filename. The `%(ext)s` placeholder is replaced with the appropriate file extension.

## 7. Download a Playlist

Download videos from a playlist.

```powershell
yt-dlp "https://www.youtube.com/playlist?list=PLAYLIST_ID"
```

Replace the example URL with the playlist URL. A playlist may contain many videos, so check the available storage space first.

## 8. Download Selected Playlist Items

Download specific items from a playlist.

```powershell
yt-dlp --playlist-items 1,3,5 "https://www.youtube.com/playlist?list=PLAYLIST_ID"
```

This example selects playlist items 1, 3, and 5.

To download the first five items, use `--playlist-items 1-5`.

## 9. Update yt-dlp

If `yt-dlp` was installed using Windows Package Manager, check for an available update with:

```powershell
winget upgrade --id yt-dlp.yt-dlp -e
```

## Key Takeaway

`yt-dlp` provides options for controlling media quality, selecting formats, extracting audio, naming output files, and downloading playlists. Understanding these options makes media downloads easier to manage.

Use these commands only for content you are authorized to download, and follow applicable copyright laws and website terms.

