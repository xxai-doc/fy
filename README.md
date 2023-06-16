<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

It is oan te rieden om nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) earst te ynstallearjen, en dan `direnv allow` nei it ynfieren fan de map ( [de .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) sil automatysk útfierd wurde nei it ynfieren fan de map).

De betsjutting is: Sineeske oersetting nei Japansk, Koreaansk, Ingelsk, Ingelske oersetting nei alle oare talen. As jo ​​allinich Sineesk en Ingelsk stypje wolle, kinne jo gewoan `zh: en` skriuwe.

De betsjutting is: Sineeske oersetting nei Japansk, Koreaansk, Ingelsk, Ingelske oersetting nei alle oare talen. As jo ​​allinich Sineesk en Ingelsk stypje wolle, kinne jo gewoan `zh: en` skriuwe.

* [front-end koade](https://github.com/xxai-art/web)
* [Taalpakketten foar de side as gehiel](https://github.com/xxai-art/web/tree/main/i18n)
* [Taalpakketten foar oanmeldmodules](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Webside Meartalige dokumintaasje](https://github.com/xxai-doc)

De front-end programmeartaal is [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , dy't wat funksjes tafoeget basearre op 'e coffeescript-syntaksis, sjoch [./coffee_plus.md](./coffee_plus.md) .

## Ynternasjonalisaasje fan websiden en dokuminten

Bouwe op de folgjende 3 projekten

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  It efterheaksel is `.mdt` , jo kinne de syntaksis brûke dy't fergelykber is mei `<+ ./coffee_plus/import.js>` om te ferwizen nei eksterne bestannen, en markdown generearje mei it efterheaksel `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown-oersetting sil gjin koades en keppelings oersette en oersette sinnen yn cache. As de oersetting wizige is, mar de oarspronklike tekst is net wizige, sil it opnij útfiere de wiziging fan de oersetting net oerskriuwe.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Taalbestannen foar it oersetten `yaml` generearre websiden.

### Ynstruksjes foar automatisearring fan dokumintoersetting

Sjoch koade repository [xxai-art/doc](https://github.com/xxai-art/doc)

It is oan te rieden om nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) earst te ynstallearjen, en dan `direnv allow` nei it ynfieren fan de map ( [de .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) sil automatysk útfierd wurde nei it ynfieren fan de map).

Om de grutte koadebasis oerset yn hûnderten talen te foarkommen, haw ik in aparte koadebasis foar elke taal makke en in organisaasje makke om de koadebasis op te slaan

It ynstellen fan de omjouwingsfariabele `GITHUB_ACCESS_TOKEN` en dan útfiere [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) sil automatysk de koade repository oanmeitsje.

Fansels kinne jo ek sette it yn in koade basis.

Oersetting skript referinsje [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

De skriptkoade wurdt as folget ynterpretearre:

[bunx](https://bun.sh/docs/cli/bunx) is in ferfanging foar npx, dat is flugger. Fansels, as jo gjin bun ynstalleare hawwe, kinne jo ynstee `npx` brûke.

`bunx mdt zh` jout `.mdt` yn de zh-map as `.md` , sjoch de 2 keppele triemmen hjirûnder

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` is de kearnkoade foar oersetting (as jo allinich `nodejs` hawwe ynstalleare, mar `bun` en `direnv` binne net ynstalleare, kinne jo ek `npx i18n` útfiere om te oersetten).

It sil [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) parse, de konfiguraasje fan `i18n.yml` yn dit dokumint is as folget:

```
en:
zh: ja ko en
```

De betsjutting is: Sineeske oersetting nei Japansk, Koreaansk, Ingelsk, Ingelske oersetting nei alle oare talen. As jo ​​allinich Sineesk en Ingelsk stypje wolle, kinne jo gewoan `zh: en` skriuwe.

De lêste is [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , dy't de ynhâld ekstrahearret tusken de haadtitel en de earste ûndertitel fan ' `README.md` fan elke taal om in yngong `README.md` te generearjen. De koade is heul ienfâldich, jo kinne it sels sjen.

Google API wurdt brûkt foar fergese oersetting. As jo ​​gjin tagong krije ta Google, konfigurearje en set dan in proxy yn, lykas:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

It oersettingsskript sil in oerset cache yn `.i18n` map generearje, kontrolearje it asjebleaft mei `git status` en heakje it ta oan it koade-repository om werhelle oersettingen te foarkommen.

Run `bunx i18n` asjebleaft elke kear as jo de oersetting wizigje om de cache te aktualisearjen.

As de oarspronklike tekst en de oersetting tagelyk wizige wurde, sil de cache betize wurde, dus as jo wizigje wolle, kinne jo mar ien wizigje, en dan `bunx i18n` útfiere om de cache te aktualisearjen.
