<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

In diel fan 'e websidekoade is iepen boarne, wolkom om te helpen de oersetting te optimalisearjen.

## front-end koade

* [front-end koade](https://github.com/xxai-art/web)
* [Taalpakketten foar de side as gehiel](https://github.com/xxai-art/web/tree/main/i18n)
* [Taalpakketten foar oanmeldmodules](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Webside Meartalige dokumintaasje](https://github.com/xxai-doc)

De programmeartaal foar front-end is [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , dy't wat funksjes tafoeget basearre op 'e coffeescript-syntaksis, sjoch [./coffee_plus.md](./coffee_plus.md) .

## Ynternasjonalisaasje fan websiden en dokuminten

Bouwe op de folgjende 3 projekten

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

It markdown-sjabloan, mei it efterheaksel `.mdt` , kin ferwize nei eksterne bestannen mei in syntaksis dy't fergelykber is mei `<+ ./coffee_plus/import.js>` .

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Markdown-oersetting sil gjin koades en keppelings oersette en oersette sinnen yn cache. As de oersetting wizige is, mar de oarspronklike tekst is net wizige, sil it opnij útfiere de wiziging fan de oersetting net oerskriuwe.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

Taalbestannen foar it oersetten `yaml` generearre websiden.
