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

## Spójność z polską lokalizacją gry

Nazwy konkretnych przedmiotów należy porównywać z polską lokalizacją *Kingdom Come: Deliverance*.
Jeśli przedmiot ma już ustaloną nazwę w grze, używaj jej konsekwentnie zamiast tworzyć nowy wariant.
Dla kategorii dodanych przez ARSI, które nie mają odpowiednika w grze,
przyjmij spójne polskie nazewnictwo i stosuj je w całym tłumaczeniu.

Wstępne porównanie z polskim plikiem gry `Localization/Polish_xml.pak` → `text_ui_items.xml` wykonano w trybie tylko do odczytu.
Spośród 498 wierszy szablonu 348 ma angielski tekst źródłowy występujący również w tej tabeli;
dla 339 z nich znaleziono jednoznaczny polski odpowiednik. Obecne tłumaczenie zgadza się z nim
(po pominięciu białych znaków na początku i końcu) w 319 przypadkach. W pozostałych 20 przypadkach
12 dotyczy nazw kategorii ARSI, a 8 nazw przedmiotów — te wpisy wymagają ręcznego sprawdzenia.

To dopasowanie po tekście źródłowym jest wskazówką, nie pełnym audytem wszystkich plików gry ani gwarancją,
że każde wystąpienie ma ten sam kontekst. Główny pakiet ARSI nie znajduje się w repozytorium,
więc znaczenie kategorii dodanych przez mod wymaga jeszcze weryfikacji. Przy pracy nad XML-em zachowuj
klucze i teksty źródłowe, a zmieniaj wyłącznie pola tłumaczenia.

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
