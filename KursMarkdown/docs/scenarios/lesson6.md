# Lekcja 6 – Funkcje w Pythonie – argumenty, wartości zwracane, funkcje wbudowane. Jak ułatwić sobie pisanie dużych programów?

**Czas realizacji:** 45 minut (1 godzina lekcyjna). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Podstawy języka Python: instrukcje wejścia/wyjścia (`input()`, `print()`).

- Stosowanie zmiennych do przechowywania danych.

- Instrukcje warunkowe (`if`, `else`) do podejmowania decyzji przez program.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, **funkcje** oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |

## Wstęp teoretyczny (przewidziany na około 10 minut)

Do tej pory pisaliśmy programy, które wykonywały się od góry do dołu. Jednak wraz ze wzrostem złożoności kodu powtarzanie tych samych fragmentów staje się uciążliwe. Funkcje to wydzielone części programu, które mają swoją nazwę i mogą być wielokrotnie wywoływane, co ułatwia zarządzanie kodem i czyni go bardziej czytelnym.

Część funkcji już znamy – korzystaliśmy z nich w programach. Są to funkcje **wbudowane** w
język Python, otrzymujemy je „w pakiecie”:

- `print()` wyświetla informacje na ekranie;

- `input()` pobiera dane od użytkownika;

- `int()` przekształca tekst na liczbę całkowitą;

- `range()` tworzy sekwencję liczb całkowitych; korzystaliśmy z niej w pętli `for`.

O funkcjach myślimy często jak o „robocie”, który dla wejściowych danych wyprodukuje wynik, którego
potrzebujemy. Uruchomienie funkcji nazywamy **wywołaniem**, a dane wejściowe nazywamy
**argumentami**. Funkcja może przyjmować zero lub więcej argumentów, zgodnie z jej definicją. Wynik wywołania zwracany jest za pomocą instrukcji `return`.

![funkcja_obrazek](./lesson6-materials/funkcja.png)

Dla przykładu, argumentem funkcji `int()` może być napis reprezentujący liczbę całkowitą, a wynikiem jest liczba: `int("123")`
jako wynik zwraca liczbę `123`.

### Nowa funkcja

Zobaczmy działanie funkcji `len()`. Czy potrafisz odgadnąć, co robi?

```python
wynik = len("kajak")
print(wynik)

wynik = len("ABC")
print(wynik)
```

Funkcja może wykonywać działanie bez zwracania użytecznego wyniku. Na przykład `print()` wyświetla tekst i zwraca specjalną wartość `None`.

Przykład z życia:

- Automat z napojami: wrzucasz pieniądze (dane) – dostajesz napój (wynik), jak funkcja `int()`.

- Domofon: naciskasz guzik i mówisz swoje imię (dane) – dzwoni, ale nic nie dostajesz do ręki, jak `print()`.

## Jak tworzyć funkcje w Pythonie? (15 minut)

Funkcje w Pythonie piszemy następująco:

```python
def nazwa_funkcji(argumenty):
    # Uwaga na wcięcie!
    logika
```

Uruchom i przetestuj poniższe funkcje:

```python
def narysuj_ksztalt():
    print("....")
    print(".  .")
    print("....")

narysuj_ksztalt()
narysuj_ksztalt()
```

```python
def przedstaw(imie):
    print("Witam, tu", imie)

przedstaw("Kasia")
przedstaw("Olek")
```

```python
def plus_jeden(x):
    return x+1

# Uwaga: Funkcja zwraca wynik, więc go wypisujemy!
print(plus_jeden(5))
```

```python
def suma(a, b, c):
    return a+b+c

# Uwaga: Funkcja zwraca wynik, więc go wypisujemy!
print(suma(1, 2, 3))
print(suma(3, -3, 0))
```

**Ciekawostka**: powiedzieliśmy, że funkcja `print()` zwraca specjalną wartość `None`. Możemy to sprawdzić!

```python
wynik_funkcji = print("Ala ma kota")
print(wynik_funkcji)
```

## Zadania do rozwiązania na komputerze (przewidziane na około 20 minut)

