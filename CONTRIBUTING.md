# Contributing to Totentanz

This document attempts to describe the processes for contributing to the Totentanz project.

All contributions are welcome. No contribution is too small and all contributions are valued.

# Purpose

## What it is

This file explains where to place your contributions, what to include in a PR, and how to format the files.

## What it is not

This is not a generic contributing guide. It will not cover such topics as "how to edit text files", "how to view json files", "how to code", "how to use git", "how to use GitHub", "how to commit", "how to make pull request", "how to not shoot myself in the foot while dealing with git branches", "how to breathe" or "why this is so complicated".
This is intentional and has two main reasons:

- There is more than enough documentation online, and in the era of AI you can be guided at your own pace with your own context and preferences. For generic stuff, googling or asking your favourite LLM will be more productive than reading step-by-step guide.
- The guide would be opinionated. I do 100% of my work over ssh and always minimize dependencies, to be able doing everything on any remote server in the same way as on physically local machine. This experience would be useless or even harmful for anyone who needs fancy IDE and graphical representation of their work.

This is not a guide on what exactly you should contribute. It's for you to decide.

# Pronouns

When it comes to the contributing process, there are two: `I`, and `we`.

`I` (@LiviaMedeiros) am solely responsible for:
- Steering the project overall
- Maintaining the infrastructure: servers, domains, etc. (including regular payments)
- Doing the code that deals with potentially sensitive information (private area, mainly API server)
- Making final decisions on the changes (i.e. approving and merging pull requests)
- Doing other changes that i deem required (e.g. pushing hotfixes without PR, or force-pushing)

`We` (`I` and `you`) are responsible for:
- Features in the public area of the project
- Bugfixes in the public area of the project
- Any other contributions in the public area of the project

There also is `they`, i.e. users who do not contribute, but if you read this document it is assumed that you are interested in being part of `we`. The guide will refer to you as `you` but it's important to keep in mind that in the area open for public contributions `we` have the same rights and the same knowledge. When it comes to a specific image or client-side js script, `I` may have same or less knowledge about it than `you`. In other words, this guide is aimed on `us`.

# Contents

