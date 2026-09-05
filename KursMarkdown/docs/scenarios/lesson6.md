# Matematyka z pomocą Pythona – Jak napisać program rozwiązujący moją pracę domową?

## Wymagana wiedza

- Podstawy języka Python: instrukcje wejścia/wyjścia (input(), print()).
- Stosowanie zmiennych do przechowywania danych.
- Instrukcje warunkowe (if, else) do podejmowania decyzji przez program.
- Stosowanie własnych funkcji (def, return).

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, **wyrażenia arytmetyczne i logiczne**, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |

## Wstęp teoretyczny (przewidziany na około 15 minut)

Python to nie tylko język dla programistów, ale potężne narzędzie matematyczne, które może zastąpić zaawansowany kalkulator naukowy. Pozwala on na automatyzację obliczeń z Twojej pracy domowej – od geometrii po teorię liczb.

Aby skutecznie rozwiązywać zadania matematyczne, musimy najpierw stworzyć specyfikację, czyli określić, co jest daną w zadaniu (wejście), a co mamy obliczyć (wynik).

Większość operacji wykonujemy za pomocą standardowych operatorów i funkcji wbudowanych. Część z nich już znamy, na przykład operatory działań  `+, -, *, /`. W Pythonie mamy również operator potęgowania: `2**4` oznacza matematyczne $2^4$.

Przydatnymi operatorami są operatory dzielenia bez reszty `//` oraz operator modulo (reszta z dzielenia) `%`.

Popatrzmy na następujący przykład programu w Pythonie:

```Python
x = 12
print("Wynik dzielenia całkowitego 12/5 to: ", 12//5, " a reszta z dzielenia to: ", 12 % 5)
```

**Wyzwanie**: Jak napisać program, który sprawdzi, czy wczytana liczba jest parzysta?

Prócz operatorów, w Pythonie mamy kilka przydatnych **funkcji** wbudowanych, na przykład:

- `abs(liczba)` - zwraca wartość bezwzględną z liczby
- `min(x, y, z)` oraz `max(x, y, z)` - zwraca minimalną/maksymalną wartość spośród podanych liczb
- `round(liczba, ile_po_przecinku)` - zaokrągla liczbę

Przeanalizujmy następujący program w Pythonie:

```Python
liczba = int(input())
print("Wartość bezwzględna: ", abs(liczba))
print("Minimum z liczby i 0: ", min(liczba, 0))
print("Jedna trzecia część liczby, zaokrąglona: ", round(liczba/3, 2))
```

Co zostanie wypisane na ekranie, po podaniu `-1` jako wejście?

### Rozszerzenie możliwości - moduł math

Aby uzyskać dostęp do bardziej zaawansowanych funkcji, musimy „zaimportować” dodatkowy zestaw narzędzi `math`.
Zawiera on przydatne funkcje, na przykład:

- `sqrt(liczba)` – pierwiastek kwadratowy z liczby.
- `pi` – bardzo dokładna wartość liczby π.
- `ceil(liczba)` – zaokrąglenie w górę (sufit), z `2.5` zrobi `3`.
- `floor(liczba)` – zaokrąglenie w dół (podłoga), z `2.5` zrobi `2`.
- `gcd(a, b)` – największy wspólny dzielnik (NWD).

Aby korzystać z `math`, na początku programu należy umieścić linijkę z `import`:

```Python
from math import *

print(sqrt(25))
```

## Wspólne eksperymenty z językiem Python (10 minut)

Sprawdźmy, jak Python radzi sobie z typowymi problemami z podręcznika:

1. Liczba przeciwna i odwrotna - wczytaj liczbę i wypisz jej wartość przeciwną oraz odwrotną
2. Precyzja zaokrągleń - wczytaj liczbę i zaokrąglij ją do 2 miejsc po przecinku
3. Pierwiastkowanie/potęgowanie - wczytaj liczbę i wypisz jej pierwiastek oraz kwadrat

## Zadania do rozwiązania na komputerze (przewidziane na około 20 minut)

Zaprojektuj programy, które pomogą Ci w nauce innych przedmiotów (wybierz 2 z poniższej listy):

- Twierdzenie Pitagorasa: Napisz funkcję, która przyjmuje długości dwóch przyprostokątnych a i b, a zwraca długość przeciwprostokątnej c. Wykorzystaj math.sqrt() oraz wzór $a^2 + b^2 = c^2$.
- Pole koła i obwód: Wczytaj promień `r`. Oblicz pole ($\pi r^2$) i obwód ($2\pi r$). Użyj stałej `pi`. Zaokrąglij wynik do 2 miejsc po przecinku.
- Kalkulator NWD: Wykorzystaj `gcd(a, b)`, aby sprawdzić, przez jaką największą liczbę można skrócić ułamek $\frac{a}{b}$.
- Zakupy i reszta: Napisz program, który wczyta cenę towaru i kwotę, jaką zapłacił klient. Oblicz resztę, ale wypisz ją jako wartość bezwzględną (użyj `abs()`), na wypadek gdyby klient dał za mało pieniędzy.
- Średnia ocen: Wczytaj 5 ocen z informatyki i oblicz ich średnią arytmetyczną. Jeśli średnia wynosi np. `4.75`, użyj `ceil()`, aby sprawdzić, czy uczeń ma szansę na ocenę bardzo dobrą.

## Zadania do rozwiązania na platformie Szkopuł

### Łamanie czekolady

![czekolada](./lesson6-materials/czekolada.png)

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

??? Wskazówka
    Jedno przełamanie prostokątnej czekolady wzdłuż linii podziału oddziela pasek o wymiarach $x \times m$ (jeśli łamiemy wzdłuż wierszy) lub $n \times y$ (jeśli łamiemy wzdłuż kolumn).
    
    Oznacza to, że odłamana część składa się z liczby kawałków będącej wielokrotnością $m$ (i nie większej niż cała czekolada $n \times m$) LUB wielokrotnością $n$ (i nie większej niż $n \times m$).
    
    Warunek można zapisać tak:
    `k <= n * m and (k % n == 0 or k % m == 0)`

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/eSgi8Ae29vCPojodBrdDAooI/site/?key=statement){ .md-button .md-button--primary }