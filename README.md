# Sealed Proposal

A single-page client proposal presented as a sealed envelope. The recipient burns the wax seal, the letter unrolls into one long page, and it ends in a reply form where they pick a package, tick add-ons, see a running total and sign.

Open `index.html` in a browser, or serve it from any static host.

## Using it

- **Edit proposal** (top right) opens the editor: recipient, sender, sections, packages, add-ons, closing, envelope style, colours, seal letters or logo, and your drawn signature. Changes save in that browser's `localStorage`.
- Add the recipient's name to the link as a hash to personalise it, e.g. `index.html#Oak-and-Vine`.
- A signed reply is stored in the browser and locks the seal. **Reset signing** clears it.

## Notes

- The "Download signed PDF" button uses the claude.ai artifact `downloads` capability, so it only appears when the page runs as a Claude artifact. On a plain static host the button stays hidden.
- Fonts load from Google Fonts and jsPDF from cdnjs.