Zaimplementuj wybrane 3 funkcje z poniższej listy:

- **Powitanie 2.0**: Napisz funkcję `powitanie(imie)`, która wypisze tekst „Witaj, [imie]! Miło cię widzieć”. Wywołaj ją dla trzech różnych imion.

- **Kalkulator BMI**: Napisz funkcję `oblicz_bmi(waga, wzrost)`, która zwróci wartość wskaźnika BMI ($masa/wzrost^2$). Parametr `waga` oznacza masę w kilogramach, a dodatni `wzrost` jest podany w metrach. Następnie w programie głównym wczytaj dane, wywołaj funkcję i wypisz wynik.

- **Parzysta**: Napisz funkcję `czy_parzysta(liczba)`, która zwraca True, jeśli liczba jest parzysta, i False w przeciwnym razie. Użyj jej w pętli wypisującej tylko parzyste liczby z zakresu od 1 do 20.

- **Pole trójkąta**: Napisz program z funkcją `pole_trojkata(a, h)`, która pomoże ci sprawdzić wyniki twojej pracy domowej z matematyki.

- **Rysuj gwiazdki**: Napisz funkcję `rysuj_linie(dlugosc)`, która wypisuje ciąg gwiazdek o podanej długości. Użyj jej, aby narysować choinkę.

- **Chemia – masa molowa**: Napisz funkcję `masa_molowa(masa, liczba_moli)`, która zwróci masę molową substancji. Następnie w programie głównym wczytaj dane i wypisz wynik.

- **Matematyka – średnia ocen**: Napisz funkcję `srednia_ocen(oceny)`, która zwróci średnią arytmetyczną ocen zapisanych na niepustej liście. Sprawdź wynik dla przykładowych ocen.

- **Geografia – temperatura**: Napisz funkcję `c_na_f(celsiusz)`, która zamienia stopnie Celsjusza na stopnie Fahrenheita. Użyj jej dla trzech różnych temperatur.

- **Historia – wiek postaci**: Napisz funkcję `wiek_postaci(rok_urodzenia, rok_wydarzenia)`, która zwróci przybliżony wiek historycznej postaci jako różnicę lat (bez uwzględnienia daty urodzin).

- **Fizyka – droga**: Napisz funkcję `oblicz_droge(predkosc, czas)`, która zwróci drogę przebytą przez ciało (droga=predkosc*czas). Sprawdź wynik dla przykładowych danych.

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### Podaj długość słowa

Zastosuj funkcję `len()` w praktyce.

Wczytaj słowo, a następnie podaj jego długość. Możesz założyć, że słowo będzie miało najwyżej 15 znaków.

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/SAuc7UAS2ZnCLOMrnfURVcr5/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/SAuc7UAS2ZnCLOMrnfURVcr5/site/?key=statement).

### Kwadrat

**Uwaga: kod rysujący kwadrat powinien znajdować się w funkcji `kwadrat(n)`.**

Napisz program, w którym użytkownik wprowadzi jedną liczbę nieparzystą $n$.

Twoim zadaniem jest wypisanie wzoru o wymiarach $n \times n$ złożonego ze znaków `@`.

Do wczytania danych wykorzystaj polecenie `n = int(input())`.

#### Wejście

W jedynym wierszu wejścia znajduje się jedna nieparzysta liczba całkowita $n$ ($2 < n < 1002$).

#### Wyjście

Na wyjściu wypisz $n$ wierszy po $n$ znaków w każdym, tworzących wzór złożony ze znaków `@`.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 5 | @@@@@<br>@@@@@<br>@@@@@<br>@@@@@<br>@@@@@ |
| 7 | @@@@@@@<br>@@@@@@@<br>@@@@@@@<br>@@@@@@@<br>@@@@@@@<br>@@@@@@@<br>@@@@@@@ |

??? tip "Wskazówka"
    W Pythonie możesz wypisać wiele razy ten sam znak, korzystając z mnożenia: `'#'*5`

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/m7d6WQdRnYjrZQo6s3g6v5hY/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/m7d6WQdRnYjrZQo6s3g6v5hY/site/?key=statement).
