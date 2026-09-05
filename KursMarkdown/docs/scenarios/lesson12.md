# Własności liczbowe – podzielność, suma cyfr, iloczyn cyfr

## Wymagana wiedza

- Pętle `while` oraz `for`
- Operatory `%` (modulo) oraz `//` (dzielenie całkowite)

## Treści z podstawy programowej

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. | 1) Formułuje problem w postaci specyfikacji i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów. | 1) W programach stosuje: instrukcje wejścia/wyjścia, wyrażenia arytmetyczne, pętle. |

## Wstęp teoretyczny (15 minut)

Aby wyciągnąć ostatnią cyfrę liczby, używamy operacji `n % 10`. 
Aby "pozbyć się" ostatniej cyfry, używamy operacji dzielenia całkowitego `n // 10`.

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

Algorytm "obcina" kolejne cyfry, dodając je do wyniku.

Przeanalizujmy algorym dla `n = 123`:

W pierwszym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `3`.
Suma zostanie zwiększona o `3`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `12`.

W kolejnym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `2`.
Suma zostanie zwiększona o `2`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `1`.

W kolejnym obrocie pętli, w zmiennej `cyfra` zostanie zapisana wartość `1`.
Suma zostanie zwiększona o `1`, a nowa wartość `n` po podzieleniu **całkowitym** przez `10` będzie równa `0`.

Po zakończeniu pętli w zmiennej `suma` znajduje się wartość `6`.

## Zadania do rozwiązania (60 minut)

1. **Iloczyn cyfr**: Zmodyfikuj powyższy program tak, aby obliczał iloczyn cyfr podanej liczby.

!!! Wskazówka
    Pamiętaj, że dla iloczynu zmienna początkowa powinna wynosić 1, a nie 0!

2. **Liczba cyfr**: Napisz program, który policzy, ile cyfr ma podana liczba.

!!! Wskazówka
    Przy każdym obrocie pętli zwiększaj zmienną pomocniczą `ile_cyfr` o 1.

3. **Podzielność**: Napisz program, który wczyta liczbę i sprawdzi, czy jest ona podzielna przez sumę swoich cyfr.

!!! Wskazówka
    Najpierw oblicz sumę cyfr, a później za pomocą polecenia `%` sprawdź, czy liczba jest podzielna przez `suma`.
    Uwaga, wartość `n` będzie równa `0` na koniec pętli! Zapisz sobie jej początkową wartość w zmiennej.

4. **Suma parzystych cyfr**: Napisz program, który obliczy sumę tylko tych cyfr liczby, które są parzyste.

## Zadania do rozwiązania na platformie Szkopuł

### Atak na mleczarnię

![mleko](./lesson12-materials/krowa.png)

Mleczarnia *Rogate Mleko* dostarcza mleko do centrali *Rzeka Mleka*. Centrala każdego dnia wysyła depeszę z informacją, ile potrzeba mleka.

Depesza z centrali to ciąg oddzielonych spacją znaków. Gdy dodamy wszystkie cyfry z depeszy, otrzymamy ilość litrów mleka, które mleczarnia musi wysłać.

Niestety depesze są nagminnie atakowane i zmieniane przez wrogich hakerów. Wplatają oni w ciąg dodatkowe znaki – litery, przecinki, średniki, wykrzykniki itp. Na szczęście hakerzy nie dodają żadnych dodatkowych cyfr.

Twoim zadaniem jest napisanie programu, który odrzuci z depeszy wszystkie znaki niebędące cyframi i obliczy sumę cyfr znajdujących się w wiadomości.

Do wczytania danych wykorzystaj polecenia:
`import sys`
`dane = sys.stdin.read().split()`

#### Wejście

W pierwszej linii znajduje się jedna liczba całkowita $n$ ($1 \le n \le 10^6$), oznaczająca liczbę znaków w depeszy.

W drugiej linii znajduje się $n$ znaków oddzielonych spacjami.

#### Wyjście

W jedynym wierszu wyjścia wypisz jedną liczbę całkowitą – sumę wszystkich cyfr znajdujących się w depeszy.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 9<br>x 4 ! 3 4 * 8 2 2 | 23 |

*Wyjaśnienie:*
Depesza zawiera cyfry: $4, 3, 4, 8, 2, 2$. Suma tych cyfr wynosi $4 + 3 + 4 + 8 + 2 + 2 = 23$.

??? Wskazówka
    Napisz funkcję pomocniczą `czy_cyfra`, która sprawdzi kod ASCII kolejnych znaków.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/anm/site/?key=statement){ .md-button .md-button--primary }

### Patrol

Przez pustkowia, pędząc na motocyklach o napędzie nuklearnym z prędkością tysiąca mil na godzinę, porusza się patrol. Dokładniej to się poruszał, bo teraz jego członkowie stoją w miejscu i uzupełniają paliwo w reaktorach. To dobry moment na pochwalenie się przebiegiem pojazdów – udało Ci się nawet zobaczyć jedną z tych wartości. Całkiem ładna liczba $n$, chociaż ładniejsza by była, gdyby składała się z jednakowych cyfr.

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

??? Wskazówka
    Ponieważ $n$ może mieć aż $10\,000$ cyfr, potraktuj je jako napis (ciąg znaków), a nie klasyczną liczbę.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/ew5Aw-TuOaBMVIC3EkFJKP9G/site/?key=statement){ .md-button .md-button--primary }