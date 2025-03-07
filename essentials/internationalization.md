---
title: Internationalization (i18n)
description: Translate FormKit UI and validation messages into supported languages — or provide your own.
---

# Internationalization (i18n)

:PageToc

FormKit ships with internationalization support for all of its interfaces and validation messages.

## Available languages

Currently, FormKit supports the following languages (in the `@formkit/i18n` package):

- 🇱🇾 Arabic (ar) — 🙏&nbsp;@Ahmedelforjani
- 🇦🇿 Azerbaijani (az) — 🙏&nbsp;@EmrullahKutlar
- 🇧🇬 Bulgarian (bg) — 🙏&nbsp;@ivanov1234159
- <img src="/img/catalan.png" alt="Catalan flag (Senyera)" class="rare-flag"> Catalan (ca) — 🙏&nbsp;@petergithubmgw
- 🇨🇳 Chinese (zh) — 🙏&nbsp;@myleslee
- 🇨🇳 Chinese Traditional (zh-TW) — 🙏&nbsp;@actocoa 
- 🇭🇷 Croatian (hr) — 🙏&nbsp;@antemarkic
- 🇨🇿 Czech (cs) — 🙏&nbsp;@dfridrich
- 🇩🇰 Danish (da) — 🙏&nbsp;@bjerggaard
- 🇳🇱 Dutch (nl) — 🙏&nbsp;@arjendejong12
- 🇺🇸 English (en)
- 🇫🇮 Finish - (fi) — 🙏&nbsp;@mihqusta
- 🇫🇷 French (fr) — 🙏&nbsp;@HoreKk, @pop123123123
- <img src="/img/frisian_flag.svg" alt="Frisian flag" class="rare-flag"> Frisian (fy) — 🙏&nbsp;@arjendejong12
- 🇩🇪 German (de) — 🙏&nbsp;@digitalkaoz, @tosling
- 🇬🇷 Greek (el) — 🙏&nbsp;@mendrinos
- 🇮🇱 Hebrew (he) - 🙏&nbsp;@Hepi420
- 🇭🇺 Hungarian (hu) — 🙏&nbsp;@KristofKekesi
- 🇮🇸 Icelandic (is) - 🙏&nbsp;@Gunsobal
- 🇮🇩 Indonesian (id) - 🙏&nbsp;@rama-adi
- 🇮🇹 Italian (it) - 🙏&nbsp;@punga78, @Archetipo95
- 🇯🇵 Japanese (ja) - 🙏&nbsp;@wonyx
- 🇰🇿 Kazakh (kk) - 🙏&nbsp;@ilya-raevskiy
- 🇰🇷 Korean (ko) - 🙏&nbsp;@bwp618, @titusdecali
- 🇱🇻 Latvian (lv) - 🙏&nbsp;@Bamslation 
- 🇱🇹 Lithuanian (lt) - 🙏&nbsp;@balu-lt 
- 🇲🇳 Mongolian (mn) - 🙏&nbsp;@zemunkh
- 🇳🇴 Norwegian Bokmål (nb) - 🙏&nbsp;@hognevevle
- 🇮🇷 Persian (fa) - 🙏&nbsp;@shahabbasian
- 🇵🇱 Polish (pl) - 🙏&nbsp;@xxSkyy
- 🇧🇷 Portuguese (pt) 🙏&nbsp;@r-martins, @dbomfim
- 🇷🇴 Romanian (ro) - 🙏&nbsp;@danve
- 🇷🇺 Russian (ru) - 🙏&nbsp;@andreimakushkin
- 🇸🇰 Slovak (sk) - 🙏&nbsp;@neridev
- 🇸🇮 Slovenian (sl) - 🙏&nbsp;@krisflajs
- 🇷🇸 Serbian (sr) - 🙏&nbsp;@milos5593
- 🇦🇷 Spanish (es) - 🙏&nbsp;@inibg
- 🇸🇪 Swedish (sv) - 🙏&nbsp;@purung
- 🇹🇯 Tajik (tg) - 🙏&nbsp;@devixrootix
- 🇹🇱 Tetum (tet) - 🙏&nbsp;@joshbrooks
- 🇹🇭 Thai (th) - 🙏&nbsp;@pknn
- 🇺🇦 Ukrainian (uk) - 🙏&nbsp;@aresofficial
- 🇺🇿 Uzbek (uz) - 🙏&nbsp;@root5427
- 🇹🇷 Turkish (tr) - 🙏&nbsp;@ragokan, @cemkaan
- 🇻🇳 Vietnamese (vi) - 🙏&nbsp;@oanhnn

