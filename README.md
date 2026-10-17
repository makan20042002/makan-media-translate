<div align="center">

<img src="logo.png" width="132" alt="MAKAN Media Translate logo">

# MAKAN Media Translate

### Offline subtitles and song lyrics from audio or video—on your own Windows PC.

Drop in a song, recording, or movie. MAKAN Media Translate uses Whisper locally to create timed text, can translate it through a configurable engine chain, and exports subtitle files your media player understands.

[**Download v0.1.0 for Windows**](https://makanlab.tech/media-translate/#download) · [Product page](https://makanlab.tech/media-translate/) · [Quick start](#quick-start) · [Report a problem](https://github.com/makan20042002/makan-media-translate/issues)

![Windows 10/11](https://img.shields.io/badge/Windows-10%20%7C%2011-1677ff?style=flat-square) ![Local transcription](https://img.shields.io/badge/transcription-local-16c784?style=flat-square) ![Interface languages](https://img.shields.io/badge/UI-English%20%7C%20%D9%81%D8%A7%D8%B1%D8%B3%DB%8C-7657ff?style=flat-square)

</div>

## What it does

```text
Audio or video  →  Whisper transcription  →  Optional translation  →  Preview & edit  →  SRT / VTT / ASS / TXT
```

1. **Open a media file** — MP3, WAV, M4A, AAC, OGG, OPUS, FLAC, MP4, MKV, WEBM, MOV, or AVI.
2. **Transcribe locally** — Whisper runs on your computer and can use a compatible graphics card.
3. **Translate if you want** — use local models and services first, then optional online providers in an ordered fallback chain.
4. **Review and export** — jump to any line, correct the text, choose the subtitle appearance, and save as **SRT, VTT, ASS, or TXT**.

## Highlights

- **Offline speech-to-text.** After the first model download, Whisper transcription does not require an internet connection.
- **GPU acceleration with CPU fallback.** A supported GPU can make transcription faster, but it is not required.
- **Flexible translation chain.** Supports downloaded offline models, Ollama (including TranslateGemma), LM Studio-compatible servers, Chrome's on-device translator, optional free web translators, and Gemini with your own API key.
- **Editable live preview.** Click a line to seek, edit text in place, and switch among original, translated, and bilingual views.
- **Subtitle styling.** Choose English or Persian fonts, font size, one of 24 colours or a custom colour, and an optional background box. Styles can be embedded in supported output files.
- **Useful for songs.** Lyrics appear below the player; styled ASS lyrics can also be displayed with MP3 files in players such as PotPlayer.
- **English and Persian interface.** A built-in user guide is available in both languages.
- **Installer or portable build.** Use the standard Windows installer or a single portable executable.

## Download

Current release: **v0.1.0** for 64-bit Windows 10 and 11.

| Package | Size | SHA-256 |
| --- | ---: | --- |
| [Installer](https://makanlab.tech/downloads/media-translate/MAKAN-Media-Translate-Setup-0.1.0.exe) | 78.0 MB | `25093542eaf23559ba75eb23d8fa5c8d45406d589def5f79610e2693cb9f1797` |
| [Portable](https://makanlab.tech/downloads/media-translate/MAKAN-Media-Translate-portable.exe) | 70.9 MB | `d241b68c103be3e9b2e1507ce8d5c83a4e5584fb2dafcaa9d8c05dcc1d607fb4` |

Verify a download in PowerShell:

```powershell
Get-FileHash .\MAKAN-Media-Translate-Setup-0.1.0.exe -Algorithm SHA256
```

> [!IMPORTANT]
> The app is not code-signed yet. Windows may show **“Windows protected your PC.”** If you obtained the file from the official link above and its hash matches, choose **More info**, then **Run anyway**.

### Optional: ffmpeg

MKV, AVI, and very long videos may require [ffmpeg](https://ffmpeg.org/). It is not bundled with the app. Put `ffmpeg.exe` next to the application or select it through **Choose ffmpeg** inside the app.

## Quick start

1. Drop a media file onto the first page.
2. Open **Model Hub** and download a Whisper model once. Enable **GPU** if your hardware supports it.
3. Select **Transcribe**, then optionally translate the result.
4. Review the lines and open **Subtitle style** if you want to change their appearance.
5. Select **Save subtitles** and choose SRT, VTT, ASS, or TXT.

For automatic subtitle discovery in most media players, give the subtitle and media files the same base name and keep them in the same folder—for example, `interview.mp4` and `interview.srt`.

## Privacy, clearly stated

| Feature | Leaves your computer? |
| --- | --- |
| Whisper speech recognition | **No** |
| Downloaded offline translation models | **No** |
| Ollama or LM Studio running locally | **No** |
| Optional free web translators | **Yes — subtitle text is sent when you enable them** |
| Gemini | **Yes — subtitle text is sent when you configure and use your own key** |

There is no account, analytics, or tracking. API keys are held in memory and are not saved or written into output files.

## System requirements

- Windows 10 or 11, 64-bit
- 8 GB RAM minimum; 16 GB or more recommended
- A recent NVIDIA or AMD GPU is helpful, but optional
- From a few hundred MB to several GB of free disk space, depending on the models you download
- Internet access for the first model download and for any online translation provider you choose to use

## Honest limitations

- Whisper can miss, repeat, or invent words—especially in music. Persian singing is currently the most difficult case. Always review important output.
- Translation quality depends on the selected engine and language pair. Local TranslateGemma through Ollama produced the best results during current testing, but results will vary.
- Free web translators are unofficial integrations and may stop working without notice.
- The first model download requires internet access.
- The app does **not** burn subtitles into video or convert media files.
- Qwen, Canary, and Parakeet speech engines are not included.

## Build from source

Install the current [Node.js LTS](https://nodejs.org/), then run:

```bash
npm install
npm run desktop    # open the Windows desktop app
npm start          # run the browser version; stop it before npm test
npm test           # run the test suite
npm run installer  # create the Windows installer in dist/
npm run dist       # create the portable executable in dist/
```

Developer documentation:

- [Architecture overview](docs/OVERVIEW.md)
- [Merge guide](docs/MERGE_GUIDE.md)
- [Third-party licences](docs/THIRD_PARTY.md)

## Credits and licences

MAKAN Media Translate uses:

- [Whisper](https://github.com/openai/whisper) by OpenAI (MIT), through Transformers.js (Apache-2.0)
- NLLB-200 (CC BY-NC 4.0; **non-commercial use only**), M2M-100, and mBART-50 (MIT)
- Electron and electron-builder (MIT)
- ffmpeg when supplied separately by the user

See [`docs/THIRD_PARTY.md`](docs/THIRD_PARTY.md) for the complete notices and terms. The licences of individual models still apply when those models are downloaded and used.

## Support

- [Open an issue](https://github.com/makan20042002/makan-media-translate/issues)
- [Visit the product page](https://makanlab.tech/media-translate/)
- [Contact MAKAN LAB](https://makanlab.tech/#contact)

---

<div dir="rtl">

## خلاصه فارسی

**MAKAN Media Translate** از فایل صوتی یا تصویری، با Whisper و روی رایانه‌ی خودتان، زیرنویس زمان‌دار می‌سازد. نتیجه را می‌توانید بررسی و ویرایش کنید، ترجمه کنید و با فرمت‌های **SRT، VTT، ASS یا TXT** ذخیره کنید. قلم، اندازه، رنگ و پس‌زمینه‌ی زیرنویس نیز قابل تنظیم است.

- [دانلود نسخه‌ی ویندوز](https://makanlab.tech/media-translate/#download)
- تبدیل گفتار به متن و مدل‌های ترجمه‌ی آفلاین، فایل شما را از رایانه خارج نمی‌کنند.
- مترجم‌های آنلاین اختیاری و Gemini فقط هنگام فعال‌بودن، متن زیرنویس را به سرویس مربوط می‌فرستند.
- برنامه هنوز امضای دیجیتال ندارد؛ پیش از اجرا، فایل را فقط از وب‌سایت رسمی بگیرید و مقدار SHA-256 را بررسی کنید.
- Whisper ممکن است به‌ویژه در موسیقی و آواز فارسی، واژه‌ای را اشتباه تشخیص دهد یا واژه‌ای اضافه کند؛ نتیجه‌ی مهم را حتماً بازبینی کنید.

</div>
