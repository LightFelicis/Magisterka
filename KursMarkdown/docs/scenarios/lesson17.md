# Lekcja 17 – Porządkowanie zbioru – sortowanie przez wybieranie

**Czas realizacji:** 90 minut (2 godziny lekcyjne). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Listy.

- Wyszukiwanie minimum (z poprzedniej lekcji).

- Zamiana wartości między zmiennymi.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 2) stosuje przy rozwiązywaniu problemów podstawowe algorytmy: […]<br>b) wyszukiwania i porządkowania: wyszukuje element w zbiorze nieuporządkowanym oraz porządkuje elementy w zbiorze metodą przez proste wybieranie; |

## Wstęp teoretyczny (15 minut)

Sortowanie przez wybieranie (selection sort) to intuicyjny algorytm, który dzieli naszą listę na dwie części: **już posortowaną** (na początku) oraz **jeszcze nieposortowaną**.

### Jak to działa krok po kroku?

1.  **Szukanie**: Przeszukujemy nieposortowaną część listy, aby znaleźć w niej najmniejszy element.
2.  **Zamiana**: Gdy znajdziemy najmniejszą liczbę, zamieniamy ją miejscami z pierwszym elementem części nieposortowanej.
3.  **Postęp**: Teraz nasza „posortowana część” powiększyła się o jeden element. Przesuwamy się o jedną pozycję w prawo i powtarzamy cały proces dla reszty liczb.
4.  **Koniec**: Powtarzamy te kroki tak długo, aż zostanie nam tylko jeden (ostatni) element – on siłą rzeczy musi być już największy i na właściwym miejscu.

### Przykład z życia: Sortowanie kart
Wyobraź sobie, że trzymasz w ręku wachlarz nieuporządkowanych kart (np. od dwójki do asa). Chcesz je ułożyć od najmniejszej do największej:

1.  Przeglądasz wszystkie karty w ręku i szukasz tej najniższej (np. dwójki).
2.  Wyciągasz ją i przekładasz na sam początek (lewa strona).
3.  Teraz szukasz najniższej karty wśród tych, które pozostały po prawej stronie od dwójki.
4.  Znajdujesz np. trójkę i kładziesz ją zaraz za dwójką.
5.  Powtarzasz to, aż w prawej ręce nie zostanie ci żadna karta.

**Dlaczego „przez wybieranie”?** Bo w każdym kroku algorytm „wybiera” konkretną wartość – tę najmniejszą z dostępnych – i umieszcza ją na właściwym miejscu.

## Wizualizacja (unplugged)
Uczniowie dostają karty z liczbami. Muszą ustawić się w szeregu i posortować zgodnie z algorytmem.

1. Nauczyciel wskazuje pierwszą osobę w szeregu jako „miejsce docelowe”.
2. Klasa szuka osoby z najniższym numerem w pozostałej części szeregu.
3. Wybrana osoba zamienia się miejscami z osobą na „miejscu docelowym”.

## Wspólne eksperymenty (20 minut)

Przeanalizujmy kod implementujący sortowanie przez wybieranie. Zwróć uwagę na dwie pętle – zewnętrzna wskazuje pozycję, na którą ma trafić najmniejszy element nieposortowanej części listy, a wewnętrzna przeszukuje pozostałą, nieposortowaną część listy.

```python
lista = [64, 25, 12, 22, 11]

for i in range(len(lista)):
    # Zakładamy, że pierwszy element nieposortowanej części jest najmniejszy
    min_idx = i
    for j in range(i + 1, len(lista)):
        if lista[j] < lista[min_idx]:
            min_idx = j

    # Zamiana miejscami: najmniejszy znaleziony trafia na pozycję o indeksie i
    lista[i], lista[min_idx] = lista[min_idx], lista[i]

print("Posortowana lista:", lista)
```

## Zadania do rozwiązania (55 minut)

1. **Sortowanie malejące**: Zmodyfikuj powyższy kod tak, aby liczby były układane od największej do najmniejszej (odwrócenie kierunku sortowania).
2. **Mediana**: Napisz program, który wczyta od użytkownika 5 liczb, posortuje je, a następnie wypisze element środkowy (medianę).

