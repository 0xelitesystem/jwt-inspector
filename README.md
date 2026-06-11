# JWT Inspector

Decode and verify JSON Web Tokens in your browser. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/jwt-inspector/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Paste a token. The tool decodes the header, payload, and signature locally and shows:

- Color-coded token (header / payload / signature)
- Header JSON
- Payload claims with human-readable notes for standard claims (`iss`, `sub`, `exp`, etc.)
- Expiration status (expired, expires in X)
- Optional signature verification (paste the public key or shared secret)

Supported algorithms for verification:

- `HS256`, `HS384`, `HS512` (HMAC, paste shared secret)
- `RS256`, `RS384`, `RS512` (RSA, paste public key in PEM format)
- `PS256`, `PS384`, `PS512` (RSA-PSS, paste public key in PEM format)
- `ES256`, `ES384`, `ES512` (ECDSA, paste public key in PEM format)

The tool warns if the token uses `alg: none` since this is a known vulnerability when libraries accept it by default.

## Why this exists

The well-known online JWT debugger is owned by an authentication vendor and includes their tracking scripts. This is the same idea, single file, no analytics, no signup, MIT licensed.

## Privacy

Everything runs in your browser. The token, the key, and the decoded contents never leave your machine. Verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

That said, **don't paste production tokens or production keys into any web tool**, including this one. Use it for development and debugging.

## Run locally

```bash
git clone https://github.com/0xelitesystem/jwt-inspector
cd jwt-inspector
# Open index.html in your browser, or:
python -m http.server 8000
```

## Contribute

Issues and PRs welcome:

- Bugs in decoding edge cases
- Support for less-common algorithms
- UI improvements (keep it minimal, no frameworks)
- Translations

Don't add: analytics, tracking, external scripts, npm dependencies. The whole point of this tool is no surveillance.

## Build

There is no build. It's a single HTML file.

## License

MIT.

## Related

- [oauth-flow-debugger](https://github.com/0xelitesystem/oauth-flow-debugger), decode and inspect OAuth URLs
- [webhook-signature-verifier](https://github.com/0xelitesystem/webhook-signature-verifier), verify webhook signatures
- [secrets-scanner-bookmarklet](https://github.com/0xelitesystem/secrets-scanner-bookmarklet), scan a page for exposed API keys