Although flags are <a href="http://www.flagsarenotlanguages.com/blog/why-flags-do-not-represent-language/">poor representations of languages</a> (flags indicate a geographic nation, while languages can be spoken in many ares of the world), we use the flags in the list above to indicate the location of the contributor who created that particular locale.

::Cta
--- 
href: "https://i18n.formkit.com" 
type: "ghost" 
label: "Help others who speak your language!" 
button: "Contribute a locale"
---
::

## Using a locale

FormKit’s `defaultConfig` includes the english locale by default — to add an additional locale, import it from `@formkit/i18n` and append it to the `locales` option when you initialized the FormKit plugin. To set the active locale specify it with the `locale` option:

```js
import { createApp } from 'vue'
import App from 'App.vue'
import { plugin, defaultConfig } from '@formkit/vue'
import { de, fr, zh } from '@formkit/i18n'

const app = createApp(App)
app.use(
  plugin,
  defaultConfig({
    // Define additional locales
    locales: { de, fr, zh },
    // Define the active locale
    locale: 'fr',
  })
)
app.mount('#app')
```

## Changing the active locale

There are two ways to change your active locale:

- Using `this.$formkit.setLocale()` from the Vue plugin (best for options API).
- Directly modifying the root `config` object (best for composition API).

### Using `setLocale`

When using Vue’s options API, you have access to `this.$formkit` which contains `setLocale('de')` — a purpose-built method that globally changes the current locale:

::Example
---
  name: "Changing locale example"
  file: [
    '_content/_examples/locale-change/locale-change.vue',
    '_content/_examples/locale-change/formkit.config.js'
  ]
---
::

### Using root `config`

When using the composition API, you won’t have access to `this.$formkit`. Instead, you can fetch and modify the root FormKit configuration object. This is made available globally via Vue’s `inject` mechanism and a unique Symbol:

::Example
---
  name: "Changing locale via config"
  file: [
    '_content/_examples/locale-change-config/locale-change-config.vue',
    '_content/_examples/locale-change-config/formkit.config.js'
  ]
---
::

## Overriding

If you find a phrase in your locale isn’t worded the way you prefer, you can override those individual messages globally in your configuration. You can do this by providing a `messages` object to the `defaultConfig`:

```js
import { createApp } from 'vue'
import { plugin, defaultConfig } from '@formkit/vue'
import App from 'App.vue'

const app = createApp(App)
app.use(
  plugin,
  defaultConfig({
    messages: {
      en: {
        ui: {
          submit: '🚀 Launch',
        },
      },
    },
  })
)
```

::Callout
---
type: "tip"
label: "Message keys"
---
Messages are generally found under a locale’s <code>ui</code> or <code>validation</code> property. To see a full list of keys and messages <a href="https://github.com/formkit/formkit/blob/master/packages/i18n/src/locales/en.ts">checkout the english locale.</a>
::

## Adding your language

Writing a locale for a language you know is a great way to contribute to FormKit and an easy way to get started with open source too! We are always eager to see pull requests for new locales. To support this effort, we’ve created a locale builder — a small web app to make the translation process as easy as possible.

::Cta
--- 
href: "https://i18n.formkit.com"
label: "Help others who speak your language!" 
button: "Contribute a locale"
---
::

Of course, you are not required to use our locale builder to submit a language, and are more than welcome to submit a standard pull request with your locale included.

::Callout
---
type: "info"
label: "Localization"
---
If your language is already on the list (let's say English), but your locality speaks a variation of that language (like 🇬🇧 <code>en-GB</code>), please feel free to submit your localized language.
::
