# Pliki
Moduł OS pozwala na nawiązanie interakcji między użytkownikiem, a systemem operacyjnym, zaczynamy od ```import os```

## Wyjątki
zdarzenia wykryte podczas wykonywania, które przerywają przepływ programu
```python
try:
    dzielna = int(input("Podaj liczbe do dzielenia: "))
    dzielnik = int(input("Podaj liczbe którą dzielimy: "))
    wynik = dzielna / dzielnik
except ZeroDivisionError as e:
    print(e)
    print("Nie mozna dzielić przez zero!")
except ValueError as e:
    print(e)
    print("Wprowadzona wartość musi być liczbą")
except Exception as e:
    print(e)
    print("Wystąpil błąd")
else:
    print(wynik)
finally:
    print("Ten blok kodu zawsze wykona się na końcu")
```

## Znajdywanie pliku
```python
path = "C:\\Users\\admin\\plik.txt"
project_file = "plik.txt"

if os.path.exists(path):
    print("Znaleziono")
else:
    print("Nie znaleziono")

os.path.isfile(path)
os.path.isdir(path)
```

## Operacje na plikach
po otwarciu poprzez *open()* nalezy pamiętać o wywołaniu *close()* na końcu
```python
f = open("file.txt", "a")
f.write("Nowy tekst dodany do pliku!")
f.close()
```

*with open()* automatycznie zamknie plik po zakończonych operacjach
```python
try:
    with open('plik.txt') as file:
        print(file.read())
except FileNotFoundError:
    print("Nie znaleziono pliku")
```

```python
text = "Witaj pliku"
with open('plik.txt','w') as file:
    file.write(text)
```

| mode | opis działania                                                      |
|------|---------------------------------------------------------------------|
| 'r'  | domyślny mode, otwiera plik do odczytu                              |
| 'w'  | otwiera plik do zapisu i nadpisuje dane                             |
| 'x'  | tworzy plik                                                         |
| 'a'  | otwiera plik do dopisywania danych nie usuwając istniejących        |

## Usuwanie pliku
```python
path = "plik.txt"

try:
    os.remove(path) # plik
    os.rmdir(path) # folder
except FileNotFoundError:
    print("Nie odnaleziono pliku")
except PermissionError:
    print("Brak dostepu do pliku")
else:
    print(f"Pomyslnie usunieto {path}")
```

## Definicje
* https://www.programiz.com/python-programming/methods/built-in/open

## Zadania
1. Utwórz plik integer_dataset.txt, który będzie zawierał 30 losowych liczb z przedziału (0; 200) oddzielonych spacjami, a następnie:
 * znajdź największą i najmniejszą liczbę
 * policz liczbę parzystych liczb
 * wyznacz średnią arytmetyczną załadowanych liczb
 * policz wszystkie liczby mniejsze lub równe 100.

2. Napisz program, który wczyta plik tekstowy o nazwie dane.txt zawierający kilka losowych zdań z generatora https://www.lipsum.com/, a następnie wypisze pobrane znaki w konsoli.
* stwórz histogram wystąpienia pojedynczych znaków w tekście w formie słownika
* wypisz pięć najczęściej występujących liter wraz z liczbą ich wystąpień
* zamień miejscami dwa najczęściej występujące znaki w tekście i zapisz cały zmieniony ciąg do pliku podmiana.txt
* odwróć kolejnością wszystkie znaki, a następnie zapisz je do pliku wspak.txt
* *dodatkowe zamień pierwszy znak z drugim, trzeci z czwartym, itd. 
