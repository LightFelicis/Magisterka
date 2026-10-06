# Lekcja 12 – Zastosowanie praktyczne – implementacja wybranej metody szyfrowania lub kodowania

**Czas realizacji:** 90 minut (2 godziny lekcyjne). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Podstawy języka Python (lekcje 1–9).

- Intuicyjne rozumienie algorytmu jako listy kroków.

- Podstawy myślenia analitycznego i krytyczne podejście do informacji.

- Podstawowe metody szyfrowania.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |
| V. Przestrzeganie prawa i zasad bezpieczeństwa. Uczeń: | |
| | 1) opisuje kwestie etyczne związane z wykorzystaniem komputerów i sieci komputerowych, takie jak: **bezpieczeństwo**, cyfrowa tożsamość, **prywatność**, własność intelektualna, **równy dostęp do informacji i dzielenie się informacją**; |
| IV. Rozwijanie kompetencji społecznych. Uczeń: | |
| | 1) bierze udział w różnych formach współpracy, jak: […] realizacja projektów, […] projektuje, tworzy i prezentuje efekty wspólnej pracy; |

## Wstęp do projektu (10 minut)

Na poprzednich dwóch lekcjach poznaliśmy szyfr Cezara i ROT13 oraz sposób zapisu leet speak.

Program musi:

- wczytać wiadomość do przetworzenia (może zawierać spacje);

- przetworzyć wiadomość wybraną metodą: szyfrem Cezara, ROT13, szyfrem podstawieniowym lub zapisem leet speak;

- wypisać przetworzoną wiadomość oraz nazwę zastosowanej metody.

Szkielet programu:

```python
print("Podaj wiadomość do zakodowania")
wiadomosc = input()
wiadomosc_zakodowana = ""

# Algorytm kodujący

print(wiadomosc_zakodowana)
print("Przetworzone metodą <METODA>")

```

## Samodzielna implementacja i pomysły na rozszerzenie programu (45 minut)

Chętni mogą rozszerzyć podstawową wersję programu o następujące elementy:

* obsługę polskich liter;

* wybór metody szyfrowania lub kodowania (zaimplementowanie 2–3 metod);

* szyfrowanie zawartości pliku tekstowego (wczytaj `plik.txt` i stwórz `plik_zakodowany.txt`).

## Podsumowanie i prezentacja projektów (35 minut)

Po zakończeniu pracy każdy z uczniów prezentuje swój program nauczycielowi.
Testowanie własnego rozwiązania i wprowadzanie korekt to naturalna część pracy programisty.
