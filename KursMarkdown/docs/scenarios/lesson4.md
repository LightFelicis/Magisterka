## Zastosowanie praktyczne: Quiz. Jak użyć tego co umiem?

## Wymagana wiedza

- Podstawy języka Python: instrukcje wejścia/wyjścia (input(), print()).
- Stosowanie zmiennych do przechowywania danych.
- Instrukcje warunkowe (if, else) do podejmowania decyzji przez program.

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, **instrukcje iteracyjne**, funkcje oraz zmienne i tablice. |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| IV. Rozwijanie kompetencji społecznych. Uczeń: | |
| | 1) bierze udział w różnych formach współpracy, jak: (...) realizacja projektów (...) tworzy i prezentuje efekty wspólnej pracy |

## Wstęp do projektu (10 minut)

Zamiast rozwiązywać krótkie zadania, uczniowie stworzą kompleksowy program – Quiz, który będzie sprawdzał wiedzę użytkownika na wybrany temat (np. sport, historia, gry wideo). Program musi:
- Zadawać pytania.
- Pobierać odpowiedzi od użytkownika.
- Reagować na to, czy odpowiedź jest poprawna (używając instrukcji warunkowych).

Szkielet gry:

```Python
# Powitanie i przygotowanie zmiennej na punkty
print("Witaj w Wielkim Quizie Wiedzy!")

# Pytanie 1
print("Jak nazywa się stolica Polski?")
print("A. Warszawa B. Kraków C. Żyrardów D. Poznań")
odpowiedz1 = input()


if odpowiedz1 == "A":
    print("Brawo! To poprawna odpowiedź.")
else:
    print("Niestety, to błąd. Koniec gry!")
    exit() # Program kończy działanie przy złej odpowiedzi

# Tutaj dodaj kolejne pytania...
```

## Samodzielna implementacja i pomysły na rozszerzenie programu (35 minut)

Dla chętnych, bazową wersję gry mozna rozszerzyć o takie funkcjonalności, jak:
- Koła ratunkowe, na przykład odrzucenie połowy odpowiedzi
- System akceptujący zarówno odpowiedź "A", "a", słowną: "Warszawa"
- Punkty i gwarantowane wygrane
- Dodaj system ocen na koniec gry (np. jeśli punkty > 5, wypisz „Jesteś ekspertem!”)

## Podsumowanie i prezentacja projektów

Po zakończeniu pracy każdy z uczniów prezentuje swój quiz klasie na rzutniku. Wspólne omawianie wyników i rozgrywka
sprzyjają budowaniu kompetencji społecznych i pozwala na wymianę doświadczeń programistycznych. 
Testowanie własnego rozwiązania i wprowadzanie korekt to naturalna część pracy programisty.
