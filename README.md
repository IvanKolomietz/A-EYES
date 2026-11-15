# Answer Pad

A small writing pad for iPad. Handwrite a math answer with Apple Pencil and send it to whichever AI you are studying with, instead of typing out the notation.

**Try it:** https://ivankolomietz.github.io/A-EYES/

## Why

When an AI tutor asks for your answer, typing fractions, exponents and integrals is slow. Answer Pad sits in a small window beside your notes app, so you can write the answer by hand and pass it straight to the chat.

## How to use it

1. Open the link above in Safari on your iPad.
2. Tap Share, then **Add to Home Screen**. It opens like an app from then on.
3. Keep your notes app open and bring Answer Pad in as a Slide Over or small window.
4. Write your answer with Apple Pencil. Need more room? Drag the page up with a finger to scroll down (two fingers when **Finger** is on).
5. Tap **Check**, pick your AI app (ChatGPT, Claude, Gemini and so on) from the share menu, and send.

**Copy** puts the picture on the clipboard instead, for pasting into a chat by hand.

## Sending to your laptop

If you chat with your AI on a laptop, the pad can send your answer there instead.

1. On the laptop, open https://ivankolomietz.github.io/A-EYES/receive.html and leave it open next to your chat. It shows an 8-character code.
2. In Answer Pad on the iPad, tap **Laptop**, type the code, and tap **Connect**. You only do this once; the code is remembered.
3. The Check button now says **Send**. Tap it and your answer appears on the laptop page.
4. On the laptop, click **Copy** and press Ctrl+V in your chat.

Answers travel through the free public relay [ntfy.sh](https://ntfy.sh) as ordinary web traffic, so this works on school and office Wi-Fi that stops devices from reaching each other directly. Each answer is encrypted on the iPad with a key made from the pairing code and decrypted on the laptop, so the relay only carries scrambled data. The relay keeps that scrambled copy for a few hours and then deletes it. The relay limits how many messages one network can send per day, so on a busy shared network a send can occasionally be refused; Copy still works when that happens.

To go back to the share menu, tap **Laptop**, then **Stop sending to laptop**.

## Buttons

| Button | What it does |
| --- | --- |
| Eraser | Rubs out whatever you drag over; a circle shows where it is. It switches back to the pen when you lift the Pencil |
| Select | Circle some writing, then drag it to move it, or drag the dot at its corner to resize it. While something is selected, the Clear button reads **Delete** and removes just that. Tap Select again to go back to the pen |
| Undo | Takes back the last thing you did, including an erase, a move, a resize, or a Clear |
| Clear | Wipes the pad. Undo brings it back |
| Finger | Lets you draw with a finger. Off by default, so a resting palm never draws |
| Laptop | Pairs the pad with a laptop so answers are sent there |
| Copy | Copies your answer as an image |
| Check | Sends your answer to an AI app through the share menu. Reads **Send** when paired with a laptop |

## Good to know

- It works with any AI app that accepts images. Nothing is tied to one company.
- No account, no sign-up, no API key.
- Your handwriting stays on your device until you tap Check, Send or Copy. The app has no server of its own and collects nothing.
- The image covers everything you wrote, including parts scrolled off screen. It is cropped to your writing, in dark ink on white, so it is easy for an AI to read.
- It works offline once it has been opened one time.
- Check cannot place your answer into a chat automatically: iPadOS does not let one app type into another, so the share menu is the hand-off.

## Running it yourself

The app is four static files with no build step:

- `index.html` is the pad
- `receive.html` is the laptop page that receives answers
- `manifest.webmanifest` and the two icons make it installable
- `sw.js` keeps it working offline

Serve the folder from any web server. Copy, Check and Add to Home Screen need a secure address (`https`) or `localhost`:

```
python -m http.server 8000
```

Then open `http://localhost:8000`.
