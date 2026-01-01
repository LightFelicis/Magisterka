# Temat Podstawy Pythona – pierwsze kroki. Po co programować?

## Wymagana wiedza

Brak, jest to lekcja wprowadzająca.

## Treści z podstawy programowej

| Dział      | Sekcja                          |
| ----------- | ------------------------------------ |
| I. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń:       |  |
| | 1) Projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia wyjścia, wyrażenia arytmetyczne, oraz zmienne. |
| III. Posługiwanie się komputerem, urządzeniami cyfrowymi i sieciami komputerowymi. Uczeń: | |
| | 3) Poprawnie posługuje się terminologią związaną z informatyką i technologią. |

## Wstęp teoretyczny (przewidziany na około 15 minut)

Współczesna informatyka to nie tylko umiejętność korzystania z gotowych aplikacji, ale przede wszystkim rozwiązywanie problemów za pomocą metod informatycznych. Programowanie pozwala nam przejść z roli "cyfrowego konsumenta" do roli "cyfrowego twórcy".

### Zadanie wprowadzające (7 minut)

Wyobraź sobie, że masz robota, który rozumie tylko bardzo proste polecenia: "narysuj odcinek o długości `X` cm", "obróć się o `X` stopni w lewo/prawo" oraz "powtórz `X` razy".

Na przykład, dla komend:

```
Powtórz 2 razy: narysuj odcinek o długości 5 cm, obróć się o 90 stopni w lewo, narysuj odcinek o długości 3 cm, obróć się o 90 stopni w prawo
```

Robot narysuje schodki:

![robot.gif](./lesson0-materials/robot.gif)


Napisz na kartce instrukcję, jak narysować kwadrat, używając tylko trzech komend, które zna robot.

**Wniosek**: Komputery są bardzo szybkie, ale wykonują instrukcje dosłownie. Programowanie to proces precyzyjnego wydawania takich instrukcji.

### Podstawowe pojęcia języka Python (8 minut)

W języku Python będziemy korzystać z trzech fundamentów:

* Instrukcja wyjścia (print()): Pozwala komputerowi "mówić" do nas, czyli wyświetlać tekst na ekranie.
* Instrukcja wejścia (input()): Pozwala komputerowi "słuchać", czyli pobierać dane od użytkownika.
* Zmienne: To "pudełka" w pamięci komputera, w których przechowujemy dane, np. liczby lub imiona, aby użyć ich później.

Polecenia wydawane komputerowi napisane w języku Python nazywamy kodem. Przeanalizujmy na poniższy kod:

```Python
print("Dzień dobry, jestem robotem!")
print("Jak masz na imię?")
imie = input()
print("Cześć", imie, "miło mi cię poznać!")
```

Po uruchomieniu, możemy przeprowadzić rozmowę z robotem. Uruchamiając ponownie, robot zaczyna
konwersację od początku!

## Wspólne eksperymenty z językiem Python (10 minut)

Poniższe programy należy uruchomić w środowisku Pythona, na przykład Spyder.

```Python
print(2+2)
```

```Python
print("2+2")
```

Jaka jest różnica między tymi kodami? Jak zachowuje się Python?

```Python
print("Kasia" + 2)
```

Błąd wykonania! Nie można dodawać słów i liczb :)

```Python
print("Witaj", "Świecie")
```

```Python
print("Witaj")
print("Świecie")
```

Możemy wypisywać kilka wyrażeń obok siebie, korzystając z przecinka. Dwa wywołania `print()` -> dwie linijki tekstu.

```Python
imie = input()
wiek = int(input())
print(imie, "ma lat", wiek)
```

Python potrzebuje innej komendy żeby wczytać słowa (imię to słowo), a innej komendy żeby wczytać liczbę (wiek to liczba).

## Zadanie do rozwiązania na komputerze (25 minut)

### Symbole działań matematycznych

Uruchom poniższy program. Co oznaczają symbole `+`, `-`, `/`, `*`?

```Python
print(12+2)
print(12-2)
print(12/2)
print(12*2)
```

### Prosty kalkulator (sumator)

