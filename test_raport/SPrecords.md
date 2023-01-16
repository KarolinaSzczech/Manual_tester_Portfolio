 # Raport z testów #     

Raport z testów strony https://sprecords.pl/


_**Desktop:**_

 - OS: Windows 10 PRO
 - Browser: Chrome version 107.0.5304.108 (Oficjalna wersja) (64-bitowa)
 - Browser: Firefox Developer Edition Wersja 108.0b6
 - Browser: Microsoft Edge Wersja 107.0.1418.56 (Oficjalna kompilacja) (wersja 64-bitowa)
 - Browser: Opera Wersja Wersja:94.0.4606.37  (wersja 64-bitowa)

_**Smartphone:**_

Device: POCO X3 NFC
Android wersja MIU 13.0.3
Browser Chrome version 107.0.5304.105

**Czas testów:**
 - Testowanie strony https://sprecords.pl/ 4h
 - Na przygotowanie raportu około 3h

# Przetestowano: #

### Rejestracja: ###

Wysłanie pustego formularza - nie działa poprawnie

#### _Wykryte defekty:_ ####

**ID-001 Formularz rejestracji waliduje tylko po jednym polu na raz** 

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Nie wypełniaj żadnego pola 
4. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu Imię

5. Wypełnij pole Imię
6. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu Nazwisko

7. Wypełnij pola: Imię i Nazwisko
8. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu E-mail

10. Wypełnij pola: Imię, Nazwisko i E-mail
11. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu Hasło

![Screen_1](https://user-images.githubusercontent.com/118970045/212694757-eb7dcc2f-ce01-4d4a-9497-89a3287f8424.png)
![Screen 2](https://user-images.githubusercontent.com/118970045/212694754-4ef4732d-42bb-42e4-8d76-d7f930bf927f.png)
![screen- brak emaila](https://user-images.githubusercontent.com/118970045/212695058-8619899d-b272-46ae-90dc-c41acb628775.png)
![screen - bez hasla](https://user-images.githubusercontent.com/118970045/212694750-5623b4fc-51a4-434d-855d-f1f2a10a937c.png)

Oczekiwane zachowanie: Komunikat "Wypełnij pole" powinien pojawić się przy wszystkich niewypełnionych polach.


Rejestracja konta z użyciem błędnego adresu e-mail (brak znaku @, użycie , zamiast .)- walidacja działa poprawnie

Rejestracja konta z użyciem długiego adresu email -

Weryfikacja walidacji hasła - **walidacja nie działa poprawnie**

_Na stronie brak informacji o wymaganiach hasła. Żeby utworzyć konto wystarczy wpisać 5 znaków, nie muszą spełniąć wymagań typu wielka litera, cyfra i znak specjalny. Hasłem może być pięć jednakowch małych liter np: aaaaa_ 

Weryfikacja użycia krótkiego hasła (krótszego niż 5 znaków) - **waliacja działa poprawnie** 

Weryfikacja użycia długiego hasła - **walidacja nie działa poprawnie**


#### _Wykryte defekty:_ ####

**ID-002 Formularz rejestracji nie waliduje za długiego hasła**

_Możliwe jest utworzenie konta z użyciem za długiego hasła ale nie jest możliwe poźniejsze zalogowanie się na konto z użyciem wybranego hasła._

Priorytet: Wysoki

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz rejestracji konta
3. Wypełnij poprawnie pola Imię, Nazisko, E-mail
4. Użyj bardzo długiego hasła wypełniając pole Hasło. Jako hasło ja użyłam słowa: Wiaderkoooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo
5. Naciśnij Zapisz

Rezultat: Konto zostało utworzone poprawnie, użytkownik zostaje zalogowany na stronie.

Następnie

6. Wyloguj się z konta
7. Zaloguj się na konto przy użyciu wcześniejszych danych z użyciem ustawionego długiego hasła.

Rezultat: Brak możliwości zalogowania się na utwrzone konto. Pod polem hasło pojawia się komunikat Niepoprawny format

![screen - brak możliwości zalogowania się](https://user-images.githubusercontent.com/118970045/212700822-c5640a56-8fe8-4410-860c-ea904b46fc1f.png)

Oczekiwane zachowanie: Komunikat "Nieprawidłowy format" powinien pojawiać się na etapie rejestracji konta, a nie dopiero na etapie logowania. 

Rejestracja konta z użyciem poprawnych danych - **działa**

Walidacja użycia wcześniej użytego adresu e-mial - walidacja działa poprawnie



### Logowanie: ###

Logowanie poprawnymi danymi - działa

Logowanie nieistniejącego użytkownika - walidacja działa

Logowanie z użyciem adresu E-mail innego użytkownika - walidacja działa poprawnie

Logowania danymi nieistniejącego konta - walidacja nie działa poprawnie

#### _Wykryte defekty:_ ####

**ID-003 Formularz logowania waliduje tylko po jednym polu na raz** 

Priorytet: Niski

Kroki:

1. Wejdź na stronę https://sprecords.pl/
2. Otwórz formularz logowania konta
3. Nie wypełniaj żadnego pola 
4. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu E-mail

5. Wypełnij pole E-mail
6. Kliknij Zapisz

Rezultat: Komunikat "Wypełnij pole" pojawia się przy polu Hasło

![logowanie 1](https://user-images.githubusercontent.com/118970045/212708281-8e58c326-0202-412e-b7bb-b0f78eca194a.png)
![logowanie 2](https://user-images.githubusercontent.com/118970045/212708290-6ca1aa89-107e-45e6-a839-a02b5cfeb3d1.png)


Oczekiwane zachowanie: Komunikat "Wypełnij pole" powinien pojawić od razu się przy wszystkich niewypełnionych polach.











