# my-AI-companion (Uzi)

Uzi is an AI girl who lives on your Windows desktop. She talks to you, listens to you,
walks around your screens, sits on a couch, plays guitar and plays music.
She comes with a pre-made personality, and you can choose your own.

I made her because I wanted an AI friend on my computer that works without the internet
and doesn't send my chats anywhere. Her brain runs on my own PC with [Ollama](https://ollama.com).

## Download and play

**Go to the [Releases page](https://github.com/YOUR-USERNAME/my-AI-companion/releases/latest)
and download `my-AI-companion-v1.0.zip`.** Don't use the green Code button for this.
The zip on the Releases page is the one made for installing.

## How to install (Windows 10 or 11)

1. Download `my-AI-companion-v1.0.zip` from the Releases page.
2. Right click it and choose **Extract All**. Put the folder on your Desktop.
3. Open the folder and double click **`Install.bat`**.
4. Windows might say "Windows protected your PC". That is because my file is not signed.
   You can open `Install.bat` in Notepad first and read it. It is short. Then click
   **More info** and **Run anyway**.
5. A black window opens and asks you 3 questions:
   - **Which model?** Press `1` for a normal PC (about 8 GB RAM). Press `2` for a weak PC (2 to 4 GB RAM).
   - **Webcam model?** Press `Y` only if you want Uzi to see you through the webcam. It is about 1.7 GB.
   - **Tailscale?** Press `Y` only if you want to use the phone page.
6. If you don't have Python, the installer installs it and then tells you to close the
   window and double click `Install.bat` again. Do that.
7. Wait until the window says **ALL DONE**. The first time can take a while because the AI
   model is a big download.
8. Double click **`Run.bat`** to start Uzi.

When she starts, a character shows up on your screen. Then a couch and a control panel
show up. The control panel explains every setting and how to use it.

## What Install.bat does

It only does these 5 things:

1. Checks for Python. If it is missing, it installs Python 3.12 with `winget`.
2. Installs Ollama with `winget`.
3. Installs Tailscale with `winget`, only if you said yes.
4. Installs the Python packages in `requirements.txt` with `pip`.
5. Downloads the AI model you picked with `ollama pull`.

It doesn't change your Windows settings and it doesn't need admin rights. If Python or
Ollama need permission, Windows asks you.

## What Uzi can do

- **Talk:** she talks out loud in English. You talk to her with a press-to-talk button.
  You can drag the button anywhere on your screen.
- **Walk around:** she walks over all your screens and reacts to your mouse.
- **Couch:** she sits on a couch. You can drag it wherever you want.
- **Music and guitar:** she plays music from a folder you pick, to annoy you a little. She also
  plays guitar sometimes. The guitar sound is made by the program itself.
- **Memory:** she remembers your old chats and misses you when you are away.
- **Personality:** she comes with a pre-made personality, and you can choose your own in the control panel.
- **Control panel:** you can change how often she does things, her voice speed, the size of her and more.

These are **off until you turn them on** in the control panel:

- **Webcam:** she can see you and comment.
- **Phone page:** a web page you open on your phone to chat with her (uses Tailscale and a secret link).
- **PC control:** she can open and close browser tabs, go to YouTube and add songs on Spotify.
  There is also an advanced mode (apps, volume, windows, typing, shutdown). It asks first
  before risky things, and it writes down what it did.

## How it works

- The **brain** is a small AI model that runs on my PC with Ollama (`gemma2:2b`, or
  `qwen2.5:0.5b` for weak PCs). It works without internet after installing.
- She **hears** me with `sounddevice` and `faster-whisper`, which turns my speech into text on my own PC.
- The **window, character and couch** are made with Python (`tkinter` and `Pillow`).
- The **memory** is saved in a small file next to the program. It is not uploaded anywhere.
- The webcam uses a small image model called `moondream`, also local.

Everything is in one big Python file, `uzi_offline.py`. Some of the comments in it are in
Swedish because I am Swedish.

## If something doesn't work

| Problem | Double click this |
| --- | --- |
| Uzi can't reach her brain | `Check_brain.bat` |
| The phone page doesn't open | `Check_phone.bat` (start Uzi first) |
| She can't hear me or doesn't talk | `Test.bat` |
| A package didn't install | Run `Install.bat` again |

If an install fails because your Python is very new, install Python 3.12 and try again.

## Character picture

There is no character art in this repo, because I don't want to use art that isn't mine.
Until you add a picture, Uzi is a simple purple shape. To change it, put a picture called
`uzi.png` in the same folder as `uzi_offline.py`, or pick one in the control panel.
Use a picture you made or have permission to use.

## How I used AI

I made this project myself, but I used AI to help. I used AI to help me write some of the
code, the installer and this README. I have dyslexia and writing is hard for me, so I told
the AI what I wanted in my own words and it helped me turn that into text. I decided what
Uzi should be and do, I tested it on my own PC, and I changed things when they didn't work.

## License

MIT. See the [LICENSE](LICENSE) file.