!!! tip "Wskazówka"
    Skorzystaj z polecenia `len()`, aby odczytać długość tablicy i obliczyć środkowy indeks.

3. **Sortowanie imion**: Stwórz listę kilku imion i spróbuj je posortować alfabetycznie. Czy Python radzi sobie z porównywaniem słów (operator `<`) tak samo łatwo jak z liczbami?
4. **Sortowanie par**: Masz listę wyników biegaczy: `wyniki = [[12.5, "Jan"], [11.2, "Ola"], [13.1, "Piotr"]]`. Posortuj ją według czasu (pierwszy element w każdej parze). Zauważ, że Python przy zamianie `lista[i], lista[min_idx]` przenosi całe „paczki” danych (liczbę wraz z imieniem).

!!! warning "Dobór algorytmu"
    Sortowanie przez wybieranie ma złożoność kwadratową i służy tu do nauki. Dla setek tysięcy elementów użyj `sorted()` lub metody `sort()`.

## Zadania do rozwiązania na platformie Szkopuł

*Poniższe opisy są adaptacjami redakcyjnymi treści zadań. Pełne treści są dostępne na platformie Szkopuł.*

### Sortowanie bąbelkowe

Jasio bardzo lubi porządek, dlatego ponumerował wszystkie samochodziki w swojej kolekcji i tak ustawił je na półce. Niestety zamiłowanie do porządku kończy mu się, gdy trzeba posprzątać w pokoju. Często więc mama, tracąc cierpliwość, sprząta sama.

Kolejność samochodzików na półce nie ma dla mamy znaczenia. Jasio, zobaczywszy samochodziki poustawiane w losowej kolejności, bardzo się zasmucił. Chciałby je uporządkować, ale samochodzików jest bardzo dużo i trudno mu to zrobić – zwłaszcza że niektóre samochodziki pożyczył kolegom.

Pomóż Jasiowi i napisz program, który posortuje samochodziki według ich numerów.

Do wczytania danych wykorzystaj polecenia:
`n = int(input())`
`samochodziki = list(map(int, input().split()))`

#### Wejście

W pierwszym wierszu wejścia znajduje się liczba całkowita $n$ ($1 \le n \le 10^4$), oznaczająca liczbę samochodzików, które aktualnie znajdują się na półce.

Drugi wiersz zawiera $n$ liczb całkowitych oddzielonych pojedynczymi spacjami – są to numery samochodzików w kolejności, w jakiej obecnie stoją na półce.

#### Wyjście

W jedynym wierszu wyjścia wypisz $n$ numerów samochodzików ułożonych w kolejności rosnącej, oddzielonych spacjami.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 10<br>19 15 17 1 5 10 14 7 16 2 | 1 2 5 7 10 14 15 16 17 19 |

??? tip "Wskazówka"
    W języku Python wczytaną listę liczb można bardzo łatwo posortować za pomocą wbudowanej metody `.sort()` lub funkcji `sorted()`.
    Aby wypisać elementy listy oddzielone spacjami w jednym wierszu, użyj rozpakowania listy: `print(*samochodziki)`.

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/zZRpgyajpZA5OAVa-Fi8BonM/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/zZRpgyajpZA5OAVa-Fi8BonM/site/?key=statement).


### 10 wspaniałych

!!! warning "Niejednoznaczność oryginału"
    Oryginał dopuszcza mniej niż 10 kandydatów, ale wymaga 10 wyników. Na potrzeby ćwiczenia przyjmij n ≥ 10. Zachowanie sprawdzarki dla mniejszych danych wymaga potwierdzenia.

![muszkieter](./lesson17-materials/muszkieter.png)

D'Artagnan ogłosił konkurs na 3 muszkieterów. Niestety zgłosiło się mnóstwo chętnych – nawet milion!

D'Artagnan stwierdził, że nie jest w stanie sprawdzić wszystkich kandydatów. Na szczęście każdy kandydat podał swoją moc, która może być również ujemna.

D'Artagnan poprosił ciebie, byś wyznaczył 10 najlepszych kandydatów i wypisał ich moce.

