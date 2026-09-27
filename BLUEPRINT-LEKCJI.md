# Blueprint do tworzenia lekcji

Skopiuj cały prompt poniżej do ChatGPT. Uzupełnij wyłącznie sekcję **DANE LEKCJI** i dołącz potrzebne materiały. ChatGPT powinien przygotować jeden gotowy plik, który wystarczy dodać do katalogu strony, zatwierdzić i wysłać na GitHub.

## Prompt

````text
Tworzysz kompletną stronę HTML z materiałami do lekcji Roblox Studio.

DANE LEKCJI:
- Temat: [WPISZ TEMAT]
- Data lekcji: [RRRR-MM-DD]
- Krótki opis: [OPCJONALNIE]
- Materiały i skrypty Lua:
[WKLEJ TUTAJ KODY ORAZ INFORMACJE, GDZIE NALEŻY JE UMIEŚCIĆ]

WYMAGANIA:

1. Zwróć jeden kompletny plik HTML gotowy do zapisania i opublikowania na GitHub Pages.

2. Pierwszymi znakami pliku muszą być metadane Jekyll. Nie umieszczaj przed nimi komentarza ani deklaracji HTML:

---
layout: null
lesson: true
title: "[czytelny tytuł lekcji]"
date: [data lekcji w formacie RRRR-MM-DD]
description: "[jedno krótkie zdanie opisujące zawartość]"
permalink: /[krotki-slug-bez-polskich-znakow]/
---

3. Samodzielnie utwórz:
   - czytelny tytuł,
   - jednozdaniowy opis,
   - krótki slug bez polskich znaków,
   - proponowaną nazwę pliku w formacie RRRR-MM-DD-slug.html.

4. Po metadanych umieść pełny dokument zaczynający się od <!doctype html>. Strona musi być:
   - po polsku,
   - zapisana w UTF-8,
   - czytelna dla dzieci,
   - responsywna na telefonie i komputerze,
   - pozbawiona zewnętrznych bibliotek,
   - zgodna z GitHub Pages.

5. Zachowaj spójny, prosty wygląd: jasne tło, białe sekcje, granatowe bloki kodu, niebieskie przyciski i duże czytelne nagłówki.

6. Na początku strony dodaj link „← Wróć do wszystkich lekcji” prowadzący do „/”.

7. Każdy skrypt Lua umieść w osobnej sekcji zawierającej:
   - zrozumiałą nazwę,
   - dokładną lokalizację w Roblox Studio, np. „Workspace → Lawa → Script”,
   - krótkie wyjaśnienie działania,
   - blok <pre> z kodem,
   - przycisk „Kopiuj kod”.

8. Każdy blok kodu oraz jego przycisk kopiowania muszą używać tego samego, unikalnego identyfikatora. Nie powtarzaj identyfikatorów w dokumencie.

9. Przycisk kopiowania ma używać navigator.clipboard. Po sukcesie powinien przez 1800 ms wyświetlać „Skopiowano ✓”, a w przypadku błędu „Zaznacz kod ręcznie”.

10. Poprawnie zabezpiecz kod wyświetlany wewnątrz HTML:
    - & zapisuj jako &amp;,
    - < zapisuj jako &lt;,
    - > zapisuj jako &gt;,
    - znaki potrzebne składni HTML zapisuj jako encje.
   Kod skopiowany przez użytkownika ma jednak zawierać normalne znaki Lua, ponieważ przeglądarka dekoduje encje w textContent.

11. Nie zmieniaj działania przekazanych skryptów Lua. Możesz poprawić formatowanie i wcięcia. Jeżeli zauważysz błąd logiczny, opisz go dopiero po wygenerowanym pliku, bez cichego zmieniania kodu.

12. Nie dodawaj reklam, analityki, zewnętrznych fontów, frameworków ani linków do innych serwisów.

13. Sprawdź przed odpowiedzią, czy:
    - metadane zawierają lesson: true,
    - data ma format RRRR-MM-DD,
    - permalink zaczyna i kończy się ukośnikiem,
    - wszystkie znaczniki HTML są zamknięte,
    - każdy przycisk kopiuje właściwy kod,
    - polskie znaki są poprawne.

FORMAT ODPOWIEDZI:

Najpierw podaj proponowaną nazwę pliku w jednej krótkiej linii.

Następnie zwróć kompletną zawartość pliku w jednym bloku ```html```. Nie dziel kodu na fragmenty i niczego nie pomijaj.
````

## Publikowanie nowej lekcji

1. Utwórz plik o nazwie zaproponowanej przez ChatGPT.
2. Wklej do niego cały wygenerowany kod — razem z metadanymi pomiędzy liniami `---`.
3. Dodaj plik do tego samego katalogu co `index.html`.
4. Wykonaj commit i push do gałęzi publikowanej przez GitHub Pages.
5. Po przebudowaniu strony nowa lekcja automatycznie pojawi się na początku listy.

Nie trzeba ręcznie zmieniać `index.html`.
