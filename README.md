[![API server status](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-api.yml/badge.svg)](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-api.yml)
[![Downloadable assets server status](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-downloadable.yml/badge.svg)](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-downloadable.yml)
[![Web assets server status](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-web.yml/badge.svg)](https://github.com/Puella-Care/totentanz-meta/actions/workflows/watchdog-web.yml)

# Totentanz

Totentanz is a project preserving *Magia Record: Puella Magi Madoka Magica Side Story* and making it playable after End of Service.

---

## How to Play

1. **Download the APK:**  
   Get the latest [release](https://github.com/Puella-Care/client-apk/releases).

2. **Install on Android:**  
   Follow your device's standard instructions to install APKs.

3. **Launch and Enjoy:**  
   Jump straight into the game with all features unlocked.

---

## How to Contribute

Contributions in any of the following areas are welcome. There are several overlay repositories:
- Downloadable assets overlay: [`Puella-Care/en-download`](https://github.com/Puella-Care/en-download)
- Image web assets overlay: [`Puella-Care/en-image_web`](https://github.com/Puella-Care/en-image_web)
- Text web assets overlay: [`Puella-Care/en-text`](https://github.com/Puella-Care/en-text)
- Server-side data overlay: [`Puella-Care/en-data`](https://github.com/Puella-Care/en-data)

See also: [`CONTRIBUTING.md`](https://github.com/Puella-Care/totentanz-meta/blob/main/CONTRIBUTING.md).

For bug reports or anything else, open [issues](https://github.com/Puella-Care/totentanz-meta/issues).

---

## How to Support

Totentanz is a project maintained on a non-commercial basis. While it's free for everyone:
- **Financial Support:** Consider donating to cover domain, development, and hosting costs.
  - Boosty: https://boosty.to/PuellaCare/donate
  - BTC: `bc1qlz0azz0mq32mt3ja30gzd9h5t9tk4zzr207aqv`
  - LTC: `LNUNTsqG9S4PqQwqMPL5sD3ciPxNPS8CFd`
  - ETH: `0xB14ad0d9c20f083e90Ae9c14E6F231E6Fa1EE2A2`
  - USDT: `0xB14ad0d9c20f083e90Ae9c14E6F231E6Fa1EE2A2`
  - XMR: `46w6fcnMy4kdtxwLSxXZqYbVAHp4Cu47HPiQfzrqM761Qbj7xMJojmkEPhhc3jT98VDw746hgRQHgDh7RtHEnB3iSMu482T`
  - XTM: `12NDEKjmJBY4xTuNkgDrv47fmFhwNLNHTrM4eKqoPUFMk3uQYCYoDcGPQX2HEJP9xR6ZErERP2oJoSSCMzC7GRb66nx`
  - For any other ways, contact via `livia@cirno.name` or open an issue in this repository.
  - If you want to be credited as sponsor, contact via same email.
- **Spread the Word:** Share Totentanz with your community.  
  There are no limitations or restrictions on spreading the info and links.

---

## How to Contact

For legal or official matters, do not hesitate to contact via: `9@cirno.name`

For everything else, contact via: `livia@cirno.name`

To make sure your email gets through, please include `Totentanz` in the subject or body. Spam filters are stupid, but this word is explicitly allowlisted.

---

## FAQ

**Q: Do I need an account to play?**  
A: No, Totentanz is fully unlocked from the start. This includes stories, M-Girls, doppels, memorias, etc.

**Q: Is there in-app purchasing?**  
A: No, the game is entirely free.

**Q: Which platforms are supported?**  
A: Currently, Totentanz is available only on Android. An iOS version may follow.

**Q: How do I report a bug?**  
A: Please open an issue on this GitHub repository, provide steps to reproduce your problem and screenshots.

**Q: How can I contribute to translations or assets?**  
A: Visit the GitHub repos listed in above and submit a pull request.

**Q: Can this be played offline?**  
A: No, the game requires connection to the server to work.

**Q: Can this be played on PC?**  
A: Yes, by using virtual machine with Android installed.

**Q: Can this be played in web browser?**  
A: No. It is feasible, but would require implementing all native features (e.g. live2d, animations, sounds, battles) in WebView realm.

**Q: Will installing it overwrite the original game?**  
A: No, the game will be installed separately.

**Q: Is server-side code open source?**  
A: For several reasons it is not. This may change in the future.

**Q: What language is used for API server?**  
A: JavaScript, the only dependency is [`fastify`](https://github.com/fastify/fastify). Unless this answer is updated, there is still no other dependencies.

**Q: What language/tools/hardware is used for the internal infrastructure?**  
A: Various.

**Q: Was AI used in the development process?**  
A: No. I am not strictly against AI, but the code quality of current models is too low, and it pushes code to gray legal area.

**Q: What was used as reference for development?**  
A: The data collected within [`puella-historia`](https://github.com/LiviaMedeiros/puella-historia) project. No other code nor data source was used.
This was an intentional decision to prove dataset's self-sufficiency and to make server fully independent in both architecture choices and legal matters.

There are gaps in the datasets that were later filled using guesses, historical data preserved as videos/pictures/etc., and asking people who remember things.

**Q: I do [something] but my progress is not saved, why?**  
A: The server operates in stateless mode.

**Q: What does stateless mode mean?**  
A: It means that for most methods, the changes are not preserved.
To improve the gameplay experience, there are a few exceptions:
- `user` data such as login name, etc.
- `gameUser` data such as M-Girl on homescreen, background, comment, etc.
- `userDeck` data with user-defined decks.
- `userQuestBattleResult` data which allows playing quests.
- Patrols subsystem works on shared basis rather than per-user.

All of these are preserved in memory only, i.e. changes can be wiped after timeout or server restart.

**Q: What is required for persistent storage?**  
A: Async `node:sqlite/promises` API.

**Q: What are differences between this APK and the one from Google Play?**  
A: The client part is basically [`magiatranslate`](https://github.com/rayshift/magiatranslate) using different servers.  
See [`Puella-Care/client-apk`](https://github.com/Puella-Care/client-apk) for details.

**Q: Where do I find history of scenario translations and credits for the translators?**  
A: The current scenario translations are in the [`Puella-Care/en-download`](https://github.com/Puella-Care/en-download) repository.  
All previous contributions were made to the MagiaTranslate project, and can be found in the [`kamihama/magia-assets`](https://git.rayshift.io/kamihama/magia-assets) repository.

**Q: Why can I play auto and x3 speed in battles that should not have it?**  
A: QoL improvement.

**Q: How do I import my account data?**  
A: If you have account backup made with latest version of `connect`, it might be possible in the future.

**Q: How do I access the tutorial?**  
A: The prologue story can be found in the archive. The tutorial battles are not accessible at the moment.

**Q: The texts are in Japanese, how to read?**  
A: Contribute to the translation overlay to make them show in English.

**Q: The texts are in English, is there a Japanese version?**  
A: It might come in the future. It is not a high priority since there's very little interest in Japanese version.

**Q: Is there any region restriction or country code?**  
A: No, and never will be. As long as your region has access to the World Wide Web, it is accessible.

**Q: I have problem during asset downloading, what do I do?**  
A: Make sure your connection is stable, continue download in case of error, and be patient.

**Q: I have connection problems, what do I do?**  
A: Fix your connection.

**Q: I think the server might be down, is it for everyone or just me?**  
A: Check the server status badges on this page. If any of them doesn't say 'passing', it is down for everyone.

**Q: I found a typo, image error, or broken layout; how do I fix it?**  
A: Open pull request to the corresponding overlay repository.

**Q: I found an image that is not loading, how do I fix it?**  
A: See [#19](https://github.com/Puella-Care/totentanz-meta/issues/19) for the current list of known missing assets.

If you have one of these, feel free to share or open pull request to the [`Puella-Care/en-image_web`](https://github.com/Puella-Care/en-image_web) repository. If nobody has it, it is lost media and nothing can be done about it.

**Q: I encountered the `Blam, Totentanz crashed` error, what to do?**  
A: Bugreport it. It's an internal server error, usually these are logged and resolved ASAP.

**Q: I encountered any other error, what to do?**  
A: Bugreport it. It's a client-side error, and steps to reproduce are mandatory to investigate it.

**Q: How likely is iOS version?**  
A: Easy if someone manages to make `magiatranslate`-patched version of iOS client app. Impossible otherwise.

**Q: I heard that it was feasible with vanilla `v3.1.9`, is that still true?**  
A: Not anymore. Vanilla app now points to the `Capricieux` server. See [#12](https://github.com/Puella-Care/totentanz-meta/issues/12) and [#18](https://github.com/Puella-Care/totentanz-meta/pull/18).

**Q: What is `Capricieux`?**  
A: Separate server in Tokyo designed to strictly separate Archive App from this project. See [`Puella-Care/capricieux`](https://github.com/Puella-Care/capricieux) repository.

**Q: The M-Girl transformation videos are not playing, how to fix?**  
A: Make sure to enable High Quality Videos in Settings -> Manage Data.  
Low Quality Videos are also available, but not recommended.

**Q: The story that was supposed to be voiced is not voiced, how to fix?**  
A: Make sure to download full voices.  
Only full download is available, per-story download might become available later.

**Q: Why only a few events are available?**  
A: Event availability is limited to the data collected. If you have data for more events, feel free to share.  
See [#34](https://github.com/Puella-Care/totentanz-meta/issues/34) for the list of currently missing implementations. If the event *type* is already implemented, adding another event of same type only requires the data.

**Q: Where is changelog?**  
A: All changes to the public part of the project are public in the repositories within [`Puella-Care`](https://github.com/Puella-Care) org. You can see full history of changes.

Significant changes to the internal part of the project are periodically summarized in the [feed on `boosty.to`](https://boosty.to/puellacare).

**Q: There were changes to the web overlays, but I don't see them ingame, how to fix?**  
A: Clear app cache (do not clear all data).

**Q: Why are enemy waves in quest battles always constant?**  
A: The data is limited and wave generation is difficult to implement in efficient way. It might be feasible to implement to some extent in the future.

**Q: Why is the total power of arena deck not calculated properly?**  
A: Performance considerations: user arena matches are generated synchronously, whereas retrieving the actual arena deck must be done asynchronously.

**Q: I need a real game with gacha and 3D models, what do I do?**  
A: Play [Madoka Magica Magia Exedra](https://play.google.com/store/apps/details?id=com.aniplex.magia.exedra.en)

**Q: I am content owner and I want some files to be removed, what do I do?**  
A: Open pull request or issue; or contact via email for legal and official matters.

---

## Sponsors

Notes:  
The list is updated manually, sometimes there might be a delay. If you feel like your name must be here, or if you wish it to be changed, or if you wish it to be removed, please open a PR or contact me.  
The list is sorted alphabetically, case-insensitive.

| ![Antimony](https://images.boosty.to/user/40383229/avatar?croped=1&mh=64&mw=64) | ![Axel Katsuragi](https://images.boosty.to/user/40386153/avatar?croped=1&mh=64&mw=64)| ![Destroyer068](https://images.boosty.to/user/40393353/avatar?croped=1&mh=64&mw=64) | ![igi](https://images.boosty.to/user/40384011/avatar?croped=1&mh=64&mw=64) | ![IzunaMoon](https://cdn.discordapp.com/avatars/644342720755925002/b782ba38066f22df493aec7fbcdac6ee.webp?size=64) | ![Izzy](https://cdn.discordapp.com/avatars/322449352721301504/48bd27a219b16e46815f4dbe4ab01582.webp?size=64) | ![Pontiff](https://images.boosty.to/user/40748117/avatar?croped=1&mh=64&mw=64) | ![VirusLord](https://images.boosty.to/user/40383226/avatar?croped=1&mh=64&mw=64) |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Antimony | Axel Katsuragi | Destroyer068 | igi | IzunaMoon | Izzy | Pontiff | VirusLord |

---

## Acknowledgements

Thanks to `Magica Quartet/Aniplex・Magia Record Partners` and everyone involved in Magia Record for the game itself.

Thanks to everyone who contributed to the [`magiatranslate`](https://github.com/rayshift/magiatranslate) project that made translated version possible.

Thanks to everyone who contributed to all assets repositories (both here and in [`kamihama/magia-assets`](https://git.rayshift.io/kamihama/magia-assets)), expanding the translation far beyond what NA version had.

Thanks to everyone who helped with the [`puella historia`](https://github.com/LiviaMedeiros/puella-historia) project that made exhaustive implementation possible.

Thanks to `sisyphus888` who provided server for the downloadable assets.

---

## Copyright notice

© 2025-2026 [LiviaMedeiros](https://github.com/LiviaMedeiros).

Based on [Magia Record: Puella Magi Madoka Magica Gaiden](https://magireco.com/) - Copyright by Magica Quartet/Aniplex, Magia Record Partners
