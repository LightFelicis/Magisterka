# Lekcja 13 – Własności liczb – podzielność, suma cyfr i iloczyn cyfr

**Czas realizacji:** 90 minut (2 godziny lekcyjne). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Pętle `while` oraz `for`.

- Operatory `%` (modulo) oraz `//` (dzielenie całkowite).

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |

## Wstęp teoretyczny (15 minut)

Operacje na cyfrach omawiamy dla nieujemnych liczb całkowitych. Liczba 0 ma jedną cyfrę, a iloczyn jej cyfr wynosi 0; w tych zadaniach obsłuż ten przypadek osobno.

Aby wyznaczyć ostatnią cyfrę liczby, używamy operacji `n % 10`.
Aby „pozbyć się” ostatniej cyfry, używamy operacji dzielenia całkowitego `n // 10`.

Przykład dla liczby 123:

- `123 % 10 = 3`

- `123 // 10 = 12`

## Wspólne eksperymenty (15 minut)

Przeanalizujmy algorytm sumujący cyfry liczby:

```python
n = int(input("Podaj liczbę: "))
suma = 0
while n > 0:
    cyfra = n % 10
    suma = suma + cyfra
    n = n // 10
print("Suma cyfr wynosi:", suma)
```

Algorytm „obcina” kolejne cyfry, dodając je do wyniku.

Przeanalizujmy algorytm dla `n = 123`:

W pierwszej iteracji pętli w zmiennej `cyfra` zostanie zapisana wartość `3`.
Suma zostanie zwiększona o `3`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `12`.

W kolejnej iteracji pętli w zmiennej `cyfra` zostanie zapisana wartość `2`.
Suma zostanie zwiększona o `2`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `1`.

W kolejnej iteracji pętli w zmiennej `cyfra` zostanie zapisana wartość `1`.
Suma zostanie zwiększona o `1`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `0`.

Po zakończeniu pętli w zmiennej `suma` znajduje się wartość `6`.

## Zadania do rozwiązania (60 minut)

1. **Iloczyn cyfr**: Zmodyfikuj powyższy program tak, aby obliczał iloczyn cyfr podanej liczby.

!!! tip "Wskazówka"
    Pamiętaj, że dla iloczynu początkowa wartość zmiennej przechowującej iloczyn powinna wynosić 1, a nie 0!

2. **Liczba cyfr**: Napisz program, który policzy, ile cyfr ma podana liczba.

!!! tip "Wskazówka"
    Przy każdej iteracji pętli zwiększaj zmienną pomocniczą `ile_cyfr` o 1.

3. **Podzielność**: Napisz program, który wczyta liczbę i sprawdzi, czy jest ona podzielna przez sumę swoich cyfr.

!!! tip "Wskazówka"
    Najpierw oblicz sumę cyfr, a później za pomocą polecenia `%` sprawdź, czy liczba jest podzielna przez obliczoną sumę cyfr.
    Uwaga: po zakończeniu pętli wartość `n` będzie równa `0`. Przed rozpoczęciem pętli zapisz początkową wartość liczby w osobnej zmiennej. Nie wykonuj dzielenia przez zero: dla liczby 0 suma cyfr wynosi 0.

4. **Suma parzystych cyfr**: Napisz program, który obliczy sumę tylko tych cyfr liczby, które są parzyste.

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### Atak na mleczarnię

![mleko](./lesson13-materials/krowa.png)

Mleczarnia *Rogate Mleko* dostarcza mleko do centrali *Rzeka Mleka*. Centrala każdego dnia wysyła depeszę z informacją, ile potrzeba mleka.

Depesza z centrali to ciąg oddzielonych spacją znaków. Gdy dodamy wszystkie cyfry z depeszy, otrzymamy liczbę litrów mleka, które mleczarnia musi wysłać.

Niestety depesze są nagminnie atakowane i zmieniane przez wrogich hakerów. Wplatają oni w ciąg dodatkowe znaki – litery, przecinki, średniki, wykrzykniki itp. Na szczęście hakerzy nie dodają żadnych dodatkowych cyfr.

Twoim zadaniem jest napisanie programu, który odrzuci z depeszy wszystkie znaki niebędące cyframi i obliczy sumę cyfr znajdujących się w wiadomości.

Do wczytania danych wykorzystaj polecenia:
`import sys`
`dane = sys.stdin.read().split()`

#### Wejście

W pierwszym wierszu znajduje się jedna liczba całkowita $n$ ($1 \le n \le 10^6$), oznaczająca liczbę znaków w depeszy.

W drugim wierszu znajduje się $n$ znaków oddzielonych spacjami.

#### Wyjście

W jedynym wierszu wyjścia wypisz jedną liczbę całkowitą – sumę wszystkich cyfr znajdujących się w depeszy.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 9<br>x 4 ! 3 4 * 8 2 2 | 23 |

*Wyjaśnienie:*
Depesza zawiera cyfry: $4, 3, 4, 8, 2, 2$. Suma tych cyfr wynosi $4 + 3 + 4 + 8 + 2 + 2 = 23$.

??? tip "Wskazówka"
    Napisz funkcję pomocniczą `czy_cyfra`, która sprawdzi kod ASCII kolejnych znaków.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/anm/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/anm/site/?key=statement).


### Patrol

Przez pustkowia, pędząc na motocyklach o napędzie nuklearnym z prędkością tysiąca mil na godzinę, porusza się patrol. A dokładniej – poruszał się, bo teraz jego członkowie stoją w miejscu i uzupełniają paliwo w reaktorach. To dobry moment na pochwalenie się przebiegiem pojazdów – udało ci się nawet zobaczyć jedną z tych wartości. Całkiem ładna liczba $n$, chociaż byłaby ładniejsza, gdyby składała się z jednakowych cyfr.

Uzupełnianie paliwa jeszcze trochę potrwa, więc znajdź w tym czasie najmniejszą liczbę $k$ składającą się z jednakowych cyfr, dla której zachodzi $n \le k$.

Do wczytania danych wykorzystaj polecenie `n_str = input().strip()`.

#### Wejście

W pierwszym wierszu znajduje się jedna dodatnia liczba całkowita $n$ ($1 \le n \le 10^{10\,000}$), oznaczająca zaobserwowany przebieg motocykla patrolowego.

#### Wyjście

Na wyjściu wypisz jedną liczbę całkowitą $k$ składającą się z jednakowych cyfr, będącą najmniejszą taką liczbą spełniającą warunek $k \ge n$.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 9 | 9 |
| 329 | 333 |
| 797 | 888 |

??? tip "Wskazówka"
    Ponieważ $n$ może mieć aż $10\,001$ cyfr, potraktuj ją jako napis (ciąg znaków), a nie klasyczną liczbę.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/ew5Aw-TuOaBMVIC3EkFJKP9G/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/ew5Aw-TuOaBMVIC3EkFJKP9G/site/?key=statement).