Do wczytania danych wykorzystaj polecenia:
`n = int(input())`
`moce = list(map(int, input().split()))`

#### Wejście

W pierwszym wierszu znajduje się jedna liczba całkowita $n$ ($1 \le n \le 1\ 000\ 000$), oznaczająca liczbę chętnych kandydatów.

W drugim wierszu znajduje się $n$ liczb całkowitych z zakresu od $-1\ 000\ 000$ do $1\ 000\ 000$, oznaczających moce kolejnych kandydatów.

#### Wyjście

Twój program powinien wypisać w jednym wierszu moce 10 kandydatów o największych wartościach, posortowane malejąco i oddzielone spacjami.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 12<br>3 6 3 2 5 9 4 -1 -2 3 8 1 | 9 8 6 5 4 3 3 3 2 1 |

??? tip "Wskazówka"
    Możesz posortować całą listę mocy malejąco, a następnie wypisać tylko pierwsze 10 elementów.
    Zamiast sortowania możesz również 10 razy wyszukać maksymalną wartość i usuwać ją ze zbioru.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/10wspanialych/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/10wspanialych/site/?key=statement).


### Bitwa pod Wiedniem

Największa turecka armia XVII wieku oblega Wiedeń. Jest już w odległości strzału z rusznicy od zamku cesarza. Gorące letnie słońce wypala resztki wiary obrońców. Losy Europy zawisły na włosku.

Wiadomość, że Polacy idą na odsiecz, rozchodzi się błyskawicznie i podnosi morale. Wiedeń broni się nadzieją. Ale czy 27 tysięcy polskich żołnierzy może zadecydować w bitwie przeciwko 300 tysiącom agresorów? Obrońcy wierzą...

Król Jan III Sobieski ma do dyspozycji chorągwie husarskie, pancerne, piechoty... Ale w jakiej kolejności mają uderzyć, by zaskoczyć wielkiego wezyra Kara Mustafę?

Król Jan nadał wszystkim chorągwiom nazwy w postaci liczb. To nie są zwykłe liczby. To szyfr, który mówi chorągwiom, w jakiej kolejności mają się ustawić:

* Im większa suma cyfr liczby, tym bardziej z przodu musi być chorągiew.

* Jeśli dwie chorągwie mają tę samą sumę cyfr, z przodu powinna być ta chorągiew, której liczba jest większa.

Do wczytania danych wykorzystaj polecenia:
`n = int(input())`
`choragwie = list(map(int, input().split()))`

#### Wejście

Pierwszy wiersz wejścia składa się z jednej liczby naturalnej $n$ ($1 \le n \le 4 \cdot 10^5$), oznaczającej liczbę chorągwi.

Drugi wiersz wejścia zawiera $n$ liczb całkowitych z przedziału od $1$ do $10^{18}$, oznaczających nazwy chorągwi.

#### Wyjście

Twój program powinien wypisać w jednym wierszu wszystkie nazwy chorągwi w kolejności bojowej, oddzielone pojedynczym odstępem.

#### Przykład

| Wejście | Wyjście |
| :--- | :--- |
| 4<br>1000 122 9 32 | 9 122 32 1000 |

*Wyjaśnienie:*
Największą sumę cyfr ma liczba $9$ (suma $9$) i tę chorągiew wypisujemy najpierw. Liczby $122$ i $32$ mają taką samą sumę cyfr ($5$) – chorągiew $122$ wypisujemy wcześniej, gdyż jest większa od $32$. Najmniejszą sumę cyfr ma liczba $1000$ (suma $1$) i tę chorągiew wypisujemy na końcu.

??? tip "Wskazówka"
    Zdefiniuj funkcję pomocniczą obliczającą sumę cyfr liczby (np. `sum(int(c) for c in str(x))`).

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/VDUW5eIFUfmutWAqey-KQG7O/site/?key=statement){ .md-button .md-button--primary }

**Źródło:** publiczne archiwum zadań serwisu Szkopuł — [odnośnik do zadania](https://szkopul.edu.pl/problemset/problem/VDUW5eIFUfmutWAqey-KQG7O/site/?key=statement).
