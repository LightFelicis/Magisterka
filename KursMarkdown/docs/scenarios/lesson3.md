# Lekcja 3 – Instrukcje warunkowe – if, elif, else. Jak kierować zachowaniem komputera?

**Czas realizacji:** 45 minut (1 godzina lekcyjna). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

Podstawy języka Python: wczytywanie danych (`input()`), wypisywanie (`print()`), zmienne oraz podstawowe operatory arytmetyczne

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, **wyrażenia arytmetyczne i logiczne, instrukcje warunkowe**, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |

## Wstęp teoretyczny (przewidziany na około 15 minut)

Do tej pory nasze programy działały jak proste przepisy kulinarne – komputer wykonywał instrukcje jedna po drugiej, od góry do dołu. Jednak w prawdziwym świecie często musimy podejmować decyzje na podstawie pewnych warunków. Instrukcje warunkowe pozwalają programowi „skręcać” i wybierać różne ścieżki działania w zależności od tego, czy dany warunek jest prawdziwy, czy fałszywy.

### Zadanie wprowadzające (5 minut) – Informatyka „unplugged”

Zagrajmy w prostą grę: „Poprawna reakcja”. Uczniowie reagują na polecenia nauczyciela:

1. **IF** (jeśli) mam podniesioną prawą rękę -> wszyscy szumią.
2. **ELIF** (w przeciwnym razie, jeśli) mam podniesioną lewą rękę -> wszyscy tupią.
3. **ELSE** (w każdym innym przypadku) -> wszyscy siedzą cicho z rękami na blacie.

Sprawdzamy różne sytuacje: nauczyciel podnosi prawą rękę, lewą rękę albo nie podnosi żadnej. Co się stanie, jeśli podniesie obie ręce naraz?

**Wniosek:** Komputer sprawdza warunki po kolei. Gdy tylko znajdzie taki, który jest prawdziwy, wykonuje przypisane mu zadanie i pomija resztę.

### Składnia instrukcji warunkowych w Pythonie (10 minut)

Aby komputer mógł podjąć decyzję, używamy następującej konstrukcji:

```python
if warunek:
    # kod, gdy warunek jest prawdziwy
elif inny_warunek:
    # kod, gdy pierwszy był fałszywy, a ten jest prawdziwy
else:
    # kod, gdy żadne z powyższych nie zadziałało
```

Ważne: Zwróć uwagę na dwukropki na końcach wierszy oraz wcięcia (ang. indentation). Wcięcia informują Pythona, które wiersze kodu należą do danej instrukcji warunkowej.

Piszemy przykładowy program sprawdzający, czy liczba jest liczbą dodatnią:

```python
x = int(input())
if x == 0:
    print("Zero!")
elif x >= 0:
    print("Dodatnia")
else:
    print("Ujemna")
```

## Wspólne eksperymenty z językiem Python (15 minut)

### Logika matematyczna

Uruchom poniższy kod i przeanalizuj jego działanie:

```python
x = int(input())
if x > 20:
    print("A")
elif x > 10:
    print("B")
else:
    print("C")
```

Co wypisze program dla liczby `15`?

Zmodyfikuj warunki, wykorzystując następujące wyrażenia:

`4 > 1`,  `x == 5`, `2 + 2 == 5`, `x != 20`

Jak działa teraz program?

### Operatory logiczne `and` i `or`

W bardziej skomplikowanych problemach jeden prosty warunek to za mało. Wtedy stosujemy wyrażenia logiczne, które pozwalają łączyć wiele sprawdzeń w jedną całość.

- `and` (i): Cały warunek jest prawdziwy tylko wtedy, gdy wszystkie jego części są prawdziwe.
- `or` (lub): Cały warunek jest prawdziwy, jeśli przynajmniej jedna z jego części jest prawdziwa. Stosujemy go, gdy wystarczy nam spełnienie dowolnego z podanych wymagań. `Przykład: if wiek >= 18 or ma_zgode_rodzicow:`

Działanie operatorów logicznych można wyjaśnić na przykładzie zamawiania pizzy:

- `and` jest jak zamówienie: „Chcę pizzę, która ma ser i pieczarki” – jeśli zabraknie choć jednego składnika, nie będziesz zadowolony.
- `or` jest jak zamówienie: „Zjem pizzę, jeśli będzie na niej ser lub szynka” – będziesz zadowolony, gdy dostaniesz ser, gdy dostaniesz szynkę, albo oba te składniki naraz.

## Zadania do rozwiązania na komputerze (przewidziane na około 15 minut)

### Kategorie wiekowe

Napisz program, który wczyta nieujemną liczbę całkowitą oznaczającą wiek i przypisze ją do jednej z trzech kategorii:

1. Wiek co najmniej 18 lat: „Kategoria: 18 lat i więcej”.
2. Wiek co najmniej 16, ale mniej niż 18 lat: „Kategoria: 16–17 lat”.
3. Wiek poniżej 16 lat: „Kategoria: poniżej 16 lat”.

```python
wiek = int(input("Ile masz lat? "))
if wiek >= 18:
    print("Kategoria: 18 lat i więcej")
elif wiek >= 16:
    print("Kategoria: 16–17 lat")
else:
    print("Kategoria: poniżej 16 lat")
```

