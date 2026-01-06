# Funkcje w Pythonie – argumenty, wartości zwracane, funkcje wbudowane. Jak ułatwić sobie pisanie dużych programów?

## Wymagana wiedza

- Podstawy języka Python: instrukcje wejścia/wyjścia (input(), print()).
- Stosowanie zmiennych do przechowywania danych.
- Instrukcje warunkowe (if, else) do podejmowania decyzji przez program.

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, **funkcje** oraz zmienne i tablice. |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |

## Wstęp teoretyczny (przewidziany na około 10 minut)

Do tej pory pisaliśmy programy, które wykonywały się od góry do dołu. Jednak wraz ze wzrostem skomplikowania kodu, powtarzanie tych samych fragmentów staje się uciążliwe. Funkcje to wydzielone części programu, które mają swoją nazwę i mogą być wielokrotnie wywoływane, co ułatwia zarządzanie kodem i czyni go bardziej czytelnym.

Część funkcji już znamy, korzystaliśmy z nich w programach! Są to funkcje **wbudowane** w
język Python, otrzymujemy je "w pakiecie":

- `print()` wyświetla informacje na ekranie
- `input()` pobiera dane od użytkownika
- `int()` przekształca tekst na liczbę całkowitą
- `range()` generuje sekwencje (ciąg kolejnych wartości), korzystaliśmy z niej w pętli `for`

O funkcjach myślimy często jak o "robocie", który dla wejściowych danych wyprodukuje wynik, którego
potrzebujemy. W informatyce, uruchomienie funkcji nazywamy **wywołaniem**, a dane wejściowe nazywamy
**argumentami**. Argumentów może być zero, lub wiele. Wynik wywołania zwracany jest za pomocą komendy `return`.

![funkcja_obrazek](./lesson5-materials/funkcja.png)

Dla przykładu, argumentem dla funkcji `int()` jest słowo, a wynikiem jest liczba: `int("123")`
jako wynik zwraca liczbę `123`.

**Nowa funkcja** Zobaczmy działanie funkcji `len()`. Czy potrafisz odgadnąć, co robi?

```Python
wynik = len("kajak")
print(wynik)

wynik = len("ABC")
print(wynik)
```

Funkcje nie muszą zwracać wartości jako wyniku, jeśli to nie jest potrzebne. Na przykład `print("Hello World")` to funkcja, która wykonuje polecenie, ale jej wynik nie jest ważny. Ciekawostka: taka funkcja
zwraca specjalną wartość: `None`!

Przykład z życia:
- Automat z napojami: wrzucasz pieniądze (dane) - dostajesz napój (wynik), jak funkcja `int()`
- Domofon: naciskasz guzik i mówisz swoje imię (dane) - dzwoni, ale nic nie dostajesz do ręki, jak `print()`

## Jak tworzyć funkcje w Pythonie? (15 minut)

Funkcje w Pythonie piszemy następująco:

```Python
def nazwa_funkcji(argumenty):
    # Uwaga na wcięcie!
    logika
```

Uruchom i przetestuj poniższe funkcje:

```Python
def narysuj_ksztalt():
    print("....")
    print(".  .")
    print("....")

narysuj_ksztalt()
narysuj_ksztalt()
```

```Python
def przedstaw(imie):
    print("Witam, tu", imie)

przedstaw("Kasia")
przedstaw("Olek")
```

```Python
def plus_jeden(x):
    return x+1

# Uwaga: Funkcja zwraca wynik, więc go wypisujemy!
print(plus_jeden(5))
```

```Python
def suma(a, b, c):
    return a+b+c

# Uwaga: Funkcja zwraca wynik, więc go wypisujemy!
print(suma(1, 2, 3))
print(suma(3, -3, 0))
```

**Ciekawostka**: powiedzieliśmy, że funkcja `print()` nie zwraca wartości wywołania, tylko
`None`. Możemy to sprawdzić!

```Python
wynik_funkcji = print("Ala ma kota")
print(wynik_funkcji)
```

## Zadania do rozwiązania na komputerze (przewidziane na około 20 minut)

Zaimplementuj wybrane 3 funkcje z poniższej listy:

- **Powitanie 2.0**: Napisz funkcję powitanie(imie), która wypisze tekst „Witaj, [imie]! Miło Cię widzieć”. Wywołaj ją dla trzech różnych imion.
- **Kalkulator BMI**: Napisz funkcję oblicz_bmi(waga, wzrost), która zwróci wynik wskaźnika BMI ($$waga/wzrost^2$$). Następnie w programie głównym wczytaj dane, wywołaj funkcję i wypisz wynik.
- **Parzysta**: Napisz funkcję czy_parzysta(liczba), która zwraca True, jeśli liczba jest parzysta, i False w przeciwnym razie. Użyj jej w pętli wypisującej tylko parzyste liczby z zakresu od 1 do 20.
- **Pole trójkąta**: Napisz program z funkcją pole_trojkata(a, h), która pomoże Ci sprawdzić wyniki Twojej pracy domowej z matematyki.
- **Rysuj gwiazdki**: Napisz funkcję rysuj_linie(dlugosc), która wypisuje ciąg gwiazdek o podanej długości. Użyj jej, aby narysować choinkę.
- **Chemia – masa molowa**: Napisz funkcję masa_molowa(masa, liczba_moli), która zwróci masę molową substancji. Następnie w programie głównym wczytaj dane i wypisz wynik.
- **Matematyka – średnia ocen**: Napisz funkcję srednia_ocen(oceny), która zwróci średnią arytmetyczną ocen zapisanych w liście. Sprawdź wynik dla przykładowych ocen.
- **Geografia – temperatura**: Napisz funkcję c_na_f(celsiusz), która zamienia stopnie Celsjusza na Fahrenheity. Użyj jej dla trzech różnych temperatur.
- **Historia – wiek postaci**: Napisz funkcję wiek_postaci(rok_urodzenia, rok_wydarzenia), która zwróci wiek historycznej postaci w danym roku.
- **Fizyka – droga**: Napisz funkcję oblicz_droge(predkosc, czas), która zwróci drogę przebytą przez ciało (droga=predkosc*czas). Sprawdź wynik dla przykładowych danych.

## Zadania do rozwiązania na platformie Szkopuł

### Podaj długość słowa

Zastosuj funkcję `len()` w praktyce.

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/SAuc7UAS2ZnCLOMrnfURVcr5/site/?key=statement){ .md-button .md-button--primary }

### Kwadrat 0

Napisz funkcję, która rysuje kwadrat za pomocą ASCII.

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/m7d6WQdRnYjrZQo6s3g6v5hY/site/?key=statement){ .md-button .md-button--primary }