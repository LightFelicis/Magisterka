# Temat: Instrukcje warunkowe – if, elif, else. Jak kierować zachowaniem komputera?

## Wymagana wiedza

Podstawy języka Python: wczytywanie danych (input()), wypisywanie (print()), zmienne oraz podstawowe operatory arytmetyczne

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń:      |  |
|       | 1) Formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) i wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) W programach stosuje: instrukcje wejścia/wyjścia, **wyrażenia arytmetyczne i logiczne, instrukcje warunkowe**, instrukcje iteracyjne, funkcje oraz zmienne i tablice. |

## Wstęp teoretyczny (przewidziany na około 15 minut)

Do tej pory nasze programy działały jak proste przepisy kulinarne – komputer wykonywał instrukcje jedna po drugiej, od góry do dołu. Jednak w prawdziwym świecie często musimy podejmować decyzje na podstawie pewnych warunków. Instrukcje warunkowe pozwalają programowi "skręcać" i wybierać różne ścieżki działania w zależności od tego, czy dany warunek jest prawdziwy, czy fałszywy.

### Zadanie wprowadzające (5 minut) – Informatyka "unplugged"

Zagrajmy w prostą grę: "Poprawna reakcja". Uczniowie reagują na polecenia nauczyciela:

1. **IF** (jeśli) mam podniesioną prawą rękę -> wszyscy szumią.
2. **ELIF** (w przeciwnym razie, jeśli) mam podniesioną lewą rękę -> wszyscy tupią.
3. **ELSE** (w każdym innym przypadku) -> wszyscy siedzą cicho z rękami na blacie.

Testujemy proste kombinacje - podniesiona prawa/lewa/żadna ręka, co jeśli nauczyciel podniesie obie naraz?

**Wniosek:** Komputer sprawdza warunki po kolei. Gdy tylko znajdzie taki, który jest prawdziwy, wykonuje przypisane mu zadanie i pomija resztę.

### Składnia instrukcji warunkowych w Pythonie (10 minut)

Aby komputer mógł podjąć decyzję, używamy następującej konstrukcji:

```Python
if warunek:
    # kod, gdy warunek jest prawdziwy
elif inny_warunek:
    # kod, gdy pierwszy był fałszywy, a ten jest prawdziwy
else:
    # kod, gdy żadne z powyższych nie zadziałało
```

Ważne: Zwróć uwagę na dwukropki na końcach linii oraz wcięcia (ang. indentation). Wcięcia informują Pythona, które linijki kodu należą do danej instrukcji warunkowej.

Piszemy przykładowy program sprawdzający, czy liczba jest liczbą dodatnią:

```Python
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

```Python
x = int(input())
if x > 20:
    print("A")
elif x > 10:
    print("B")
else:
    print("C")
```

Co wypisze program dla liczby `15`?

Zmodyfikuj warunki, wykorzystaj takie wyrażenia:

`4 > 1`,  `x == 5`, `2 + 2 == 5`, `x != 20`

Jak działa teraz program?

### Instrukcje `and` i `or`

W bardziej skomplikowanych problemach jeden prosty warunek to za mało. Wtedy stosujemy wyrażenia logiczne, które pozwalają łączyć wiele sprawdzeń w jedną całość.

- `and` (i): Cały warunek jest prawdziwy tylko wtedy, gdy wszystkie jego części są prawdziwe. 
- `or` (lub): Cały warunek jest prawdziwy, jeśli przynajmniej jedna z jego części jest prawdziwa. Stosujemy go, gdy wystarczy nam spełnienie dowolnego z podanych wymagań. `Przykład: if wiek >= 18 or ma_zgode_rodzicow:`

Analogię operatorów logicznych można porównać do zamawiania pizzy:

- `and` jest jak zamówienie: "Chcę pizzę, która ma ser i pieczarki" – jeśli zabraknie choć jednego składnika, nie będziesz zadowolony.
- `or` jest jak zamówienie: "Zjem pizzę, jeśli będzie na niej ser lub szynka" – będziesz zadowolony, gdy dostaniesz ser, gdy dostaniesz szynkę, albo oba te składniki na raz.

## Zadania do rozwiązania na komputerze (przewidziane na około 15 minut)

### Prawo jazdy i pełnoletniość
Napisz program, który zapyta użytkownika o wiek.

1. Jeśli ma 18 lat lub więcej, wypisz: "Jesteś osobą pełnoletnią. Możesz prowadzić samochód".
2. Jeśli ma co najmniej 16 lat (ale mniej niż 18), wypisz: "Nie jesteś pełnoletni, ale możesz już robić prawo jazdy kategorii B1!".
3. W innym przypadku wypisz: "Jesteś jeszcze za młody na prawo jazdy".

```Python
wiek = int(input("Ile masz lat? "))
if wiek >= 18:
    print("Jesteś osobą pełnoletnią. Możesz prowadzić samochód.")
elif wiek >= 16:
    print("Nie jesteś pełnoletni, ale możesz już robić prawo jazdy kategorii B1!")
else:
    print("Jesteś jeszcze za młody na prawo jazdy.")
```

### Interaktywny system zamówień „Pizza-Bot”

Napisz program, który zdecyduje, czy zamówienie klienta może zostać zrealizowane na podstawie dostępności składników i jego preferencji.
Specyfikacja problemu:
- Dane wejściowe: Odpowiedzi „tak” lub „nie” (wczytane jako tekst) na pytania o posiadanie sera, sosu pomidorowego, szynki oraz pieczarek.
- Wynik: Komunikat „Zamówienie przyjęte!” lub „Niestety, nie możemy zrobić Twojej pizzy”.

Zasady logiczne do zaimplementowania:
1. Warunek konieczny (and): Aby pizza w ogóle powstała, musisz mieć ser ORAZ sos. Jeśli brakuje choć jednego z nich, zamówienie jest odrzucane.
2. Warunek preferencji (or): Klient zje pizzę tylko wtedy, gdy będzie na niej szynka LUB pieczarki. Jeśli nie ma żadnego z tych dodatków, zamówienie jest odrzucane (nawet jeśli jest ser i sos).

Początkowy kod uzupełnij warunkami tak, by spełniały specyfikację:

```Python
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

??? Podpowiedź: 
    Zgodnie z zasadą geometrii, suma dwóch dowolnych boków musi być większa od trzeciego boku (a+b>c oraz a+c>b oraz b+c>a).

## Zadania do rozwiązania na platformie Szkopuł

### Trzy liczby

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/HSmxAaEATSIyNA_Dw8iA84yZ/site/?key=statement){ .md-button .md-button--primary }

### Ćwiartka układu współrzędnych

[Zobacz zadanie na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/QbhwEI326MIf0rE4BlshlObK/site/?key=statement
){ .md-button .md-button--primary }







