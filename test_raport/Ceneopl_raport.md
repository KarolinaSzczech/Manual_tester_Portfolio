# Raport z testów logowania do strony https://ceneo.pl z użyciem przypadków testowych wysokiego poziomu #


| No. |	Przypadek testowy |Oczekiwany rezultat|	Otrzymany rezultat |
|----|---------|--------|---------|
|1 |  Logowanie istniejącego użytkownika poprawnymi danymi |	Użytkownik jest zalogowany do aplikacji | Działa|
|2 |  Próba zalogowania się istniejącego użytkownika z użyciem błędnego hasła | Użytkownik powinien zobaczyć komunikat np. „Nieprawidłowe dane uwierzytelniające” | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|3 |	Próba zalogowania się z użyciem losowego loginu i hasła (nie istniejącego w bazie) | Użytkownik powinien zobaczyć komunikat np.: „Nieprawidłowe dane uwierzytelniające” | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|4 |	Próba zalogowania się pustym formularzem | Powinna zostać wyświetlona informacja o wymaganej wartości lub Przycisk powinien być wyłączony tak długo, jak pola są puste | Walidacja działa|
|5 |	Weryfikacja pola logowania przy użyciu wielkich liter jako login i ważnego hasło | Użytkownik jest zalogowany do aplikacji Uwaga: Tylko jeśli tak ma to działać | Użytkownik poprawnie zalogowany|
|6 |	Weryfikacja pola logowania: w przypadku poczty e-mail weryfikacja polega tylko adresu @domain.com i ważnego hasła | Powinna zostać wyświetlona informacja "niepoprawna wartość" Uwaga: Jeżeli system używa adresu e-mail jako loginu, dobrze byłoby wyświetlić login@domena.com wraz z komunikatem "Nieprawidłowa wartość" | Walidacja działa. Pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|7 |	Zalogowany użytkownik wprowadza adres URL logowania | Użytkownik zostaje przekierowany na stronę główną| **Wykryto defekt - ID 001** Użytkownik nie został przekierowany na stronę główną. Pojawia się strona logowania |
|8 |	Wpisanie hasła na stronie logowania |	Hasło powinno być zamaskowane *** | Działa | 
|9 |	Używanie klawisza Tab do poruszania się po formularzu logowania |  Użytkownik może używać klawiatury do logowania się do aplikacji |	Działa|
|10 |	Używanie klawisza Enter do potwierdzenia formularza logowania | Użytkownik jest zalogowany do aplikacji	| Działa|
|11	| Zaznaczenie pola wyboru Zapamiętaj hasło i zalogowanie się przy użyciu poprawnych danych uwierzytelniających | Użytkownik powinien być zalogowany po ponownym wejściu na stronę, po ponownym uruchomieniu przeglądarki | Działa|
|12	| Trzykrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Blokada logowania na kilka minut i/lub e-mail do użytkownika o podejrzanej próbie logowania| **Wykryto defekt - ID 002** Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła |
|13 | Pięciokrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Blokada logowania na kilka minut i/lub e-mail do użytkownika o podejrzanej próbie logowania|**Wykryto defekt - ID 003** Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła. Pojawia się również reCAPTCHA z opcją zaznaczenia nie jestem robotem |

ID 001 Formularz rejestracji waliduje tylko po jednym polu na raz
Priorytet: Niski

Kroki:

Wejdź na stronę https://sprecords.pl/
Otwórz formularz rejestracji konta
Nie wypełniaj żadnego pola
Kliknij Zapisz
Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu Imię.

Wypełnij pole Imię
Kliknij Zapisz
Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu Nazwisko.

Wypełnij pola: Imię i Nazwisko
Kliknij Zapisz
Rezultat: Komunikat "Wypełnij pole" pojawia się tylko przy polu E-mail.

Wypełnij pola: Imię, Nazwisko i E-mail
Kliknij Zapisz



Zrobić zgłosznie na 7 12 i 13?
