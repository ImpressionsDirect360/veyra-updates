# Veyra third-party components

Veyra's original application code is MIT-licensed. The rendering engine, filter
data, libraries, search service and publisher content have their own ownership
and licenses; Veyra branding does not change those rights.

## Privacy engine

`@ghostery/adblocker` 2.20.1, Copyright 2017-present Ghostery GmbH and contributors,
is used unmodified under the Mozilla Public License 2.0. Its license and source
JavaScript are retained in `resources/app.asar/node_modules/@ghostery/adblocker`.
The exact version is also available from
https://www.npmjs.com/package/@ghostery/adblocker/v/2.20.1 and the upstream source
repository https://github.com/ghostery/adblocker. Its transitive packages retain
their individual notices and licenses in their package directories.

## Filter data

EasyPrivacy and EasyList are by **The EasyList authors (https://easylist.to/)**.
This distribution uses the Creative Commons Attribution-ShareAlike 3.0 Unported
license option documented at https://easylist.to/pages/licence.html.
License: https://creativecommons.org/licenses/by-sa/3.0/ .

The exact downloaded source lists and attribution headers are retained under
`src/privacy/`. `network.bin` is a compiled adaptation containing supported
network rules, without cosmetic rules; that adapted filter data is offered under
the same CC BY-SA 3.0 license. `manifest.json` records publisher URLs, date,
engine version and SHA-256 hashes. `npm run update:filters` deliberately downloads
fresh public lists and rebuilds the data. The browser does not contact list hosts
while browsing. This is not an endorsement by Ghostery or EasyList.

## Existing components

## Site safety data (2.5)

The unmodified HaGeZi Threat Intelligence Feeds Mini domain list is a separate
data component by HaGeZi and contributors, distributed under GPL-3.0. Its exact
source, attribution header, full license and download/hash manifest accompany
this release in `src/safety/`. Source and updates:
https://github.com/hagezi/dns-blocklists . The data retains its GPL license;
Veyra's original application source remains MIT-licensed. No endorsement or
guarantee of safety is implied. Runtime checks happen locally; periodic refreshes
download the complete public list without submitting browsing addresses.

## Browser and other libraries

Electron/Chromium notices remain beside Veyra.exe in LICENSE.electron.txt and
LICENSES.chromium.html. Other runtime dependencies (htmlparser2, ipaddr.js,
robots-parser, electron-updater and their dependencies) retain their licenses inside app.asar.
package-lock.json identifies every exact dependency version. Serper provides
the connected search service under its own terms and requires the user's key.
