# Lekcja 7 – Matematyka z pomocą Pythona. Jak napisać program rozwiązujący zadania z pracy domowej?

**Czas realizacji:** 45 minut (1 godzina lekcyjna). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Podstawy języka Python: instrukcje wejścia/wyjścia (`input()`, `print()`).
- Stosowanie zmiennych do przechowywania danych.
- Instrukcje warunkowe (`if`, `else`) do podejmowania decyzji przez program.
- Stosowanie własnych funkcji (`def`, `return`).

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, **wyrażenia arytmetyczne i logiczne**, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |

## Wstęp teoretyczny (przewidziany na około 15 minut)

Python to nie tylko język dla programistów, ale potężne narzędzie matematyczne, które może zastąpić zaawansowany kalkulator naukowy. Pozwala on na automatyzację obliczeń z twojej pracy domowej – od geometrii po teorię liczb.

Aby skutecznie rozwiązywać zadania matematyczne, musimy najpierw stworzyć specyfikację, czyli określić, jakie dane otrzymujemy w zadaniu (wejście), a co mamy obliczyć (wynik).

Większość operacji wykonujemy za pomocą standardowych operatorów i funkcji wbudowanych. Część z nich już znamy, na przykład operatory działań  `+, -, *, /`. W Pythonie mamy również operator potęgowania: `2**4` oznacza matematyczne $2^4$.

Przydatne są także operator dzielenia całkowitego `//` oraz operator reszty z dzielenia `%`.

Popatrzmy na następujący przykład programu w Pythonie:

```python
x = 12
print("Wynik dzielenia całkowitego 12/5 to: ", 12//5, " a reszta z dzielenia to: ", 12 % 5)
```

**Wyzwanie**: Jak napisać program, który sprawdzi, czy wczytana liczba jest parzysta?

Oprócz operatorów w Pythonie mamy kilka przydatnych **funkcji** wbudowanych, na przykład:

- `abs(liczba)` – zwraca wartość bezwzględną liczby;
- `min(x, y, z)` oraz `max(x, y, z)` – zwracają odpowiednio najmniejszą i największą spośród podanych liczb;
- `round(liczba, ile_po_przecinku)` – zaokrągla liczbę.

Przeanalizujmy następujący program w Pythonie:

```python
liczba = int(input())
print("Wartość bezwzględna: ", abs(liczba))
print("Minimum z liczby i 0: ", min(liczba, 0))
print("Jedna trzecia część liczby, zaokrąglona: ", round(liczba/3, 2))
```

Co zostanie wypisane na ekranie po podaniu liczby `−1` jako danych wejściowych?

### Rozszerzenie możliwości – moduł math

Aby uzyskać dostęp do bardziej zaawansowanych funkcji, musimy „zaimportować” dodatkowy zestaw narzędzi `math`.
Zawiera on przydatne funkcje, na przykład:

- `sqrt(liczba)` – pierwiastek kwadratowy z liczby.
- `ceil(liczba)` – zaokrąglenie w górę (sufit), z `2.5` zrobi `3`.
- `floor(liczba)` – zaokrąglenie w dół (podłoga), z `2.5` zrobi `2`.
- `gcd(a, b)` – największy wspólny dzielnik (NWD).

Moduł zawiera także stałą `pi`, przybliżającą liczbę π. Nie jest ona funkcją.

Aby korzystać z `math`, na początku programu należy umieścić wiersz z instrukcją `import`:

```python
from math import *

print(sqrt(25))
```

## Wspólne eksperymenty z językiem Python (10 minut)

Sprawdźmy, jak Python radzi sobie z typowymi problemami z podręcznika:

1. Liczba przeciwna i odwrotna - wczytaj liczbę różną od zera i wypisz liczbę przeciwną oraz odwrotną.
2. Precyzja zaokrągleń - wczytaj liczbę i zaokrąglij ją do 2 miejsc po przecinku.
3. Pierwiastkowanie/potęgowanie - wczytaj nieujemną liczbę i wypisz jej pierwiastek rzeczywisty oraz kwadrat.

## Zadania do rozwiązania na komputerze (przewidziane na około 20 minut)

Zaprojektuj programy, które pomogą ci w nauce innych przedmiotów (wybierz 2 z poniższej listy):

- Twierdzenie Pitagorasa: Napisz funkcję, która przyjmuje długości dwóch przyprostokątnych a i b, a zwraca długość przeciwprostokątnej c. Wykorzystaj `math.sqrt()` oraz wzór $a^2 + b^2 = c^2$.
- Pole i obwód koła: Wczytaj promień `r`. Oblicz pole ($\pi r^2$) i obwód ($2\pi r$). Użyj stałej `pi`. Zaokrąglij wynik do 2 miejsc po przecinku.
- Kalkulator NWD: Wykorzystaj `gcd(a, b)`, aby sprawdzić, przez jaką największą liczbę można skrócić ułamek $\frac{a}{b}$.
- Zakupy i reszta: Napisz program, który wczyta cenę towaru i kwotę, jaką zapłacił klient. Jeśli wpłacona kwota jest wystarczająca, wypisz resztę. W przeciwnym razie wypisz kwotę niedopłaty z osobnym komunikatem.
- Zaokrąglanie średniej: Wczytaj 5 liczb i oblicz ich średnią arytmetyczną. Użyj `ceil()`, aby zaokrąglić średnią w górę do liczby całkowitej.

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### Łamanie czekolady

![czekolada](./lesson7-materials/czekolada.png)

Pan Integer kupił swoją ulubioną czekoladę z nadzieniem toffi. Czekolada ma kształt prostokąta o rozmiarze $n \times m$ kawałków.

Pan Integer chciałby teraz odłamać **jednym prostym ruchem** (wzdłuż linii podziału) dokładnie $k$ kawałków. Czy jest to możliwe?

Do wczytania danych wykorzystaj polecenia:
`n, m = map(int, input().split())`
`k = int(input())`

#### Wejście

Pierwszy wiersz wejścia zawiera dwie liczby całkowite $n$ oraz $m$ ($1 \le n, m \le 10^6$), oznaczające rozmiar czekolady.

W drugim wierszu znajduje się jedna liczba całkowita $k$ ($1 \le k \le 10^6$), oznaczająca liczbę kawałków, które chce odłamać Pan Integer.

#### Wyjście

Na wyjściu wypisz słowo `TAK`, jeśli Pan Integer może jednym przełamaniem oderwać dokładnie $k$ kawałków czekolady, lub `NIE` w przeciwnym wypadku.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 3 5<br>6 | TAK |
| 4 8<br>6 | NIE |

??? tip "Wskazówka"
    Jedno przełamanie prostokątnej czekolady wzdłuż linii podziału oddziela pasek o wymiarach $x \times m$ (jeśli łamiemy wzdłuż wierszy) lub $n \times y$ (jeśli łamiemy wzdłuż kolumn).

    Oznacza to, że odłamana część składa się z liczby kawałków będącej wielokrotnością $m$ (i mniejszej niż cała czekolada $n \times m$) LUB wielokrotnością $n$ (i mniejszej niż $n \times m$).

    Warunek można zapisać tak:
    `0 < k < n * m and (k % n == 0 or k % m == 0)`

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/eSgi8Ae29vCPojodBrdDAooI/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/eSgi8Ae29vCPojodBrdDAooI/site/?key=statement).
