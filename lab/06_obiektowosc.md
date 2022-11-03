# Object-Oriented Programming
Paradygmat programowania, w którym programy definiuje się za pomocą obiektów opisanych za pomocą atrybutów *(czym obiekt jest)* oraz metod *(co obiekt może)*.

## POOP
Klasa - podstawowy schemat, według których tworzone są obiekt
```python
class Telefon:
    producent = "Samsung"

telefon = Telefon()
```
```python
class Drzewo:
    gatunek = None
    wiek = None
    czy_owocowe = None

    def podlej(self):
        print("Drzewo zostało podlane")
```
```python
class Drzewo:

    def __init__(self, gatunek, wiek, czy_owocowe):
        self.gatunek = make
        self.wiek = wiek
        self.czy_owocowe = czy_owocowe

    def podlej(self):
        print("Drzewo zostało podlane")

    def przytnij(self):
        print(f"Przycinam {self.gatunek}")

from drzewo import Drzewo

drzewo_1 = Drzewo("jabłoń", 10, true)
drzewo_2 = Drzewo("grusza", 2, true)
```

## Class vs instance variable
```python
class Zegarek:

    liczba_wskazowek = 3 #class variable

    def __init(self, kolor):
        self.kolor = kolor #instance variable

zegarek_1 = Zegarek("zloty")
zegarek_2 = Zegarek("czarny")

zegarek_1.liczba_wskazowek = 2 #tylko dla instancji
Zegarek.liczba_wskazowek = 4 #wpływa na wszystkie instancje

```

## Single, multilevel and multiple inhertiance
```python
class Organizm:
    zywy = True

class Zwierze(Organizm):
    def jesc(self):
        print("Je")

class Kot(Zwierze):
    def spij(self):
        print("Kot spi")

class Sztuczka():
    def aportuj(self):
        print("Aport")

class Pies(Zwierze, Sztuczka):
    rasa = None
```

## Metody magiczne
Są to funkcje, które należą do klasy i służą wykonywania ściśle określonych akcji. Charakteryzują się podwójnym podkreśleniem (*dunder* czyli **d**ouble **under**score) np. ```___str___, ___init__```

przykłady
* `__init__` - metoda wykorzystywana jako konstruktor obiektu, w niej podajemy parametry dla nowej instancji klasy
* `__str__` - metoda wywoływana przez wbudowaną funkcję `str`, `print` lub `format`, służy do wypisywania obiektu trybie *informal*
* `__repr__` - metoda wywoływana przez wbudowaną funkcję `repr`, służy do wypisywania obiektu w trybie *official*
* `__eq__` - metoda wywoływana w trakcie porównania obiektów przez operator `==`
* `__len__` - metoda wywołowana przez wbudowaną funkcję `len`
* `__iter__` - metoda wywoływana przez wbudowaną funkcję `iter` lub pętlę `for`
* `__add__` - metoda wywoływana w trakcie wywołania operatora `+` na obiektach
* `__getitem__` - metoda wywoływana w trakcie wywołania `obiekt[klucz]`
* `__slots__` - specjalna zmienna wykorzystywana do określenia atrybutów i metod. jakie klasa udostępnia

## Definicje
* metody i atrybuty klas https://pl.python.org/forum/index.php?topic=931

## Zadania
1. Stwórz jedną klasę o nazwie *Pojazd* zawierającą zmienne kolor, marka i pojemność silnika. Zainicjalizuj trzy różne instancje tej klasy.
2. Przygotuj klasę reprezentacją figurę na szachownicy o dwóch polach - *nazwa* oraz *waga*. Za pomocą odpowiednio zdefiniowanych magicznych metod posortuj za pomocą metody *sorted()*, a następnie wypisz w konsoli
3. Należy utworzyć klasę *Jednoślad*, zawierającą cechy i metody wspólne, a następnie dwie klasy *Skuter* i *Motocykl*, po niej dziedziczące. Należy zaproponować 2 atrybuty i 2 metody dla każdej z nich. Użytkownik ma mieć możliwość tworzenia nowych jednośladów z poziomu konsoli i wypisywania całej dotychczasowej bazy danych.