# Zastosowanie praktyczne. Implementacja wybranej metody szyfrowania.

## Wymagana wiedza

- Podstawy języka Python (lekcje 1-9)
- Intuicyjne rozumienie algorytmu jako listy kroków
- Podstawy myślenia analitycznego i krytyczne podejście do informacji
- Podstawowe metody szyfrowania

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. |
| V. Przestrzeganie prawa i zasad bezpieczeństwa. Uczeń: | |
| | 1) Opisuje kwestie etyczne związane z wykorzystaniem komputerów i sieci komputerowych, takie jak: **bezpieczeństwo**, cyfrowa tożsamość, **prywatność**, **równy dostęp do informacji i dzielenie się informacją**; | 
| IV. Rozwijanie kompetencji społecznych. Uczeń: | |
| | 1) bierze udział w różnych formach współpracy, jak: (...) realizacja projektów (...) tworzy i prezentuje efekty wspólnej pracy |

## Wstęp do projektu (10 minut)

Na poprzednich dwóch lekcjach poznawaliśmy różne metody szyfrowania, w tym szyfr Cezara oraz Leet Speak.

Program musi:
- Wczytać wiadomość do zakodowania (może zawierać spacje).
- Wykonać wybraną metodę szyfrowania - Cezara, ROT-13, Leet Speak, podstawieniowa.
- Wypisać zaszyfrowaną wiadomość oraz jaka metoda szyfrowania została wybrana.

Szkielet programu:

```Python
print("Podaj wiadomość do zakodowania")
wiadomosc = input()
wiadomosc_zakodowana = ""

# Algorytm kodujący

print(wiadomosc_zakodowana)
print("Zaszyfrowane metodą <METODA>")

```

## Samodzielna implementacja i pomysły na rozszerzenie programu (35+45 minut)

Dla chętnych, bazową wersję algorytmu mozna rozszerzyć o takie funkcjonalności, jak:
- Wsparcie dla liter języka polskiego
- Wybór metody szyfrowania (zaimplementowanie 2-3 metod)
- Szyfrowanie zawartości pliku tekstowego (wczytaj plik.txt i stwórz plik_zakodowany.txt)
- **TRUDNE**: Zaimplementuj metodę szyfrowania Rozier.

## Podsumowanie i prezentacja projektów

Po zakończeniu pracy każdy z uczniów prezentuje swój program nauczycielowi.
Testowanie własnego rozwiązania i wprowadzanie korekt to naturalna część pracy programisty.