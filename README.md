# Starfall Ring — 0.1.0-pre-alpha.5

**Українська:** закрийте WoW і запустіть **StarfallSetup.exe**. Перевірте папку клієнта, виберіть налаштування та натисніть **«Встановити / застосувати зміни»**. Тим самим EXE можна змінити конфігурацію або видалити патч кнопкою **«Видалити патч»**. Коротка довідка — кнопка **?**.

**English:** close WoW and run **StarfallSetup.exe**. Check the client folder, choose your settings and click **Install / apply changes**. Run the same EXE to change settings or click **Uninstall patch** to remove the patch. Click **?** for help.

---

## Українська

### Короткий список змін у pre-alpha.5

- Власний патч визначається за маніфестом усередині MPQ; застарілий журнал не блокує оновлення чи видалення.
- Виправлена компенсація масштабу постійного кільця з гліфом; розрахунок без гліфа збережений.
- Колишній зовнішній край смуги став внутрішнім для всіх кольорів, талантів, станів гліфа й обох режимів. Числові радіуси не змінені.
- Пройдено 139 автоматичних перевірок, включно з повторними оновленнями між версіями.

Автор: **Lortetas**. Це **перший тестовий реліз, pre-alpha**. Усе ще тестується; точність для всіх моделей і конфігурацій не гарантована.

Для запитань, скарг і пропозицій: [lortetas.s@gmail.com](mailto:lortetas.s@gmail.com).

### Що робить патч

Показує наземне кільце навколо носія ефекту, щоб допомогти оцінити дальність Starfall. Кільце рухається разом із ним і проєктується на рельєф. Це клієнтський візуальний ефект: він не змінює дальність, шкоду чи інші правила самого закляття.

У pre-alpha.5 смуга малюється назовні: колишній зовнішній край стає внутрішнім. Це працює для всіх кольорів, талантів, станів гліфа та обох режимів. Числовий радіус і масштаб геометрії залишені попередніми; змінене лише накладання текстури. Це візуальний орієнтир, а не точне врахування розміру кожної цілі.

Установлювач дозволяє вибрати:

- колір: зелений, фіолетовий, жовтий, червоний або блакитний;
- Nature’s Reach: 0/2, 1/2 або 2/2;
- наявність **Glyph of Focus / Гліфа фокусування**;
- постійний показ у формі сови або показ під час активного бафа Starfall.

Попередній перегляд у вікні показує колір схематично; фактичний вигляд залежить від сцени в грі. Мову можна перемикати між українською й англійською. Початково обирається українська, лише якщо мова інтерфейсу Windows — українська; для всіх інших мов — англійська.

### Важливі обмеження

- **Постійний режим поширюється також на інших гравців у формі сови**, якщо вони використовують ті самі стандартні моделі. Це не ефект лише для власного персонажа. Інші носії цих моделей теж можуть отримати кільце.
- **У режимі за бафом кільця можуть з’являтися в інших сов, які кастують Starfall**, оскільки модель ефекту спільна.
- **Радіуси інших гравців можуть бути неточними.** Вони отримують ваш вибраний візуальний профіль, хоча їхні таланти, гліф і масштаб моделі можуть відрізнятися.
- Основний тестовий сетап: **нічний ельф, Glyph of Focus, Nature’s Reach 1/2, звичайний клієнт без змінених текстур**. Інші моделі, HD-паки та змінені клієнти можуть працювати інакше й потребувати додаткових налаштувань. На інших расах результат не підтверджений.
- Додатково прийнятий у тесті **постійний профіль без гліфа, Nature’s Reach 1/2, нічний ельф**. Починаючи з pre-alpha.3, постійне кільце компенсує стандартний масштаб моделі і з гліфом, і без нього. Геометрія перевірених профілів без гліфа збережена; виправлення з гліфом ще потребує ігрового тесту. Це не підтверджує точність інших моделей або режиму за бафом.
- Розмір цілі впливає на сприйняття межі: велика ціль може отримувати шкоду, коли її центр уже за кільцем. Поведінку на краю ще досліджуємо.
- Радіус фіксується під час застосування налаштувань. Після зміни гліфа або таланту в грі **запустіть EXE та застосуйте відповідний профіль**. Автоматичного відстеження спека немає.
- Багато одночасних кілець можуть впливати на FPS. Перевірка рельєфу, переходів між локаціями та тривалості показу триває.

### Встановлення та сумісність

Починаючи з pre-alpha.2, власний патч визначається за маніфестом усередині MPQ: ID продукту, автором Lortetas, версією, конфігурацією та контрольними сумами файлів. Зовнішній журнал не є обов’язковим для розпізнавання. Підтримане оновлення попереднього формату без видалення патча; перевірені власні дублікати зберігаються в резервних копіях і об’єднуються під час застосування налаштувань. Архів зі сторонніми файлами або невірними контрольними сумами автоматично не замінюється.

Потрібні **Windows x64, .NET Framework 4.5 або новіший і WoW 3.3.5a, build 12340**. Установлювач перевіряє версію `Wow.exe`, а не назву папки. Він шукає відомі встановлення та поширені папки з іграми; якщо клієнт не знайдено, виберіть його вручну. Перевірте шлях, особливо якщо маєте кілька клієнтів.

