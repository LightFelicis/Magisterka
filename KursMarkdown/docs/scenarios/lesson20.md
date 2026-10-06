# Lekcja 20 – Trenowanie własnego modelu i eksploracja danych

**Czas realizacji:** 90 minut (2 godziny lekcyjne). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Wiedza z poprzednich lekcji dotyczących biblioteki scikit-learn.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |
| IV. Rozwijanie kompetencji społecznych. Uczeń: | |
| | 1) bierze udział w różnych formach współpracy, jak: […] realizacja projektów, […] projektuje, tworzy i prezentuje efekty wspólnej pracy; |

## Wstęp do projektu (10 minut)

Dzisiaj uczniowie pracują w grupach nad własnym projektem AI. Celem jest znalezienie problemu, który można rozwiązać za pomocą klasyfikacji.

**Pomysły na projekty:**

1. Klasyfikator dyscyplin sportowych na podstawie liczby graczy i rodzaju piłki.

2. Klasyfikacja wyniku klasówki jako „zaliczone” lub „niezaliczone” na podstawie czasu nauki i liczby przespanych godzin.

3. Klasyfikacja pogody jako „deszcz” lub „brak deszczu” na podstawie ciśnienia i wilgotności powietrza.

## Samodzielna praca (45 minut)

Kroki projektu:

1. Zbierz dane (co najmniej 10 przykładów).

2. Podziel przykłady na dane uczące i testowe, np. 8 uczących i 2 testowe. Zapisz ich cechy i etykiety w osobnych listach w Pythonie.

3. Stwórz model drzewa decyzyjnego i ucz go wyłącznie na danych uczących.

4. Przetestuj model na danych testowych, których nie użyto do uczenia modelu, i porównaj przewidywania ze znanymi etykietami.

Dziesięć przykładów wystarcza do demonstracji, ale nie do potwierdzenia wiarygodności modelu.

## Podsumowanie i prezentacja (35 minut)

Każda grupa pokazuje, jak jej model radzi sobie z nietypowymi danymi.

!!! note "Uwaga"
    Uczenie maszynowe wykorzystuje się również w systemach rekomendacji, np. do proponowania filmów na podstawie preferencji użytkowników.
