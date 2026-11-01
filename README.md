# ZenithClient

Eaglercraft 26.2 with WispCraft proxy support.

Hosted at: https://iaanzhao.github.io/ZenithClient/

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

The checked-in `wispcraft.bundle.js` is the file loaded by `index.html`.
Dependency notices and license texts are in `vendor/wispcraft/`.
Forking this repository is prohibited; if you fork it, I will file a DMCA report against you.
