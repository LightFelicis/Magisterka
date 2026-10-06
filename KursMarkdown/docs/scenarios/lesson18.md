# Lekcja 18 – Czym jest sztuczna inteligencja? Implementujemy uproszczone drzewo decyzyjne

**Czas realizacji:** 45 minut (1 godzina lekcyjna). Podany czas jest przybliżony i należy dostosować go do potrzeb oraz tempa pracy klasy.
{: .lesson-duration }

## Wymagana wiedza

- Instrukcje warunkowe `if`, `elif` i `else`.

## Treści z podstawy programowej

*Wybrane wymagania z podstawy programowej dla klas VII–VIII. [Źródło](https://zpe.gov.pl/podstawa-programowa/szkola-podstawowa/informatyka).*

| Dział | Sekcja |
| --- | --- |
| I. Rozumienie, analizowanie i rozwiązywanie problemów. Uczeń: | |
| | 1) formułuje problem w postaci specyfikacji (czyli opisuje dane i wyniki) oraz wyróżnia kroki w algorytmicznym rozwiązywaniu problemów. […] |
| II. Programowanie i rozwiązywanie problemów z wykorzystaniem komputera i innych urządzeń cyfrowych. Uczeń: | |
| | 1) projektuje, tworzy i testuje programy w procesie rozwiązywania problemów. W programach stosuje: instrukcje wejścia / wyjścia, wyrażenia arytmetyczne i logiczne, instrukcje warunkowe, instrukcje iteracyjne, funkcje oraz zmienne i tablice. W szczególności programuje algorytmy z działu I pkt 2; |

## Wstęp teoretyczny (20 minut)

Sztuczna inteligencja (AI) to dziedzina informatyki zajmująca się tworzeniem programów, które potrafią wykonywać zadania zwykle kojarzone z ludzką inteligencją.
Jednym z najprostszych modeli AI jest **drzewo decyzyjne** – seria pytań, które prowadzą do wyniku (decyzji).

**Przykłady z życia wzięte:**

*   **Bankowość**: decyzja o przyznaniu pożyczki na podstawie informacji o dochodach i historii spłat.

*   **Dobór ubrania**: wybór kurtki lub parasola na podstawie temperatury i opadów.

## Wspólne eksperymenty (15 minut)

Ręcznie zapisane instrukcje warunkowe ilustrują strukturę drzewa decyzji, ale nie pokazują uczenia maszynowego. Uczenie drzewa na danych poznamy na kolejnej lekcji.

Stwórzmy system klasyfikujący zwierzęta:

```python
print("Odpowiedz na pytania (tak/nie):")
czy_ma_piora = input("Czy ma pióra? ")

if czy_ma_piora == "tak":
    czy_lata = input("Czy lata? ")
    if czy_lata == "tak":
        print("To prawdopodobnie wróbel!")
    else:
        print("To prawdopodobnie struś!")
else:
    print("To prawdopodobnie ssak lub gad.")
```

## Zadania do rozwiązania (10 minut)

1. **Akinator**: Rozbuduj drzewo decyzyjne tak, aby potrafiło rozpoznać co najmniej pięć różnych zwierząt lub postaci z gier.
2. **Diagnoza komputera**: Napisz program, który pyta o objawy (np. „czy ekran działa?”, „czy słychać wentylator?”) i sugeruje rozwiązanie problemu z komputerem.
