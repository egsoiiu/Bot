# 📤 URL Uploader Telegram Bot

A fast and simple Telegram bot to **download files from a URL** and **upload them to Telegram** — as a document or a streamable video (MP4).

Built with ❤️ using Rust.

---

## 🚀 Live Bot

Click to use the bot now:

👉 [Https://t.me/UrlUploadAsBot](https://t.me/urluploadasBot)


> If the bot is not working then simply click this link. <br>

---

## 💡 What It Does

This bot helps you:

- 📨 Upload any file via direct URL  
- 📝 Rename files using custom syntax  
- 🎞️ Automatically detect and stream MP4 video files  
- ⚠️ Warn when the file is empty or invalid  

---

## 🧾 Commands

### `/start`

- Shows a welcome/help message and usage instructions.


### `/upload`
- Upload mas


<br><br><br><br>

## 📥 How to Upload Files

You can send the bot:

### ✅ Just a URL

```
https://example.com/video.mp4
```

The bot will:

- Download the file,
- Extract or guess its name and extension,
- Upload it to Telegram.

---

### ✅ URL with Custom Filename

Use the pipe `|` character to provide your custom name:

```
https://example.com/video.mp4 | my_movie
```

- Keeps the original extension
- Renames the file to: `my_movie.mp4`

---
<br><br><br><br>
### 📁 Sample Files to Test

<details>
<summary>Click to expand</summary>

### 📄 Document (DOC)

```
https://file-examples.com/storage/fe8b8e6/file-sample_100kB.doc
```

### 🎬 MP4 Video

```
https://file-examples.com/storage/fe8b8e6/file_example_MP4_480_1_5MG.mp4
```

### 🎥 MKV Video

```
https://filesamples.com/samples/video/mkv/sample_640x360.mkv
```

### 🧪 With Custom Name

```
https://filesamples.com/samples/video/mkv/sample_640x360.mkv | my_movie
```

</details>


<br><br>

---

<br><br>
## ⚙️ How Filename Is Determined

The bot determines the filename using:

1. `Content-Disposition` HTTP header (if available)
2. Fallback to last segment of the URL path
3. If extension is missing, it is guessed from the `Content-Type`

### 🔠 If a custom name is provided:
- The file extension is preserved and appended to your name.

### 💬 Examples

#### Input:
```
https://example.com/download/video | cool_clip
```

#### Result:
```
cool_clip.mp4
```

---

## 🛠️ Features & Logic

- ✅ Parses and decodes filenames correctly (e.g., `%20` becomes space)
- ✅ Uses `Content-Disposition` or URL for file naming
- ✅ Guesses extension if not provided (via `mime_guess`)
- ✅ Supports Telegram's MP4 streaming detection
- ✅ Detects empty files (size = 0 bytes)
- ✅ Uploads as:
  - 🧾 **Document** (default)
  - 🎬 **Streamable video** (if MP4)

---

## 🧰 Tech Stack

Built using modern Rust tools:

- `teloxide` – Telegram bot framework  
- `reqwest` – HTTP client for downloading  
- `mime_guess` – Infer file extensions from MIME type  
- `percent-encoding` – Decode percent-encoded filenames  

---

## 📷 Example Bot Output

```
📥 Send me a file URL and I’ll upload it to Telegram!
✅ Supports documents, videos, and custom filenames.
```

> Only `.mp4` files are streamed as video — others are uploaded as documents.

---

## ⚠️ Telegram File Limits

- Max file size: **2 GB**
- Only `.mp4` can be streamed as video (others sent as documents)

---

## ❌ If It Doesn’t Work

- Check that the URL is:
  - ✅ Publicly accessible
  - ❌ Not behind login
  - ✅ Not expired
- File should not be empty
- Try opening the URL in a browser — does it download?

---

## 🐳 Self-Hosting (Optional)

Want to run it yourself?

- Clone this repo
- Add your Telegram bot token in `.env`
- Run with Cargo:

```bash
API_ID=
API_HASH=
BOT_TOKEN=
```

> Coming soon: Dockerfile, Render deploy guide, Railway setup

---

## 📄 License

This project is open-source and free for personal and educational use.

❗ **Do not use this bot to share copyrighted or pirated content.**

---

## 👤 Author

Made with ❤️ by [@yourusername](https://t.me/yourusername)  
Powered by Rust 🦀
