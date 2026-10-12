# Sealed Proposal

A single-page client proposal presented as a sealed envelope. The client burns the wax seal, the letter unrolls into one long page, and it ends in a reply form where they pick a package, tick add-ons, see a running total and sign.

## How it works

1. **Publish the page once.** In this repo on GitHub: Settings → Pages → Build and deployment → Source: *Deploy from a branch*, pick `claude/trusting-feynman-gtyxv2` and `/ (root)`, then Save. After a minute or two the page is live at `https://jbweb1.github.io/Sealed-Proposal/`.
2. **Write the proposal.** Open that address, press **Edit proposal** and fill it in. Your draft is saved in your own browser, so use the same browser each time.
3. **Make the client link.** In the editor, scroll to **Send it**. Optionally type a PIN (or press *Make a PIN for me*), then press **Create client link** and copy it.
4. **Send it.** Email or message the link. If you set a PIN, send the PIN separately, for example by SMS.
5. **The client opens it.** They see the envelope with their name. Pressing the seal asks for the PIN, then the letter opens. They choose a package and extras, sign, and press **Download signed PDF**.
6. **You get the reply** when the client emails you that PDF. Put your email in the editor so the page tells them where to send it.

The link itself carries the whole proposal, so nothing is stored on a server. Each link is a snapshot: after any change, make a new link. Old links keep the version they were made with.

## The PIN

With a PIN, the letter part of the link is encrypted (AES-GCM, key derived from the PIN with PBKDF2). Someone who gets the link without the PIN sees only the envelope: the client's name, colours, seal letters and your email. A short PIN stops casual forwarding and people glancing at an inbox. It will not stop a determined attacker who has the link and time to try every PIN offline. Use 8 digits for a little more margin, and don't put anything in a proposal you could not afford to leak.

## Notes

- Replies stay in the client's browser until they send you the PDF. The page cannot notify you by itself.
- A logo on the seal makes the link much longer. Some apps cut very long links, and the editor warns you when that might happen.
- Without a hash, `index.html#Oak-and-Vine` still personalises the recipient name on your own copy.
- Fonts load from Google Fonts and jsPDF from cdnjs.
