# Przypadki testowe wysokiego poziomu dla strony https://ceneo.pl #


| No. |	Przypadek testowy |	Otrzymany rezultat |
|----|---------|-----------------|
|1 |  Logowanie istniejącego użytkownika poprawnymi danymi	|Działa. Użytkownik poprawnie zalogowany|
|2 |  Próba zalogowania się istniejącego użytkownika z użyciem błędnego hasła | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_.\|
|3 |	Próba zalogowania się z użyciem losowego loginu i hasła (nie istniejącego w bazie) | Walidacja działa. Widoczny komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|4 |	Próba zalogowania się pustym formularzem | Walidacja działa. Wyświetla się informacja o wymaganej wartości pól e-mail i hasło, nie można wysłać pustego formularza, a przycisk _Zaloguj się_ jest wyłączony tak długo, jak pola są puste|
|5 |	Weryfikacja pola logowania przy użyciu wielkich liter jako login i ważnego hasło | Użytkownik poprawnie zalogowany|
|6 |	Weryfikacja pola logowania: w przypadku poczty e-mail weryfikacja polega tylko adresu @domain.com i ważnego hasła | Walidacja działa. Pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_|
|7 |	Zalogowany użytkownik wprowadza adres URL logowania | Użytkownik nie został przekierowany na stronę główną. Pojawia się strona logowania|
|8 |	Weryfikacja czy po wejściu na stronę logowania i wpisaniu hasła jest ono zamaskowane *** |	Działa|
|9 |	Używanie klawisza Tab do poruszania się po formularzu logowania |	Działa|
|10 |	Używanie klawisza Enter do potwierdzenia formularza logowania |	Działa|
|11	| Zaznaczenie pola wyboru Zapamiętaj hasło i zalogowanie się przy użyciu poprawnych danych uwierzytelniających | Po ponownym wejściu na stronę, po ponownym uruchomieniu przeglądarki użytkownik jest zalogowany|
|12	| Trzykrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła|
|13 | Pięciokrotna próba zalogowania się jako istniejący użytkownik z nieprawidłowym hasłem | Brak blokady, użytkownik w dalszym ciągu ma możliwość logowania się, pojawia się komunikat _Niepoprawna nazwa użytkownika lub hasło_ oraz sugestia skorzystania z opcji przypomnienia hasła. Pojawia się również reCAPTCHA z opcją zaznaczenia nie jestem robotem|
