# Totentanz

Totentanz is a project preserving *Magia Record: Puella Magi Madoka Magica Side Story* and making it playable after End of Service.

---

## How to Play

1. **Download the APK:**  
   Get the latest [APK file](https://magi-reco.com/totentanz-latest.apk).
   <details><summary>Checksums</summary>

   ```
   sha2-384 e181dfb83178504e4251f8d6b2ccb1e632c3bc8596f608fbf819c895b9f6bcee29273147fe03ab1d4b97d64f76281846
   sha3-384 38ff618b27f4d031960a74a2747c3771e6aff9d2bfbdd7b7d73fe43bbc2679799500f8155ec6319b1210a739c32e7325
   ```

   </details>

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

For bug reports or anything else, open [issues](https://github.com/Puella-Care/totentanz-meta/issues).

---

## How to Support

Totentanz is a project maintained on a non-commercial basis. While it's free for everyone:
- **Financial Support:** Consider donating to cover domain, development, and hosting costs.
  - BTC: `bc1qlz0azz0mq32mt3ja30gzd9h5t9tk4zzr207aqv`
  - LTC: `LNUNTsqG9S4PqQwqMPL5sD3ciPxNPS8CFd`
  - ETH: `0xB14ad0d9c20f083e90Ae9c14E6F231E6Fa1EE2A2`
  - USDT: `0xB14ad0d9c20f083e90Ae9c14E6F231E6Fa1EE2A2`
  - XMR: `46w6fcnMy4kdtxwLSxXZqYbVAHp4Cu47HPiQfzrqM761Qbj7xMJojmkEPhhc3jT98VDw746hgRQHgDh7RtHEnB3iSMu482T`
  - For any other ways, contact via `livia@cirno.name` or open an issue in this repository.
  - If you want to be credited as sponsor, contact via same email.
- **Spread the Word:** Share Totentanz with your community.  
  There are no limitations or restrictions on spreading the info and links.

---

## How to Contact

For legal or official matters, do not hesitate to contact via: `9@cirno.name`

For everything else, contact via: `livia@cirno.name`

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

**Q: Will installing it overwrite the original game?**  
A: No, the game will be installed separately.

**Q: Is server-side code open source?**  
A: For several reasons it is not. This may change in the future.

**Q: What language is used for API server?**  
A: JavaScript, the only dependency is [`fastify`](https://github.com/fastify/fastify).

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
A: It might come in the future.

**Q: Is there any region restriction or country code?**  
A: No.

**Q: I have problem during asset downloading, what do I do?**  
A: Make sure your connection is stable, continue download in case of error, and be patient.

**Q: I have connection problems, what do I do?**  
A: Fix your connection.

**Q: I found a typo or image error, how do I fix it?**  
A: Open pull request to the corresponding overlay repository.

**Q: The M-Girl transformation videos are not playing, how to fix?**  
A: Only high quality movies are supported, make sure to select and download them.  
Only full download is available, per-M-Girl download will be available later.

**Q: The story that was supposed to be voiced is not voiced, how to fix?**  
A: Make sure to download full voices.  
Only full download is available, per-story download might be available later.

**Q: Why only a few events are available?**  
A: Event availability is limited to the data collected. If you have data for more events, feel free to share.

**Q: There were changes to the web overlays, but I don't see them ingame, how to fix?**  
A: Clear app cache (do not clear all data).

**Q: Why are enemy waves in quest battles always constant?**  
A: The data is limited and wave generation is difficult to implement in efficient way.

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

| ![Antimony](https://images.boosty.to/user/40383229/avatar?croped=1&mh=64&mw=64) | ![Axel Katsuragi](https://images.boosty.to/user/40386153/avatar?croped=1&mh=64&mw=64)| ![Destroyer068](https://images.boosty.to/user/40393353/avatar?croped=1&mh=64&mw=64) | ![igi](https://images.boosty.to/user/40384011/avatar?croped=1&mh=64&mw=64) | ![Izzy](https://cdn.discordapp.com/avatars/322449352721301504/48bd27a219b16e46815f4dbe4ab01582.webp?size=64) | ![VirusLord](https://images.boosty.to/user/40383226/avatar?croped=1&mh=64&mw=64) |
|:--:|:--:|:--:|:--:|:--:|:--:|
| Antimony | Axel Katsuragi | Destroyer068 | igi | Izzy | VirusLord |

---

## Acknowledgements

Thanks to `Magica Quartet/Aniplex・Magia Record Partners` and everyone involved in Magia Record for the game itself.

Thanks to everyone who contributed to the [`magiatranslate`](https://github.com/rayshift/magiatranslate) project that made translated version possible.

Thanks to everyone who contributed to all assets repositories (both here and in [`kamihama/magia-assets`](https://git.rayshift.io/kamihama/magia-assets)), expanding the translation far beyond what NA version had.

Thanks to everyone who helped with the [`puella historia`](https://github.com/LiviaMedeiros/puella-historia) project that made exhaustive implementation possible.

Thanks to `sisyphus888` who provided server for the downloadable assets.

---

## Copyright notice

© 2025 [LiviaMedeiros](https://github.com/LiviaMedeiros).

Based on [Magia Record: Puella Magi Madoka Magica Gaiden](https://magireco.com/) - Copyright by Magica Quartet/Aniplex, Magia Record Partners
