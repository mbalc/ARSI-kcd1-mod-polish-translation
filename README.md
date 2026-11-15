# Polskie tłumaczenie A Real Sorted Inventory

Polski przekład tekstów z szablonu językowego moda [**A Real Sorted Inventory (ARSI)**](https://www.nexusmods.com/kingdomcomedeliverance/mods/2204)
do gry *Kingdom Come: Deliverance*. Projekt ma udostępniać polską wersję językową jako dodatek
do ARSI — nie jest samodzielnym modem ani tłumaczeniem całej gry.

## Zakres

Tłumaczone są wpisy znajdujące się w szablonie językowym ARSI. Zmiany dotyczą tekstów i nie mają zmieniać działania ani ustawień
sortowania w oryginalnym modzie.

W repozytorium znajduje się plik `text__ARealSortedInventory[1].xml`, zawierający klucze, teksty źródłowe i pola tłumaczenia.
Część nazw unikatowych przedmiotów jest już po polsku, ale nagłówki kategorii pozostają po angielsku,
a w pliku wskazano też pozycje wymagające tłumaczenia. **Przekład jest nieukończony.**

## Spójność i kontekst tłumaczeń

W tabeli moda `player_item__ARealSortedInventory.xml` każde z 425 unikatowych pól `ui_name`
wskazuje klucz nazwy wyświetlanej przy konkretnym przedmiocie. Wszystkie te klucze występują
w pliku lokalizacyjnym ARSI. To znaczy, że wpisy z nazwami przedmiotów nie są tylko opisowymi
przykładami — są tekstami używanymi przez mod przy sortowaniu ekwipunku.

Porównanie z 11 tabelami XML w `Localization/Polish_xml.pak` gry wykonano w trybie tylko do odczytu.
88 z 425 kluczy przedmiotów występuje w grze pod tym samym kluczem; wszystkie 88 obecnych polskich
wpisów w szablonie zgadza się z lokalizacją gry po pominięciu białych znaków na początku i końcu.
Dodatkowo, przy dopasowaniu po identycznym angielskim tekście źródłowym, 338 nazw ma odpowiednik
w tych tabelach; 322 z nich mają jednoznaczny polski wariant, a 316 obecnych tłumaczeń zgadza się
z tym wariantem. Sześć rozbieżnych kluczy to `ui_nm_jacket_002_racek`, `ui_nm_jacket_003_racek`,
`ui_nm_hood_grey`, `ui_nm_hood_blue_blue`, `ui_nm_arrow_testing_X` i `ui_nm_test_03` — sprawdź je
ręcznie przed zmianą. Dla 16 dopasowanych nazw istnieje więcej niż jeden polski wariant, a 87 nazw
nie ma dokładnego dopasowania w tabelach gry; te przypadki wymagają sprawdzenia kontekstu lub
lokalizacji źródłowego moda.

Klucze `ui_arsi_*` oznaczają natomiast nagłówki kategorii sortowania ARSI, a nie nazwy przedmiotów.
Główny mod udostępnia ustawienia widoczności tych etykiet, więc tłumacz je jako krótkie, spójne nazwy
kategorii.

### Różnice względem ARSI 1.3.3.1

W pliku lokalizacyjnym głównego moda jest 496 aktywnych wierszy; wszystkie ich klucze znajdują się
w tym szablonie, który ma łącznie 498 wierszy. Dodatkowe `ui_arsi_weapons_dagger` i
`ui_arsi_weapons_torch` są zakomentowane w pliku głównego moda. Jest też jedna różnica w tekście
źródłowym: dla `ui_arsi_misc_skin` główny mod ma `Skins`, a szablon `Skins & Hides`.
Sprawdź te różnice przed przygotowaniem wydania tłumaczenia.

Przy edycji zachowuj klucze i teksty źródłowe, a zmieniaj wyłącznie pola tłumaczenia.

## Wymagania i wersje

- Wymagany jest oryginalny mod [A Real Sorted Inventory](https://www.nexusmods.com/kingdomcomedeliverance/mods/2204).
- Wersja głównego moda widoczna na Nexus Mods: **1.3.3.1**.
- Szablon językowy na stronie moda jest oznaczony wersją **1.3.1**.
- Zgodność tego szablonu z wersją 1.3.3.1 oraz wymagana wersja gry: **do potwierdzenia**.

## Instalacja

Repozytorium zawiera plik szablonu XML, a nie gotowy pakiet do instalacji. Sposób instalacji i dystrybucji polskiej wersji: **do uzupełnienia po przygotowaniu i przetestowaniu pakietu**.

Docelowo polska wersja ma działać jako tłumaczenie do ARSI, analogicznie do wskazanej [wersji niemieckiej](https://www.nexusmods.com/kingdomcomedeliverance/mods/2222). Jej dokładna procedura instalacji nie została jeszcze potwierdzona.

## Autorstwo

- Polski przekład: **mbalc**.
- Podstawą pracy jest szablon językowy ARSI. Informacje o wymaganych atrybucjach i warunkach dalszej dystrybucji: **do uzupełnienia**.
