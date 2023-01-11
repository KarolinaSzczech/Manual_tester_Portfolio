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

**ID-001 Bład Serwera, przy zaznaczaniu dużej ilości produktów na liście zakupów** 

priorytet: **Wysoki**

Przygotowanie: Uśytkownik posiada konto w diety.nfz.gov.pl, ma wybrany jadłospis na tydzień

Kroki:

1. Zaloguj się i przejdź do https://diety.nfz.gov.pl/moje-konto/przepisy
2. Kliknij w przycisk Lista zakupów
3. Będąc na liście zakupów po kolei zaznaczać produkty
Rezultat: W pewnym momencie zaznaczania produktów powyżej ok 45 produktów, przeglądarka wyświetla błąd, w DevTools widać requesty ze statusem 500 Internal Server Error



![Screen_1](https://user-images.githubusercontent.com/118970045/211524527-bbe2865a-2f10-43f7-bc82-9a60da7d8063.png)



**ID-002 Produkty zaznaczone jako mam w domu są widoczne na wydruku listy** 

priorytet: **Średni**

Przygotowanie: Uśytkownik posiada konto w diety.nfz.gov.pl, ma wybrany jadłospis np. na 2 dni

Kroki:

1. Zaloguj się i przejdź do https://diety.nfz.gov.pl/moje-konto/przepisy
2. Kliknij w przycisk Lista zakupów
3. Będąc na liście zakupów zaznacz produkty z jednej grupy jako te które masz w domu
4. Kliknij pobierz listę zakupów
Rezultat: Na wydruku listy znajdują się czasem produkty, które zostały zaznaczone jako te które masz w domu. Błąd występuje losowo, najczęściej udało mi się zreprodukować zaznaczając tłuszcze i ryby

**ID-003 Stylowanie filtra kategorii**

priorytet: **Niski**

Przygotowanie: Uśytkownik posiada konto w diety.nfz.gov.pl, ma wybrany jadłospis

Kroki:

1. Zaloguj się i przejdź na Porady lub Filmy

<img width="455" alt="Screen_2" src="https://user-images.githubusercontent.com/118970045/211528759-62e35fb7-2e06-458e-8301-f6ac1c683d57.png">


**ID-004 Formularz rejestracji zbędny element pod polem hasła**

priorytet: Niski

Kroki:

Otwórz https://diety.nfz.gov.pl/rejestracja


![Screen_3](https://user-images.githubusercontent.com/118970045/211535927-ae9adc74-8138-4eb9-8a34-71c1d33b41dc.png)

![screen_11](https://user-images.githubusercontent.com/118970045/211787643-0ab2d451-bcc0-4ec4-982a-4952b1a6cfe0.png)



## Sugestie dotyczące użyteczności: ##

**ID-005 Zaznaczanie na liście zakupów całych sekcji** 

np. Chce zaznaczyć wszystkie przyprawy na raz żeby nie było ich na liście zakupów

**ID-006 Wydruk listy zakupów**

Fajnie gdyby był podzielony na 2 lub wiecej kolumn żeby nie trzeba było przewijać stron, lub w przypadku wydruku nie marnować papieru

<img width="387" alt="Screen 4" src="https://user-images.githubusercontent.com/118970045/211536517-62a96103-07b4-49fc-9cbc-2292e1c89c18.png">

**ID-007 Otwieranie Jadłospisu i Listy zakupów w nowej karcie lub od razu pobieranie pliku**

**ID-008 Lepsze nazwenictwo przycisków zamiast dodawanie pomocniczych treści obok**


<img width="357" alt="Screen 5" src="https://user-images.githubusercontent.com/118970045/211537007-d2cecfe4-a04c-481b-a577-84d383454cb5.png">

<img width="979" alt="Screen 6" src="https://user-images.githubusercontent.com/118970045/211537107-f4810733-14be-440e-bd52-b86978396929.png">

<img width="390" alt="Screen 7" src="https://user-images.githubusercontent.com/118970045/211537109-c0f60f27-c1a5-47c8-998b-92999beb6161.png">


**ID-009 Poprawa komunikatu dla użytkownika który podał za długi adres email**

<img width="1264" alt="Screen 8" src="https://user-images.githubusercontent.com/118970045/211537937-f7f205dd-c050-41e6-bb98-1bd6d8fc4e1f.png">

**ID-010 Walidacja w kalkulatorze BMI po polsku**

<img width="496" alt="Screeen 10" src="https://user-images.githubusercontent.com/118970045/211539600-27cda10b-103d-462c-a662-18784e8300af.png">


## Sugestie dotyczące dostępności: ##

## PODSUMOWANIE: ##

Strona nie powinna stwarzać problemów dla większości użytkowników. Większość elementów jest zauważalna i widoczna. Ukryte treści można odsłonić za pomocą strzałek lub klikając w odpowiednie miejsce. Nawigacja po stronie nie powinna stanowić problemów dla większości użytkowników. Brak elementów rozpraszających na stronie które mogłyby zaszkodzić osobie z epilepsją.





