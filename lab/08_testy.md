# Testy

## Podział
* **testy jednostkowe** (unit tests) — testujemy pojedynczą jednostkową część taką jak funkcje, metody czy klasy
* **testy integracyjne** (integration tests) — testujemy wiele komponentów systemu za jednym razem
* **testy regresyjne** (regression tests) — wszystkie testy w domenie biznesowej mające na celu sprawdzenie czy zmiana nie spowodowała błędu w innej części systemu
* **testy akceptacyjne** (acceptance tests) — testy weryfikujące czy aplikacja spełnia wymagania biznesowe

## TDD
TDD czyli **Test-Driven Development** jest techniką programowania, a jego kluczowym aspektem jest pisanie testu przed napisaniem docelowego kodu.
* funkcjonalności muszą być odizolowane od siebie tak żeby była możliwość ich testowania
* testy jednostkowe są dokumentacją programisty i upewnieniem się, że kod spełnia wszystkie wymagania klienta
* *Keep It Simple Stupid* czyli nie implementujemy nic na zaś, tylko to co jest aktualnie potrzebne  

Cykl pisania:
* piszemy teste który nie przechodzi
* piszemy kod aby przeszedł test
* refaktorujemy kod celem optymalizacji i poprawy jakości

## Przygotowanie środowiska
* wyświetlamy okienko *Python Package* widoczne jako zakładka u dołu ekranu
* znajdujemy paczkę ```pytest```, a następnie wybieramy przycisk Install    

## Testy jednostkowe
Przykład 1
```python
def f():
    return 3

def test_f():
    assert f() == 3
```
Przykład 2
``` python
def capital_case(x):
    return x.capitalize()

def test_capital_case():
    assert capital_case('camouflage') == 'Camouflage'

def test_raises_exceptions():
    with pytest.raises(TypeError):
        capital_case2(9)

def capital_case2(input):
    if not isinstance(input, str):
        raise TypeError('Input value must be string type')
      return input.capitalize()
```
Przykład 3 - *fixture* 
```python
import pytest

class Fruit:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name

@pytest.fixture
def my_fruit():
    return Fruit("apple")

@pytest.fixture
def fruit_basket(my_fruit):
    return [Fruit("banana"), my_fruit]

def test_my_fruit_in_basket(my_fruit, fruit_basket):
    assert my_fruit in fruit_basket
```
Przykład 4 - *parametrize*
```python
@pytest.mark.parametrize("test_input,expected", [("3+5", 8), ("2+4", 6), ("6*9", 54)])
def test_eval(test_input, expected):
    assert eval(test_input) == expected
```

## Materiały i dokumentacja
* https://devenv.pl/poziomy-testow/
* https://docs.pytest.org/en/7.1.x/getting-started.html
* https://doc.pytest.org/en/latest/explanation/fixtures.html
* https://doc.pytest.org/en/latest/how-to/parametrize.html#pytest-mark-parametrize-parametrizing-test-functions
* https://semaphoreci.com/community/tutorials/testing-python-applications-with-pytest


## Zadania
1. Przygotuj testy funkcji sprawdzającej czy osoba o przekazanym wieku jest pełnoletnia dla wieku 4, 18, 24, 38  
```def is_adult(age)```
2. Przygotuj testy funkcji zwracającej pole koła dla trzech różnych wartości, dodatkowo rozważ warunek w którym promień zostanie podany jako typ różny od *int* lub *float*  
```def calculate_circle_area(r)```
3. Przygotuj test sprawdzający działanie funkcji sortującej (własnej implementacji) wywołanej na liście zawierającej listę miast, adresów mailowych, numerów telefonów oraz wartości logicznych. Do przekazywania różnych danych wykorzystaj konstrukcję ```parametrize```
4. Przygotuj klasę *Kalkulator* posiadającą funkcje *dodawanie, mnożenie i potęgowanie*. Zaproponuj testy jednostkowe weryfikujące działanie kalkulatora.