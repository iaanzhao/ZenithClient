# ZenithClient

ZenithClient's version hub and Eaglercraft 26.2 build with WispCraft proxy support.

Hosted at: https://iaanzhao.github.io/ZenithClient/

The home page lists the built-in Zenith 26.2 client, self-hosted provider builds
in `clients/`, and the official 26.3 launch page. Custom HTTPS client links are
stored locally in the browser. Only the Zenith 26.2 build includes the Zenith
WispCraft integration. See `clients/SOURCES.md` for build sources and credits.

The bundled Zenith game is `client-26.2.html`; it uses the adjacent assets and
WispCraft bundle from the site root.

## WispCraft

This local build includes WispCraft for connecting the browser client to Java
servers through a Wisp relay. The WispCraft settings entry is added to the
multiplayer server list. Open it to sign in with Microsoft using the device
code flow and configure the relay URL. Account tokens are stored by WispCraft
in this browser's local storage.

WispCraft uses the browser's WebSocket and fetch APIs to route Minecraft
connections through the selected relay. Use only a relay you trust. The relay
can observe the destination server and connection metadata; Microsoft sign-in
is performed through Microsoft's device-code page.

The proxy includes Minecraft Java 26.2 protocol 776 mappings for login,
configuration, compression, custom payloads, and play-phase traffic.

### Rebuild the WispCraft bundle

```sh
cd vendor/wispcraft
npm ci
npm run build
cp dist/index.js ../../wispcraft.bundle.js
```

The checked-in `wispcraft.bundle.js` is the file loaded by `client-26.2.html`.
Dependency notices and license texts are in `vendor/wispcraft/`.
Forking this repository is prohibited; if you fork it, I will file a DMCA report against you.
