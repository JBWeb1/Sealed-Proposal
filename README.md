# Sealed Proposal

A single-page client proposal presented as a sealed envelope. The client burns the wax seal, the letter unrolls into one long page, and it ends in a reply form where they pick a package, tick add-ons, see a running total and sign.

## How it works

1. **Publish the page once.** In this repo on GitHub: Settings → Pages → Build and deployment → Source: *Deploy from a branch*, pick `claude/trusting-feynman-gtyxv2` and `/ (root)`, then Save. After a minute or two the page is live at `https://jbweb1.github.io/Sealed-Proposal/`.
2. **Open admin.** Go to `https://jbweb1.github.io/Sealed-Proposal/#admin` (or press **Admin** at the top right) and choose a passcode the first time. Visitors without the passcode can't edit anything.
3. **Write the proposal.** In admin press **New proposal**, or **Edit** on an existing one. Add your email so clients know where to reply.
4. **Make the client link.** In the editor, scroll to **Send it**. Optionally type a PIN (or press *Make a PIN for me*), then press **Create client link** and copy it.
5. **Send it.** Email or message the link. If you set a PIN, send the PIN separately, for example by SMS.
6. **The client opens it.** They see the envelope with their name. Pressing the seal asks for the PIN, then the letter opens. They choose a package and extras, sign, download the signed PDF, and press **Write the reply email**, which opens their email app with a reply code filled in.
7. **Record the reply.** Paste their email (or just the reply code) into **Record a reply** in admin. The proposal is marked Accepted or Changes requested, with their package, total and note.

The link itself carries the whole proposal, so nothing is stored on a server. Each link is a snapshot: after any change, make a new link. Old links keep the version they were made with.

## Admin

- **Overview**: number of proposals, how many await a reply, accepted, changes asked, and the total value accepted.
- **Proposals**: every proposal in this browser, with its status, the last link you made and its PIN. Edit, preview, copy the last link, duplicate, change the status by hand, or delete.
- **Record a reply**: paste a client's reply email to update its status.
- **Backup**: everything is stored in this browser only. Download a backup regularly, and restore it to move to another computer or browser.
- **Passcode**: change it, or lock admin. The passcode keeps casual visitors on your computer out. It is not real security: anyone who can open the browser's developer tools can read the stored data, including PINs.

## The PIN

With a PIN, the letter part of the link is encrypted (AES-GCM, key derived from the PIN with PBKDF2). Someone who gets the link without the PIN sees only the envelope: the client's name, colours, seal letters and your email. A short PIN stops casual forwarding and people glancing at an inbox. It will not stop a determined attacker who has the link and time to try every PIN offline. Use 8 digits for a little more margin, and don't put anything in a proposal you could not afford to leak.

## Notes

- Replies reach you only by email. The page cannot notify you by itself.
- A logo on the seal makes the link much longer. Some apps cut very long links, and the editor warns you when that might happen.
- Without a hash, `index.html#Oak-and-Vine` still personalises the recipient name on your own copy.
- Fonts load from Google Fonts and jsPDF from cdnjs.
