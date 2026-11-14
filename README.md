# Answer Pad

A small writing pad for iPad. Handwrite a math answer with Apple Pencil and send it to whichever AI you are studying with, instead of typing out the notation.

**Try it:** https://ivankolomietz.github.io/answer-pad/

## Why

When an AI tutor asks for your answer, typing fractions, exponents and integrals is slow. Answer Pad sits in a small window beside your notes app, so you can write the answer by hand and pass it straight to the chat.

## How to use it

1. Open the link above in Safari on your iPad.
2. Tap Share, then **Add to Home Screen**. It opens like an app from then on.
3. Keep your notes app open and bring Answer Pad in as a Slide Over or small window.
4. Write your answer with Apple Pencil.
5. Tap **Check**, pick your AI app (ChatGPT, Claude, Gemini and so on) from the share menu, and send.

**Copy** puts the picture on the clipboard instead, for pasting into a chat by hand.

## Buttons

| Button | What it does |
| --- | --- |
| Eraser | Switches between writing and erasing |
| Undo | Removes the last stroke |
| Clear | Wipes the pad |
| Finger | Lets you draw with a finger. Off by default, so a resting palm never draws |
| Copy | Copies your answer as an image |
| Check | Sends your answer to an AI app through the share menu |

## Good to know

- It works with any AI app that accepts images. Nothing is tied to one company.
- No account, no sign-up, no API key.
- Your handwriting stays on your device until you tap Check or Copy. The app has no server and collects nothing.
- The image is cropped to what you wrote, in dark ink on white, so it is easy for an AI to read.
- It works offline once it has been opened one time.
- Check cannot place your answer into a chat automatically: iPadOS does not let one app type into another, so the share menu is the hand-off.

## Running it yourself

The app is four static files with no build step:

- `index.html` is the whole app
- `manifest.webmanifest` and the two icons make it installable
- `sw.js` keeps it working offline

Serve the folder from any web server. Copy, Check and Add to Home Screen need a secure address (`https`) or `localhost`:

```
python -m http.server 8000
```

Then open `http://localhost:8000`.
