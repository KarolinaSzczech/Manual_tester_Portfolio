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

### Kalkulator BMI: ###

Weryfikacja jakie dane przyjmuje formularz - **działa** 

Weryfikacja wyliczeń kalulatora na stronie z innym lub ze wzorem z wiki - **działa** 

Weryfikacja warunków brzegowych kalkulatora - **działa**



|Nr|	Test|	Wiek|	Wzrost|	Masa|	Aktywność	|Rezulat|
|--|---|---|---|---|---|---|
|1	|Minimalny wiek |	10|	10|	10|	1| Pojawia się dymek przy polu wiek "value must be greater than or equal to 18"|
|2	|Minimalny wzrost	|18	|10|	10|1| Pojawia się dymek przy polu wzrost "value must be greater than or equal to 100|
|3	|Minimalna waga	|18|	100|	10|	1|	Pojawia się dymek przy polu waga "value must be greater than or equal to 20"|
|4 |Maksymalny wiek |999|	999|	999|	1| Pojawia się dymek przy polu wiek "value must be less than or equal to 120"|
|5	|Maksymalny wzrost	|120	|999|	999|	1|	Pojawia się dymek przy polu wzrost "value must be less than or equal to 250"|
|6	|Maksymalna waga	|120|	250	|999|	1|	Pojawia się dymek przy polu waga "value must be less than or|


### Rejestracja: ###


Wysłanie pustego formularza - **walidacja działa**  Note: task do użyteczności

Rejestracja konta z użyciem poprawnych danych - **działa** 

Rejestracja konta z użyciem długiego adresu email - **walidacja działa** 

Weryfikacja walidacji hasła: za krótkie, brak wymaganych znaków, za długie - **działa**


### Logowanie: ###


Logowanie po aktywacji konta - **działa** 

Próba zalogowania danymi nie aktywowanego konta - **działa** 

Logowanie istniejacego użytkownika z nieprawidłowym hasłem - **walidacja działa** 

Wysłanie pustego formularza - **walidacja działa**

Podgląd hasła - **działa**


### Konfiguracja diety ###


Generowanie jadlospisu dla różnych typów diet i kaloryczności - **działa** 

Pobierz przepisy na dziś - **działa**

Wymiana posiłku - **działa** 

Pokaż składniki - **działa**


### Lista zakupów ###


Odznaczanie produktów - **działa z błędami** 

Pobierz listę zakupów - **działa z błędami**


### Dostępność ### 


Strona w powiększeniu 150% - **działa** 

Dostosowanie czcionek i kontrastu - **działa** 

Poruszanie się po stronie za pomocą klawiatury - **działa**


### Wersja mobilna ###

Przeglądanie przepisów w wersji mobilnej 
Przeglądanie listy zakupów w wersji mobilnej

## Wykryte defekty: ##

ID-001 Bład Serwera, przy zaznaczaniu dużej ilości produktów na liście zakupów
priorytet Wysoki

Przygotowanie: Uśytkownik posiada konto w diety.nfz.gov.pl, ma wybrany jadłospis na tydzień

Kroki:

Zaloguj się i przejdź do https://diety.nfz.gov.pl/moje-konto/przepisy
Kliknij w przycisk Lista zakupów
Będąc na liście zakupów po kolei zaznaczać produkty
Rezultat: W pewnym momencie zaznaczania produktów powyżej ok 40 produktów, przeglądarka wyświetla błąd, w DevTools Network widać requesty ze statusem 500 Internal Server Error