Патч створюється з ресурсів обраного клієнта й установлюється окремим MPQ у загальну папку **Data**. Перший кандидат — `patch-4.MPQ`; за потреби обирається наступний вільний сумісний загальний слот. Чужі архіви не перезаписуються. Якщо патч із вищим пріоритетом перекриває потрібні ресурси й сумісного слота немає, встановлення зупиниться з поясненням.

`Wow.exe` не змінюється. Окремий аддон не потрібен. Python та бібліотеки поруч із EXE не потрібні: бібліотека MPQ вбудована й розпаковується у службовий кеш встановлювача.

Журнал і резервні копії зберігаються в `%LOCALAPPDATA%\Lortetas\StarfallRing`. Видалення прибирає власний установлений патч; застарілі прототипи кільця залишаються в резервних копіях і автоматично не повертаються в гру. Зберігайте цю папку для можливого відновлення.

## English

### Pre-alpha.5 changes

- Setup identifies its patch using the embedded MPQ manifest; a stale journal no longer blocks updates or uninstall.
- Fixed permanent ring scale compensation with the glyph; the no-glyph radius calculation is preserved.
- The previous outer band edge becomes the inner edge for every color, talent rank, glyph state and both modes. Numerical radii are unchanged.
- Passed 139 automated checks, including repeated updates across setup versions.

Author: **Lortetas**. This is the **first experimental release, pre-alpha**. Everything is still being tested; accuracy across all models and configurations is not guaranteed.

For questions, complaints and suggestions: [lortetas.s@gmail.com](mailto:lortetas.s@gmail.com).

### What it does

Displays a ground ring around the effect carrier to help estimate Starfall range. The ring follows its carrier and projects onto terrain. This is a client-side visual effect: it does not change the spell’s actual range, damage or rules.

In pre-alpha.5, the band extends outward: the previous outer edge becomes the inner edge. This applies to every color, talent rank, glyph state and both display modes. The numerical radius and geometry scale are unchanged; only texture mapping changes. The ring is a visual guide and does not account precisely for every target’s size.

Available settings:

- color: green, purple, yellow, red or cyan;
- Nature’s Reach: 0/2, 1/2 or 2/2;
- **Glyph of Focus** enabled or disabled;
- permanent display in Moonkin Form, or display while the Starfall buff is active.

The preview is a schematic color sample; the in-game appearance depends on the scene. You can switch between Ukrainian and English. The default is Ukrainian only when the Windows display language is Ukrainian; all other languages default to English.

### Known limitations

- **Permanent mode also affects other players in Moonkin Form** who share the same standard models. This is not a local-player-only effect. Other carriers of these models may also display a ring.
- **Buff mode may display rings on other Moonkins casting Starfall**, because the effect model is shared.
- **Other players’ rings may be inaccurate.** They use your selected visual profile even if their talents, glyph or model scale differ.
- Main test configuration: **Night Elf, Glyph of Focus, Nature’s Reach 1/2, standard client without modified textures**. Other models, HD packs and modified clients may behave differently and need additional configuration. Other races have not been confirmed in game.
- An additional **permanent, no-glyph, Nature’s Reach 1/2 Night Elf** profile has been accepted in testing. Starting with pre-alpha.3, permanent rings compensate the standard model scale with and without the glyph. The previous no-glyph geometry is preserved; the glyph correction still needs in-game testing. This does not validate other models or the buff mode.
- Target size affects the apparent boundary: a large target may take damage with its center outside the ring. Edge behavior is still under investigation.
- Radius is fixed when settings are applied. If you change your glyph or talent in game, **run the EXE and apply the matching profile again**. Spec changes are not tracked automatically.
- Many simultaneous rings may affect FPS. Terrain coverage, zone transitions and effect lifetime remain under testing.

### Installation and compatibility

Starting with pre-alpha.2, setup identifies its patch using an embedded MPQ manifest: product ID, author Lortetas, version, configuration and payload checksums. An external journal is not required for detection. Previous-format patches can be updated without uninstalling; verified owned duplicates are backed up and consolidated when settings are applied. Archives containing unrelated files or incorrect checksums are not automatically replaced.

Requires **Windows x64, .NET Framework 4.5 or newer, and WoW 3.3.5a build 12340**. Setup checks the `Wow.exe` version, not the folder name. It searches known installations and common game folders; if no compatible client is found, browse manually. Check the chosen path, especially if you have multiple clients.

The patch is generated from the selected client’s resources and installed as a separate MPQ in the global **Data** folder. The first candidate is `patch-4.MPQ`; a later free compatible global slot is used if needed. Other archives are not overwritten. Installation stops with an explanation if a higher-priority patch overrides required resources and no compatible slot is available.

`Wow.exe` is not modified. No addon is required. No Python or adjacent DLLs are needed: the embedded MPQ library is extracted into the installer’s cache.

Installation records and backups are kept in `%LOCALAPPDATA%\Lortetas\StarfallRing`. Uninstall removes the owned installed patch. Obsolete ring prototypes remain in backups and are not automatically reactivated. Keep this folder for possible recovery.

## Third-party license

The EXE includes StormLib, used only by the installer. Its license is also embedded in the executable.

The MIT License (MIT)

Copyright (c) 1999-2013 Ladislav Zezula

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
