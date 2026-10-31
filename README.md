# my-AI-companion
my-AI-companion (Uzi)
What it is

Uzi is an AI companion character for Windows that lives on your desktop. She talks to you out loud, hears you through the microphone, walks around your screens, sits on a couch, plays guitar, plays music, remembers your chats and misses you when you’re away. She has an angsty emo-teenager personality and a catchphrase, “Bite me.”

How it works
Brain: the AI runs on your own PC through Ollama, using a small local model (gemma2:2b, or qwen2.5:0.5b for weak PCs). Nothing is sent to a cloud service, and it works offline after installation.
Hearing: the microphone is recorded with sounddevice and turned into text by faster-whisper, a local speech recognition model. You use a press-to-talk button that you can drag anywhere on the screen.
Voice: Uzi speaks out loud with the Windows text-to-speech voice.
Body: the character, couch and control panel are drawn with Python’s tkinter and Pillow. The character walks across all monitors and reacts to the mouse.
Guitar and music: the guitar sound is synthesized by the program itself with numpy. Music comes from audio files in a folder you choose.
Memory: chats are saved in a local JSON file next to the program, so she remembers earlier conversations.
Optional features, off by default: webcam vision (opencv plus the small moondream image model), a phone chat page (a small built-in web server, used through Tailscale with a secret link), and PC control (browser tabs, YouTube, Spotify). The advanced PC control asks before risky actions such as shutdown and logs what it does. You switch all of these on yourself in the control panel.
How to install it (Windows 10/11)
On the GitHub page, click Code → Download ZIP and unzip it (for example on your Desktop).
Double-click Install.bat. If Windows shows a “protected your PC” warning, that’s because the file isn’t code-signed. You can open it in Notepad first to read it. It’s short.
Answer the questions in the window:
Which model: 1 for a normal PC (about 8 GB RAM), 2 for a weak PC (2–4 GB RAM)
Whether you want the webcam model (about 1.7 GB)
Whether you want Tailscale (only for the phone page)
If Python was missing, the installer installs it and asks you to close the window and run Install.bat again.
Wait until it says ALL DONE, then double-click Run.bat.
A character appears on your desktop, followed by a couch and a control panel. The control panel explains every setting.

The installer only does five things: it installs Python 3.12 if needed, installs Ollama, optionally installs Tailscale, installs the packages in requirements.txt and downloads the AI model. It doesn’t change any system settings.

Using her
Hold the press-to-talk button and speak. She answers out loud.
Drag the couch wherever you want her to sit.
If something doesn’t work, run Check_brain.bat (AI), Check_phone.bat (phone page) or Test.bat (microphone and voice).
No character art is included. Put your own picture named uzi.png in the folder, or pick one in the control panel.
How I used AI

I used AI tools to help write some of the code. The AI assistant Claude helped me write the installer, the README and this explanation, and helped me troubleshoot. I tested it, decided what the project should do, and put it together myself.