- [Issues](#issues)
- [Pull Requests](#pull-requests)
- [Financial Contributions](#financial-contributions)

# Issues

If you:
- Found a bug that should be fixed
- Come up with a feature that should be implemented
- Want to propose any other change
- Have a question that can be actionably resolved by making changes

, do not hesitate to [open an issue in `totentanz-meta` repo](https://github.com/Puella-Care/totentanz-meta/issues/new).
Avoid creating issues in other repositories within this org. This is a single project, and [`totentanz-meta`](https://github.com/Puella-Care/totentanz-meta) exists exactly to have all issues in one place.

If your issue seems to be resolved, do not hesitate to close it, since some issues might stay opened until the issue author confirms that it's resolved.

If you wish to help with an issue and make a pull request, reference the issue it's related to (`Closes: <link-to-issue>` if your PR guarantees the issue to be fully resolved, `Refs: <link-to-issue>` in any other case).

# Pull Requests

This is where the contributing guide begins.

## Deciding on the subsystem

There are multiple servers, subsystems, and repositories. You have to select one.

### [`totentanz-meta`](https://github.com/Puella-Care/totentanz-meta)

Are your changes related purely to the project info, guides, FAQ, etc.? If not, skip this part.

The meta repo designed to aggregate all issues and info about the project. You can contribute to it directly, e.g. if you want to adjust [`README.md`](https://github.com/Puella-Care/totentanz-meta/edit/main/README.md) or [this document](https://github.com/Puella-Care/totentanz-meta/edit/main/CONTRIBUTING.md).

### [`client-apk`](https://github.com/Puella-Care/client-apk)

Do your changes belong to the client-side app itself, i.e. the apk file? If not, skip this part.

This repository is a fork of [`rayshift/magiatranslate`](https://github.com/rayshift/magiatranslate). It contains all code necessary to build the `totentanz.apk`, except the vanilla `v3.1.9` apk of course. Any bugfixes, features, refactorings are welcome, especially if you are knowledgeable in smali files and development for Android in general.

The client apk is built using workflow in that repo, which by itself should be the main source of trust, paired with the signature. The signing keys are accessible only to the repo, so if you fork it and build your version, you must use your own keys.

Not much else to say. Feel free to adjust this guide if you feel like you adding something here.

### [`en-download`](https://github.com/Puella-Care/en-download)

Do your changes belong to the few GB of data that the app downloads on fresh install, or the files the app supposed to download before reading specific parts of the story? This includes all the json story files. If not, skip this part.

The related repository is [`en-download`](https://github.com/Puella-Care/en-download), named like this because it's `en` overlay and because it belongs to the downloadable assets subsystem that canonically deals with files in `/magica/resource/download/`.

This is an overlay repository, i.e. it contains files to be written on top of base files (you are expected to have your own copy of these, for example, from your local installation or from [gitlab.com/puella-care/resource](https://gitlab.com/puella-care/resource)). Any new files will be added, or overwrite existing base files in the same location.

The main use of this overlay is translations. See a json file with texts that must be translated? Translate and upload the file in the same location. See an image that must be translated? Translate it while keeping the dimensions intact and upload the file in the same location. See a `plist`-based animation that must be translated using different dimensions? Adjust both `plist` and referenced sprites and upload everything in the same locations.

Purely cosmetic (e.g. changing whitespace in xml files or optimizing PNG files for size) changes are not required since the infra already does it.

The repo has some automated workflows. If it detects some issues (files in wrong place, invalid files), it might fail and try to inform about it. If also has automated normalization/optimization process, you might see commits from @SudachiSawa, this is normal.

There are no rules regarding commit messages whatsoever, except one: preserve authorship. The commit history of the repo is the only way to have the contribution history; so please make sure that all changes in the pull request made by you, or that every author and co-author is credited in the commit message. This includes translations and other changes sourced from NA version of the game.

Most of the time, the deployment would be triggered automatically on merge. Sometimes it will not and i will deploy changes manually. Either way, the deployment process would take a few minutes. If the changes are not deployed within a hour (e.g. because something malfunctioned in the infra), feel free to ping me to remind about it.

### [`en-image_web`](https://github.com/Puella-Care/en-image_web)

Do your changes belong to the image files that the app doesn't store locally but gets from the web server? If not, skip this part.

The related repository is [`en-image_web`](https://github.com/Puella-Care/en-image_web), named like this because it's `en` overlay and because it belongs to the web image assets subsystem that canonically deals with files in `/magica/resource/image_web/`.

This is an overlay repository, i.e. it contains files to be written on top of base files (you are expected to have your own copy of these, for example, from [`puella-historia`](https://github.com/LiviaMedeiros/puella-historia/tree/master/magica/resource/image_web) or [`image_web`](https://github.com/LiviaMedeiros/image_web/tree/master/magica/resource/image_web)). Any new files will be added, or overwrite existing base files in the same location.

The main use of this overlay is translations. See an image that must be translated? Translate it while keeping the dimensions intact and upload the file in the same location.

Purely cosmetic (e.g. optimizing PNG files for size) changes are not required since the infra already does it.

The repo has some automated workflows. If it detects some issues (files in wrong place, invalid files), it might fail and try to inform about it. If also has automated normalization/optimization process, you might see commits from @SudachiSawa, this is normal.

Note that files from NA version are always welcome, but it's your responsibility to make sure they match the latest JP version, because some dimensions could change over time while JP was active and NA was discontinued.

There are no rules regarding commit messages whatsoever, except one: preserve authorship. The commit history of the repo is the only way to have the contribution history; so please make sure that all changes in the pull request made by you, or that every author and co-author is credited in the commit message. This includes translations and other changes sourced from NA version of the game.

Most of the time, the deployment would be triggered automatically on merge. Sometimes it will not and i will deploy changes manually. Either way, the deployment process would take a few minutes. If the changes are not deployed within a hour (e.g. because something malfunctioned in the infra), feel free to ping me to remind about it. Note that there is a system that automatically triggers clearing client cache if assets were updated, but it shouldn't be relied on, and clearing app cache locally is always preferable.

### [`en-text`](https://github.com/Puella-Care/en-text)

Do your changes belong to the non-image (i.e. text-based) files that the app doesn't store locally but gets from the web server? If not, skip this part.

The related repository is [`en-text`](https://github.com/Puella-Care/en-text), named like this because it's `en` overlay and because it belongs to the web text assets subsystem that canonically deals with files in `/magica/` except `/magica/resource/`. I.e. with `/magica/template/`, `/magica/js/`, `/magica/css/`, and some others.

This is an overlay repository, i.e. it contains files to be written on top of base files (you are expected to have your own copy of these, for example, from [`puella-historia`](https://github.com/LiviaMedeiros/puella-historia/tree/master/magica/) or [`bella_donna`](https://github.com/LiviaMedeiros/bella_donna/tree/master/magica)). Any new files will be added, or overwrite existing base files in the same location.

The contents of this repository are quite broad.

#### `/magica/template/`

If you need to make changes to some static texts on pages, this is probably what you need.

This is a place for template files. The template system used is based on [Underscore.js](https://underscorejs.org/)'s template system. Most of the time, you don't need to change its internal logic, and only need it to understand how the page is structured, or to make changes to specific strings (i.e. translation).

Note that translations from NA version are always welcome, but it's your responsibility to make sure they match the latest JP version, because the layout could have JP-only adjustments over time.

The changes against base layer are reflected in the [html.patch](https://github.com/Puella-Care/en-text/blob/main/html.patch) file. Consider this file to be read-only and irrelevant when making changes, it's updated manually on the infra.

Please keep the changes minimal. If it's a direct string replacement, nothing else is required. If it's a meaningful change to the structure, please mark it with a comments such as `<!-- FIX(myUsername): description of the fix -->` right over the adjusted block of code.

There are no rules regarding commit messages whatsoever, except one: preserve authorship. The commit history of the repo is the only way to have the contribution history; so please make sure that all changes in the pull request made by you, or that every author and co-author is credited in the commit message. This includes translations and other changes sourced from NA version of the game.

Most of the time, the deployment would be triggered automatically on merge. Sometimes it will not and i will deploy changes manually. Either way, the deployment process would take a few minutes. If the changes are not deployed within a hour (e.g. because something malfunctioned in the infra), feel free to ping me to remind about it. Note that there is a system that automatically triggers clearing client cache if assets were updated, but it shouldn't be relied on, and clearing app cache locally is always preferable.

#### `/magica/css/`

If you need to make changes to layout styles or css-defined texts on pages, this is probably what you need.

This is the place for style (css) files. Most of the time, you will need to adjust these files after you changed something in `template` or `js` and they layout became ugly. Sometimes, you will need to adjust these files because some texts are hardcoded in `:before` or `:after` css blocks.

The changes against base layer are reflected in the [css.patch](https://github.com/Puella-Care/en-text/blob/main/css.patch) file. Consider this file to be read-only and irrelevant when making changes, it's updated manually on the infra.

Please keep the changes minimal. If it's a direct string replacement, nothing else is required. If it's a meaningful change to the structure, please mark it with a comments such as `/* FIX(myUsername): description of the fix */` right over the adjusted block of code.

Note that most of layout breakages coming from translation are well-known, already happened on NA, and already got fixed on NA. When searching for related css rules in NA files, you are likely to find `/* MN */` comment besides the exact change that you need. Please try it, and if the NA value works perfectly, just say 'thank you' and include it as-is. In the comment, use `MN` as the username (`/* FIX(MN): description of the fix */`).

There are no rules regarding commit messages whatsoever, except one: preserve authorship. The commit history of the repo is the only way to have the contribution history; so please make sure that all changes in the pull request made by you, or that every author and co-author is credited in the commit message. This includes translations and other changes sourced from NA version of the game.

#### `/magica/js/`

If you need to make changes to dynamically added strings or to any other logic of the game, this is the funniest part.

This is the place for code (JavaScript) files. Most of the app depends on them, and most of ingame bugs come from them.

The js files are minified, and we keep them minified to avoid the urge to rewrite everything and lose track of changes. You are free to beautify and analyze the scripts locally, but only minified versions are accepted in the overlay repository.

The changes against base layer are reflected in the [css.patch](https://github.com/Puella-Care/en-text/blob/main/js.patch) file. Consider this file to be read-only and irrelevant when making changes, it's updated manually on the infra, and it uses internal normalization to make the diff meaningful

Please keep the changes minimal. If it's a direct translation, please place the string on separate line, with a comment such as `// TL(myUsername): "oldString"` and put empty line above and below the changed part. If it's another fix, again keep the changes minimal, and use same formatting with comment such as `// FIX(myUserName): description of the fix`.

Non-trivial changes must come with exhaustive description in PR and/or beautified patch (if considered self-explanatory).

It is important to keep in mind that the scripts must comply with [EcmaScript 5](https://ecma-international.org/wp-content/uploads/ECMA-262_5th_edition_december_2009.pdf). Yes, we don't have `fetch`, or `?.`. Yes, `array.filter(...)[0]` is how we spell `array.find(...)` here. Yes, this is unfortunate, but the client-side webview is guaranteed to work only with ES5. And yes, even if you tested it on your device and it works, it doesn't mean anything. This is why we use jquery and underscore.

Of course, if there is an option to write changes without using external libs and it's concise enough, it's preferred.

It is possible to introduce an automated build system that will allow us to have overlay of fully beautified scripts while deploying fully minified versions on the web server. Transpiler is also okay. Implenentation of such system is always welcome, but until it's done, we stick to the current workflow.

There are no rules regarding commit messages whatsoever, except one: preserve authorship. The commit history of the repo is the only way to have the contribution history; so please make sure that all changes in the pull request made by you, or that every author and co-author is credited in the commit message. This includes translations and other changes sourced from NA version of the game.

### [`en-data`](https://github.com/Puella-Care/en-data)

Do your changes belong to the data served from the API server, and are purely translations? If not, skip this part.

This is a special overlay repo for the internal database for the API server. It contains files exported in a specific format, used as overlay for corresponding data. This data is currently considered static, and is held in-memory in well-compressed cache on the server side, and updating this data requires a server restart.

Nothing except the translatable strings should be changed in these files. Currently, only json format is supported.

If you are sure that some texts come from the API server but there's no file for them in this repo, feel free to open an issue describing what kind of data is it and where it appears in the app. I'll try to generate a file, implement overlaying system and add it to the repo.

### Other changes

Some data comes from the server and is generated fully dynamically. Currently, there is no repository and no way to contribute to this part, even if it's a simple and direct translation.

You still can open issues for such changes so they can be tracked.

For such changes, there will be another repo, however the format is not decided yet.

The current status is that some features are extracted in separate files designed to be self-contained and adjustable. Example:

```mjs
export const getMissionDescription = (mission, { charaList }) => {
  const { missionType, missionValue } = /^(?<missionType>ACTION_|CLEAR|COMBO_ACCELE_|COMBO_BLAST_|COMBO_CHARGE_|COUNT_CONNECT_|COUNT_MAGIA_|HP_|MEMBER_CHARA_|NOT_CONTINUE|NOT_DEAD|ONLY_DAMAGE_ATTRIBUTE_|ONLY_MEMBER_COUNT_|WAVE_)(?<missionValue>.*)$/.exec(mission)?.groups ?? {};
  const attributeMap = {
    FIRE: '火属性',
    WATER: '水属性',
    TIMBER: '木属性',
    LIGHT: '光属性',
    DARK: '闇属性',
    VOID: '無属性',
  };
  return {
    ACTION_: $ => `${$}ターン以内クリア`,
    CLEAR: () => 'クリア',
    COMBO_ACCELE_: $ => `アクセルコンボを${$}回発動`,
    COMBO_BLAST_: $ => `ブラストコンボを${$}回発動`,
    COMBO_CHARGE_: $ => `チャージコンボを${$}回発動`,
    COUNT_CONNECT_: $ => `コネクトを${$}回発動`,
    COUNT_MAGIA_: $ => `マギアを${$}回発動`,
    HP_: $ => `合計残HPが${$}％以上でクリア`,
    MEMBER_CHARA_: $ => `${charaList.find(({ id }) => id === ($ | 0)).name}を含めてクリア`,
    NOT_CONTINUE: () => 'コンティニュー無しでクリア',
    NOT_DEAD: () => '一人も倒れずにクリア',
    ONLY_DAMAGE_ATTRIBUTE_: $ => `${attributeMap[$]}のダメージだけでクリア`,
    ONLY_MEMBER_COUNT_: $ => `${$}人以下のチームでクリア`,
    WAVE_: $ => `${$}Wave内にクリア`,
  }[missionType]?.(missionValue) ?? mission;
};
```

Obviously, this can be changed in many ways, from using placeholders to dedicated templating system. Maybe just a bunch of hardcoded strings. We'll see once it is more clear how many strings must be translated and how they usually look like.

### Anything else

Anything else is likely to be bound to internal code and infra only, so the way to contribute there is to open an issue describing the bug that should be fixed or the feature that should be implemented. The more detailed the issue is, the better.

## Additional info regarding pull requests

This info is applicable for all repositories

### Legal acknowledgements

Anyone can commit. If you used data made by someone else, make sure to credit them in the commit message and/or relevant comments in code (where applicable). For uncredited changes, authorship is assumed to belong to the commit author.

### Statements regarding AI usage

Short answer: AI-assisted contributions are allowed, AI slop is not.

Long answer:

AI assistance is completely acceptable as cheaper and faster substitute to googling, digesting docs and remembering things that you are supposed to know but not keep in your brain's L2 cache. It is also acceptable to let AI review your changes to notice issues that are not obvious for the mortals. Contributions with such assistance are completely fine, as long as:

- They are carefully reviewed by you, and you are accountable for every changed byte, having full understanding of all proposed changes. Even if your prompt is perfect and the changes are 100% correct, it's not enough if there is a gap between changes and your own comprehension.
- They are marked with the `Assisted-by: <tool name or other context>` trailer in the commit message. This is not to diminish the contribution or shame, but purely for legal reasons: many AI-driven tools are trained on copyrighted code, and using them uncredited makes things complicated. Consider it to be same as leaving comment with stackoverflow link when someone copy-pastes some helper function 'as is'.

Note that if we deal with something directly written by AI, by 'AI tools' this document means actual tools that are properly trained on relevant data, aware of the full context, and run on your own resources. Any online service (both free and enterprise-level), especially using generic LLMs, is incapable of generating even remotely decent results. This situation is unlikely to change within at least few more years. As result, submitting AI slop in pull requests might be treated as spam.

## Examples

- `en-download`: https://github.com/Puella-Care/en-download/pull/13 is a good example of downloadable translations.
- `en-text`
  - https://github.com/Puella-Care/en-text/pull/16 and https://github.com/Puella-Care/en-text/pull/18 are good examples of a change to a template followed by fixup in css.
  - https://github.com/Puella-Care/en-text/pull/6 is an example of trivial translation in js.
  - https://github.com/Puella-Care/en-text/pull/1 is an example of trivial (as long as you know exactly where and what to do) fix in js.
- `en-image_web`: https://github.com/Puella-Care/en-image_web/pull/10 is a good example of added images (combines NA-sourced, and custom-made).
- `en-data`: https://github.com/Puella-Care/en-data/pull/9 is a good example of translation in server-side data.

# Financial Contributions

Lastly, financial support is also a contribution to the infra and the project overall. [Boosty page](https://boosty.to/puellacare) is currently the main way for this.