Uruchom poniższy program, który wczyta dwie liczby całkowite i wypisze ich sumę. 

Python wczytuje dane jako tekst. Aby traktował je jak liczby, należy użyć funkcji int(), np.: `liczba = int(input())`.

```Python
a = int(input("Podaj pierwszą liczbę: "))
b = int(input("Podaj drugą liczbę: "))
print("Suma wynosi:", a + b)
```

Zmodyfikuj program, żeby wczytywał trzy liczby i wypisywał ich sumę.

### Twoje dane

Napisz program, który poprosi o podanie: Twojego imienia, wieku oraz ulubionej liczby. 
Następnie niech wypisze zdanie: 

`[Imię] ma [wiek] lat, a ulubiona liczba pomnożona przez 2 to [wynik]`.

## Praca domowa do rozwiązania na platformie Szkopuł

### Bond

Poniżej widzisz kod programu, który na ekranie wypisuje komunikat: "HELLO WORLD!".
Zmodyfikuj treść programu tak, aby wypisywał w pierwszej linii komunikat "My name is
Bond.", zaś w drugiej "James Bond.".

```Python
print("HELLO WORLD!")
```

#### Wejście 

Twój program nie powinien oczekiwać żadnych danych.

#### Wyjście

W pierwszej linii wypisz komunikat: "My name is Bond.", zaś w drugiej "James Bond.".

??? Wskazówka
    W podanym jako przykład kodzie zmień odpowiednio wypisywane słowo. W Pythonie polecenie `print()` samo
    dodaje znak nowej linii na końcu, więc wystarczy, że wywołasz `print` dwa razy, a wypisane zostaną dwie linie.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/qbVEWhU7DxBcjg5p-DgL5072/site/?key=submit){ .md-button .md-button--primary }

### Obrus

Mama Tosi kupiła kwadratowy stół o boku `b` centymetrów. Ile centymetrów kwadratowych obrusa potrzebuje, żeby przykryć stół?

Do wczytywania danych skorzystaj z polecenia `b = int(input())`.

#### Wejście 

Na wejściu znajduje się jedna liczba rzeczywista b ($1 \leq b \leq 1000$), będąca długością boku stołu.

#### Wyjście

W pierwszym wierszu należy wypisać pole stołu w centymetrach kwadratowych.

#### Przykład

| Wejście      | Wyjście                          |
| :---------- | :----------------------------------- |
| 12        | 144         |

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/5ETn93jOWgwMQuCgsqIUImOl/site/?key=submit){ .md-button .md-button--primary }

### Klasy (dla chętnych)

W liceum w Bajtomiu przyjęto nowych uczniów do trzech klas pierwszych. Zapamiętaj liczby
uczniów w każdej klasie, a później je wypisz.

Do wczytania danych wykorzystaj polecenie `a, b, c = map(int, input().split())`.
Jeśli masz problemy z wypisywaniem danych, zerknij na wskazówkę!

#### Wejście 

W pierwszej linii wejścia znajdują się trzy liczby całkowite $a$, $b$ oraz $c$ ($1 \leq a, b, c \leq 50$),
odpowiednio liczba uczniów w klasie $a$, $b$ i $c$.

#### Wyjście

W pierwszym wierszu wyjścia wypisz liczby uczniów w klasach $a$, $b$ i $c$. W kolejnych trzech
liniach wypisz nazwy klas (mała litera) oraz (po odstępie) liczbę uczniów w każdej z klas.


#### Przykład

| Wejście      | Wyjście                          |
| :---------- | :----------------------------------- |
| 12 34 23    | 12 34 23 <br> a 12 <br> b 34 <br> c 23  |

??? Wskazówka
    Do wypisania wartości obok siebie możesz wykorzystać `print()`, podając wartości oddzielone przecinkami, na przykład `print(1, 2, 3, 4)` wypisze `1 2 3 4` obok siebie.

[Sprawdź kod na Szkopule :fontawesome-solid-paper-plane:](https://szkopul.edu.pl/problemset/problem/1Byaj2NLd4w4vLzHQplOs27s/site/?key=submit){ .md-button .md-button--primary }



