# Lekcja 15 – Algorytm Euklidesa – zastosowanie

**Czas realizacji:** 45 minut (1 godzina lekcyjna). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Pętla `while`.
- Pojęcie największego wspólnego dzielnika (NWD).

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |

## Wstęp teoretyczny (15 minut)

Algorytm Euklidesa to jeden z najstarszych znanych algorytmów (opisany już około 300 r. p.n.e.!). Służy do znajdowania **największego wspólnego dzielnika (NWD)** dwóch liczb całkowitych.

Zamiast wypisywać wszystkie dzielniki obu liczb i szukać największego, Euklides zauważył pewną własność:

### Dlaczego odejmowanie działa? (Dowód intuicyjny)

Załóżmy, że mamy dwie liczby: $a$ oraz $b$ ($a > b$). Jeśli jakaś liczba $d$ jest wspólnym dzielnikiem $a$ i $b$, to musi ona również dzielić ich różnicę, czyli $(a - b)$.

**Dlaczego?**
1. Skoro $d$ dzieli $a$, to możemy zapisać: $a = n \cdot d$.
2. Skoro $d$ dzieli $b$, to możemy zapisać: $b = m \cdot d$.
3. Wtedy ich różnica: $a - b = (n \cdot d) - (m \cdot d) = d \cdot (n - m)$.

Odwrotnie, każdy wspólny dzielnik $a-b$ i $b$ dzieli też $a = (a-b)+b$. Zatem obie pary mają te same wspólne dzielniki.

Jak widzisz, różnica $(a - b)$ również jest wielokrotnością liczby $d$. Oznacza to, że szukając NWD, możemy zastąpić większą liczbę różnicą tych liczb, a wynik się nie zmieni. Powtarzając to, aż liczby będą równe, otrzymamy właśnie ich największy wspólny dzielnik.

### Przykład „na kartce”: NWD(28, 12)
1. Mamy parę (28, 12). $28 > 12$, więc odejmujemy: $28 - 12 = 16$.
2. Mamy parę (16, 12). $16 > 12$, więc odejmujemy: $16 - 12 = 4$.
3. Mamy parę (4, 12). $12 > 4$, więc odejmujemy: $12 - 4 = 8$.
4. Mamy parę (4, 8). $8 > 4$, więc odejmujemy: $8 - 4 = 4$.
5. Mamy parę (4, 4). Liczby są równe! **NWD to 4**.

### Wizualizacja geometryczna
Wyobraź sobie prostokąt o bokach $a$ i $b$. Szukanie NWD to tak naprawdę próba znalezienia największego kwadratu, którym można idealnie „wykafelkować” ten prostokąt bez pozostawiania wolnych miejsc.

## Wspólne eksperymenty (10 minut)

Wersja z odejmowaniem wymaga dodatnich liczb całkowitych `a` i `b`. Przeanalizujmy kod:

```python
a = int(input("a: "))
b = int(input("b: "))
while a != b:
    if a > b:
        a = a - b
    else:
        b = b - a
print("NWD to:", a)
```

## Zadania do rozwiązania (20 minut)

1. **NWW**: Wykorzystaj wzór `NWW(a, b) = a * b // NWD(a, b)`, aby napisać kalkulator najmniejszej wspólnej wielokrotności.
2. **Skracanie ułamków**: Napisz program, który wczyta licznik i mianownik, a następnie wypisze je po podzieleniu obu przez ich NWD.
3. **Wersja z modulo**: Spróbuj zaimplementować szybszą wersję algorytmu Euklidesa, używając operatora `%`.

!!! tip "Ciekawostka"
    W module `math` istnieje gotowa funkcja `gcd(a, b)`, która robi to samo!

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### NWW (najmniejsza wspólna wielokrotność)

Napisz program, który wczyta dwie liczby całkowite i obliczy ich najmniejszą wspólną wielokrotność (NWW).

Do wczytania danych wykorzystaj polecenie:
`import sys`
`a, b = map(int, sys.stdin.read().split())`

#### Wejście

Wejście składa się z dwóch liczb całkowitych $a$ oraz $b$ ($2 \le a, b \le 32\ 000$), podanych w osobnych wierszach lub oddzielonych odstępem.

#### Wyjście

W jedynym wierszu wyjścia wypisz jedną liczbę całkowitą – najmniejszą wspólną wielokrotność liczb $a$ i $b$.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 12<br>15 | 60 |
| 7<br>14 | 14 |

??? tip "Wskazówka"
    Najmniejszą wspólną wielokrotność można obliczyć, wykorzystując największy wspólny dzielnik (NWD) ze wzoru:
    $$\text{NWW}(a, b) = \frac{a \cdot b}{\text{NWD}(a, b)}$$

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/r2en9YCg-KJu9-nMJCMxQfZQ/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/r2en9YCg-KJu9-nMJCMxQfZQ/site/?key=statement).