### Interaktywny system zamówień „Pizza-Bot”

Napisz program, który zdecyduje, czy zamówienie klienta może zostać zrealizowane na podstawie dostępności składników i jego preferencji.

**Specyfikacja problemu:**

- Dane wejściowe: Odpowiedzi „tak” lub „nie” (wczytane jako tekst) na pytania o posiadanie sera, sosu pomidorowego, szynki oraz pieczarek.
- Wynik: Komunikat „Zamówienie przyjęte!” lub „Niestety, nie możemy zrobić twojej pizzy”.

**Zasady logiczne do zaimplementowania:**

1. Warunek konieczny (`and`): Aby pizza w ogóle powstała, musisz mieć ser ORAZ sos. Jeśli brakuje choć jednego z nich, zamówienie jest odrzucane.
2. Warunek preferencji (`or`): Klient zje pizzę tylko wtedy, gdy będzie na niej szynka LUB pieczarki. Jeśli nie ma żadnego z tych dodatków, zamówienie jest odrzucane (nawet jeśli jest ser i sos).

Uzupełnij kod odpowiednim warunkiem tak, aby program spełniał specyfikację:

```python
# Wczytywanie danych od użytkownika
ser = input("Czy jest ser? (tak/nie): ")
sos = input("Czy jest sos pomidorowy? (tak/nie): ")
szynka = input("Czy jest szynka? (tak/nie): ")
pieczarki = input("Czy są pieczarki? (tak/nie): ")

if DODAJ_WARUNKI:
    print("Zamówienie przyjęte!")
else:
    print("Niestety, nie możemy zrobić Twojej pizzy")
```

### Warunek trójkąta
Napisz program, który wczyta trzy liczby całkowite (długości boków). Sprawdź, czy z tych odcinków można zbudować trójkąt. W Pythonie możesz użyć słowa `and` do łączenia warunków.

??? tip "Wskazówka"
    Zgodnie z nierównością trójkąta suma długości dowolnych dwóch boków musi być większa od długości trzeciego boku (`a + b > c`, `a + c > b` oraz `b + c > a`).

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### Trzy liczby rosnąco

Napisz program, który czyta trzy liczby całkowite, a następnie wypisuje je w kolejności niemalejącej.

Do wczytania danych wykorzystaj polecenie `a, b, c = map(int, input().split())`.

#### Wejście

Dane wejściowe zawierają trzy liczby całkowite $a, b, c$ ($1 \le a, b, c \le 1\ 000\ 000$) oddzielone pojedynczym odstępem.

#### Wyjście

Na wyjściu wypisz podane trzy liczby uporządkowane w kolejności niemalejącej, oddzielone odstępem.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 7 5 3 | 3 5 7 |

??? tip "Wskazówka"
    Możesz użyć funkcji `sorted()` do posortowania wczytanych liczb, np.:
    `liczby = sorted([a, b, c])`
    a następnie wypisać je za pomocą `print(*liczby)`.

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/HSmxAaEATSIyNA_Dw8iA84yZ/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/HSmxAaEATSIyNA_Dw8iA84yZ/site/?key=statement).

### Ćwiartka

Napisz program, który dla danego punktu na płaszczyźnie sprawdzi, w której ćwiartce układu współrzędnych się on znajduje. Może jednak być tak, że punkt nie znajduje się w żadnej ćwiartce – leży na jednej z osi lub w początku układu współrzędnych. Wówczas program powinien to stwierdzić.

Do wczytania danych możesz wykorzystać polecenie `x, y = map(int, input().split())`.

#### Wejście

Na wejściu znajdują się dwie liczby całkowite $x$ oraz $y$ ($-1\,000\,000\,000 \leq x, y \leq 1\,000\,000\,000$) oddzielone spacją, oznaczające współrzędne danego punktu.

#### Wyjście

Jeżeli podany punkt nie leży na żadnej z osi, twój program powinien wypisać: `I`, `II`, `III` lub `IV`, w przypadku gdy punkt należy do, odpowiednio, pierwszej, drugiej, trzeciej lub czwartej ćwiartki układu współrzędnych.

Jeżeli punkt leży w początku układu współrzędnych, program powinien wypisać liczbę `0`. W przeciwnym razie program powinien wypisać `OX` (duże O i duże X), jeśli punkt leży na osi X, a `OY` – jeśli punkt leży na osi Y.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 5 7 | I |
| 0 -1000000000 | OY |
| 0 0 | 0 |

??? tip "Wskazówka"
    Użyj instrukcji warunkowej `if ... elif ... else`. Najpierw sprawdź przypadek $(0, 0)$, następnie sprawdź, czy punkt leży na jednej z osi (`x == 0` lub `y == 0`), a na końcu sprawdź znaki współrzędnych $x$ i $y$, aby określić ćwiartkę (np. $x > 0$ i $y > 0$ to I ćwiartka).


[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/QbhwEI326MIf0rE4BlshlObK/site/?key=statement
){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/QbhwEI326MIf0rE4BlshlObK/site/?key=statement).
