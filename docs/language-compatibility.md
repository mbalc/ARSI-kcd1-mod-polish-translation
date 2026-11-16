# Raport zgodności językowej

**Status:** wstępny audyt statyczny; stan na 16 listopada 2026 r. **Cel:** sprawdzić, które nazwy z szablonu ARSI mają
polskie odpowiedniki w _Kingdom Come: Deliverance_ oraz wskazać różnice między szablonem a głównym modem.

## Zgłoszony problem

Autor projektu, mbalc, zgłasza, że przy używaniu głównego ARSI bez polskiego tłumaczenia niektóre nazwy przedmiotów
pojawiają się po angielsku pomiędzy nazwami polskimi. Ten raport nie odtwarza problemu w grze. Zawartość głównego moda
potwierdza jednak, że ARSI zawiera angielskie wpisy dla nazw przedmiotów, których polskie wartości nie zawsze występują
w lokalizacji bazowej gry. Jest to zgodne ze zgłoszonym objawem, ale zachowanie mechanizmu lokalizacji wymaga jeszcze
testu w grze.

## Źródła i metoda

- Szablon projektu: [`text__ARealSortedInventory[1].xml`](../text__ARealSortedInventory%5B1%5D.xml).
- Archiwum głównego ARSI 1.3.3.1 udostępnione do odczytu przez autora:
  `A Real Sorted Inventory 2204 1.3.3.1 2026-06-26T10-36Z M04BeYC8a.zip`. Zbadane pliki:
  - `ARealSortedInventory/Localization/english_xml.pak` → `text__ARealSortedInventory.xml`;
  - `ARealSortedInventory/Data/ARealSortedInventory.pak` → `Libs/Tables/item/player_item__ARealSortedInventory.xml`;
  - `ARealSortedInventory/Data/ARealSortedInventory.pak` → `Scripts/mods/ARealSortedInventory.lua`.
