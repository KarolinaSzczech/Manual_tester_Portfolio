 # Raport z testów #     
_(wersja pl)_
 
 
Raport z testów niedawno udostępnionej strony https://diety.nfz.gov.pl/

**Do testów użyto:** 

dane laptopa i przeglądarki

**Czas testów:**
 - Testowanie strony https://diety.nfz.gov.pl/ 4h
 - Na przygotowanie raportu około 2h

**Przeprowadzone testy:**
 - testy eksploracyjne,
 - testy użyteczności,
 - testy wydajności,
 - testy dostępności.

# Przetestowano: #

**Kalkulator BMI:**

Weryfikacja jakie dane przyjmuje formularz - **działa** 
Weryfikacja wyliczeń kalulatora na stronie z innym lub ze wzorem z wiki - **działa** 
Weryfikacja warunków brzegowych kalkulatora - **działa**


|Nr|	Test|	Wiek|	Wzrost|	Masa|	Aktywność	|Rezulat|
|--|---|---|---|---|---|---|
|1	|Minimalny wiek|	10|	10|	10|	1	|Pojawia się dymek przy polu wiek "value must be greater than or equal to 18"|
2	|Minimalny wzrost	|18	|10|	10|1|Pojawia się dymek przy polu wzrost "value must be greater than or equal to 100|
3	|Minimalna waga	18|	100|	10|	1|	Pojawia się dymek przy polu waga "value must be greater than or equal to 20"|
4|	Maksymalny wiek|	999|	999|	999|	1	|Pojawia się dymek przy polu wiek "value must be less than or equal to 120"|
5	|Maksymalny wzrost	|120	|999|	999|	1|	Pojawia się dymek przy polu wzrost "value must be less than or equal to 250"|
6	|Maksymalna waga	|120|	250	|999|	1|	Pojawia się dymek przy polu waga "value must be less than or|
