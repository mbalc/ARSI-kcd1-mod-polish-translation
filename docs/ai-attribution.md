# Użycie AI, autorstwo i pochodzenie prac

**Rejestr rozpoczęty:** 16 listopada 2026 r.
**Cel:** zachować kontekst projektu i odróżnić decyzje autora od pracy wykonanej z pomocą AI.

## Role i odpowiedzialność

- **Autor projektu i polskiego przekładu:** mbalc, zgodnie z deklaracją autora.
- **Decyzje o zakresie:** mbalc. Projekt ma rozwiązać zgłoszony przez autora problem angielskich nazw pojawiających się wśród polskich nazw przedmiotów podczas korzystania z ARSI bez polskiego tłumaczenia.
- **Zakres pierwszego PR:** inicjalizacja projektu obejmująca dotychczasowe pliki i dokumentację. Raport zgodności oraz rejestr użycia AI są osobnymi dokumentami, do których README prowadzi odnośnikami.
- **Tekst README:** mbalc samodzielnie zredagował wprowadzenie i opis problemu w edytorze; te zmiany zachowano jako tekst autora.
- **Pomoc AI:** GitHub Copilot wykorzystano do odczytania i porównania plików lokalizacji oraz do przygotowania dokumentacji. AI nie zmieniało komórek tłumaczenia w `text__ARealSortedInventory[1].xml`.
- **Odpowiedzialność za tłumaczenie i wydanie:** wybór ostatecznych polskich nazw, ich zatwierdzenie, testy w grze i publikacja należą do mbalc. Wyniki porównania AI są wskazówkami do weryfikacji, nie zatwierdzonymi automatycznie poprawkami.

## Rejestr prac wspomaganych przez AI

### 2026-11-16 — analiza lokalizacji i dokumentacja

**Dane wejściowe:**

- projektowy szablon `text__ARealSortedInventory[1].xml`;
- archiwum ARSI 1.3.3.1 udostępnione do odczytu przez autora (`A Real Sorted Inventory 2204 1.3.3.1 2026-06-26T10-36Z M04BeYC8a.zip`);
- lokalizacja `Polish_xml.pak` z instalacji *Kingdom Come: Deliverance*, udostępniona wyłącznie do odczytu;
- wersje i opis problemu przekazane przez autora;
- [strona głównego ARSI](https://www.nexusmods.com/kingdomcomedeliverance/mods/2204) i [strona przykładowego tłumaczenia niemieckiego](https://www.nexusmods.com/kingdomcomedeliverance/mods/2222).

**Praca AI:**

- odczyt struktury archiwum ARSI, jego tabeli `player_item`, pliku lokalizacyjnego i ustawień etykiet kategorii;
- statyczne porównanie kluczy i tekstów angielskich z polskimi tabelami gry;
- przygotowanie raportu [`language-compatibility.md`](language-compatibility.md) oraz redakcja `README.md`;
- wskazanie różnic i niejednoznacznych dopasowań do ręcznej oceny.

**Ograniczenia:** problem mieszanych nazw został zgłoszony przez autora, ale nie odtworzony przez AI w grze. Nie wykonano testów runtime ani nie potwierdzono instalacji, zgodności wszystkich wersji lub licencji. Archiwum moda i pliki gry czytano bez modyfikowania ich; nie kopiowano ich do repozytorium. Tłumaczenie XML nie było edytowane przez AI.

### 2026-11-16 — automatyczne zawijanie Markdown

**Decyzja mbalc:** formatować pliki Markdown automatycznie przy zapisie, z szerokością 120 znaków; wybrano Prettier.

**Praca AI:** dodano konfigurację Prettier oraz ustawienia i rekomendację rozszerzenia dla Visual Studio Code. Konfiguracja obejmuje pliki Markdown. Nie zweryfikowano jej w edytorze z zainstalowanym rozszerzeniem.

## Źródła i atrybucje do potwierdzenia

- Główny mod i jego zasoby należą do ich autorów; [strona ARSI na Nexus Mods](https://www.nexusmods.com/kingdomcomedeliverance/mods/2204) jest punktem odniesienia. Pełne wymagane brzmienie kredytów i warunki dystrybucji trzeba potwierdzić przed publikacją.
- Szablon zawiera komentarz `UNIQUE ITEMS BY YASM`. Zakres autorstwa tych wpisów i wymagane atrybucje nie zostały niezależnie ustalone.
- [Tłumaczenie niemieckie na Nexus Mods](https://www.nexusmods.com/kingdomcomedeliverance/mods/2222) służy jako przykład sposobu udostępnienia lokalizacji, nie jako źródło polskich tekstów.
- Dane z lokalnej instalacji gry i pobranego archiwum ARSI nie są częścią tego repozytorium. Raport opisuje ich ścieżki wewnętrzne, nie ujawnia lokalnych ścieżek użytkownika.

## Proponowana informacja o pomocy AI

> Polski przekład i decyzje terminologiczne: mbalc. Przy analizie plików źródłowych, porównaniu lokalizacji i przygotowaniu dokumentacji wykorzystano pomoc AI (GitHub Copilot). AI nie edytowało wpisów tłumaczenia; sugerowane odpowiedniki wymagają oceny autora.

## Zasady aktualizacji rejestru

Przy kolejnych istotnych pracach wspomaganych przez AI dopisz datę, zakres, źródła i wersje analizowanych plików, wynik pracy AI, decyzję lub weryfikację autora oraz nierozstrzygnięte ograniczenia. Nie zapisuj tutaj prywatnych ścieżek instalacji ani nie przedstawiaj sugestii AI jako decyzji mbalc.