- Lokalizacja gry: `Localization/Polish_xml.pak`; przeszukano wszystkie 11 tabel XML, w tym `text_ui_items.xml`.
- Wersje 1.3.3.1 dla głównego moda i 1.3.1 dla szablonu językowego pochodzą z informacji o plikach Nexus Mods
  przekazanych przez autora. Powiązane strony: [ARSI](https://www.nexusmods.com/kingdomcomedeliverance/mods/2204) i
  [przykładowe tłumaczenie niemieckie](https://www.nexusmods.com/kingdomcomedeliverance/mods/2222).

Archiwa otwarto w trybie tylko do odczytu; nie rozpakowywano ich na dysk ani nie zmieniano instalacji gry. Porównanie
sprawdzało najpierw identyczność kluczy, a następnie identyczność angielskiego tekstu źródłowego. Dopasowanie tekstu
jest wskazówką terminologiczną, nie dowodem, że dwa wpisy mają identyczny kontekst.

## Zestawienie wersji

| Element                   | Dane                                                      | Status                                                                 |
| ------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------- |
| Gra                       | _Kingdom Come: Deliverance_; numer kompilacji nieustalony | Sprawdzono pliki polskiej lokalizacji statycznie, bez testu w grze.    |
| Główny mod ARSI           | 1.3.3.1                                                   | Zbadano plik lokalizacyjny, tabelę `player_item` i ustawienia etykiet. |
| Szablon językowy          | 1.3.1 według przekazanego zrzutu listy Nexus Mods         | Różni się od lokalizacji ARSI 1.3.3.1; zobacz poniżej.                 |
| Polska lokalizacja bazowa | `Localization/Polish_xml.pak` z instalacji autora         | Porównano 11 tabel XML; nie potwierdza to zgodności runtime.           |
| Tłumaczenie niemieckie    | Nexus Mods, mod 2222                                      | Punkt odniesienia wskazany przez autora; nie analizowano jego plików.  |

## Co robią wpisy w szablonie

Tabela `player_item__ARealSortedInventory.xml` głównego moda ma 425 rekordów i 425 różnych wartości `ui_name`. Każda
wskazuje nazwę przedmiotu w interfejsie, a wszystkie te klucze występują w pliku lokalizacyjnym ARSI. Zatem wiele
wierszy szablonu to rzeczywiste etykiety przedmiotów używanych w ekwipunku, a nie przykładowe terminy.

Klucze `ui_arsi_*` są odrębnymi etykietami kategorii sortowania, nie nazwami przedmiotów. Skrypt głównego moda
udostępnia ustawienia `g_arsi_show_category_labels_*`, które sterują widocznością nagłówków. Kategorie należy tłumaczyć
jako krótkie, spójne nazwy; nie należy kopiować do nich automatycznie nazw poszczególnych przedmiotów.

## Porównanie z polską lokalizacją gry

Z 425 kluczy nazw przedmiotów:

- **88** występuje w polskich plikach gry pod identycznym kluczem; wszystkie 88 obecnych tłumaczeń w szablonie zgadza
  się z wartością gry po pominięciu białych znaków na początku i końcu.
- Pozostałych **337** kluczy `ui_name` nie znaleziono w polskich plikach gry pod tym samym identyfikatorem. Nie oznacza
  to automatycznie braku polskiego odpowiednika nazwy — może on występować pod innym kluczem.
- Dla **338** angielskich tekstów źródłowych znaleziono dopasowanie w polskich tabelach gry.
- **322** z tych dopasowań mają jeden jednoznaczny polski wariant; **316** obecnych tłumaczeń zgadza się z nim po
  pominięciu skrajnych białych znaków.
- **16** tekstów źródłowych prowadzi do więcej niż jednego polskiego wariantu i wymaga sprawdzenia kontekstu.
- **87** nazw nie ma dokładnego dopasowania tekstu źródłowego w polskich tabelach gry. Mogą pochodzić z dodatkowej
  zawartości albo wymagać sprawdzenia w innych lokalizacjach.

Sześć kluczy z jednoznacznym polskim odpowiednikiem, ale inną obecną wartością w szablonie:

| Klucz                    | Tekst angielski     | Obecny tekst w szablonie    | Odpowiednik w grze   |
| ------------------------ | ------------------- | --------------------------- | -------------------- |
| `ui_nm_jacket_002_racek` | Red pourpoint       | Red pourpoint               | Czerwony pourpoint   |
| `ui_nm_jacket_003_racek` | Blue pourpoint      | Blue pourpoint              | Niebieski pourpoint  |
| `ui_nm_hood_grey`        | Grey hood           | Grey hood                   | Szary kaptur         |
| `ui_nm_hood_blue_blue`   | Blue hood           | Blue hood                   | Niebieski kaptur     |
| `ui_nm_arrow_testing_X`  | Long-distance arrow | Lepsza dalekosiężna strzała | Dalekosiężna strzała |
| `ui_nm_test_03`          | Spear               | Spear                       | Włócznia             |

To lista do ręcznej weryfikacji, nie automatyczna propozycja zmiany: szczególnie `ui_nm_arrow_testing_X` może wymagać
kontekstu przedmiotu. W przypadku niejednoznacznych dopasowań należy sprawdzić przedmiot i jego źródło zamiast wybierać
wariant wyłącznie na podstawie angielskiego słowa.

Brak polskiej wartości pod kluczem `ui_name`, przy jednoczesnej obecności angielskiej wartości w pliku ARSI, jest
możliwym wyjaśnieniem zgłoszonego mieszania języków. To hipoteza zgodna ze statycznym porównaniem; dokładny fallback
musi być potwierdzony testem w grze.

## Różnice względem ARSI 1.3.3.1

- Główny plik lokalizacyjny ma **496 aktywnych wierszy**; wszystkie jego klucze znajdują się w szablonie projektu, który
  ma **498 wierszy**.
- `ui_arsi_weapons_dagger` i `ui_arsi_weapons_torch` są w głównym pliku lokalizacyjnym zakomentowane, ale występują jako
  aktywne wiersze w szablonie.
- Dla `ui_arsi_misc_skin` angielski tekst źródłowy w głównym modzie to `Skins`, a w szablonie `Skins & Hides`.

Szablon językowy jest opisany wersją 1.3.1, a sprawdzony główny pakiet — wersją 1.3.3.1. Różnice te należy rozstrzygnąć
przed wydaniem tłumaczenia.

## Status weryfikacji

Audyt jest porównaniem plików, nie testem runtime. Nie potwierdzono jeszcze konkretnej wersji gry, sposobu instalacji
ani zachowania fallbacku językowego. Repozytorium nie zawiera gotowego pakietu tłumaczenia. Przed publikacją należy:

1. ręcznie ocenić sześć rozbieżnych nazw i 16 niejednoznacznych dopasowań;
2. ustalić, czy zachować dwa dodatkowe nagłówki Dagger/Torch i uzgodnić `Skins` z `Skins & Hides`;
3. przetestować polskie tłumaczenie w grze z ARSI 1.3.3.1;
4. potwierdzić wymagane atrybucje i warunki dystrybucji.
