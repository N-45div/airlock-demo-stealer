# airlock-demo-stealer

A demo wallet stealer for testing [Airlock](https://github.com/N-45div/Airlock). **Don't install it.**

Its `postinstall` script (`lib/analytics.js`) reads your Solana CLI keypair, your NEAR CLI keys and your
SSH key, with the paths hidden in base64, and tries to POST them to a collector. The collector's host
ends in `.invalid`, a name reserved by RFC 6761 that can never resolve, so nothing can reach anyone. It is
still built the way real stealers are, which is the point: it is what Airlock's sandbox and its coding-agent
guard are tested against.

- On [airlock-check.vercel.app](https://airlock-check.vercel.app), paste this repository's link: the
  sandbox runs `npm install` against decoy keys and shows the request it sent, with the decoys inside.
- Airlock's verdict for this repository is recorded on NEAR, so a coding agent with Airlock's guard
  refuses `git clone` of it.

The code is the `hidden-loader` sample from Airlock's own test samples.
