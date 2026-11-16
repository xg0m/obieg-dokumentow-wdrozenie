# Etap 1. Analiza przedwdrożeniowa

Dokument zawiera notatki z warsztatu, listę wymagań, luki między stanem obecnym a docelowym oraz pytania otwarte do klienta. Dane są fikcyjne.

## Uczestnicy warsztatu

Data: 10.03.2026, czas: 2 godziny.

| Rola w projekcie | Stanowisko po stronie klienta | Czego dotyczy |
|---|---|---|
| Sponsor | Kanclerz | Cele, budżet, akceptacja koncepcji |
| Właściciel procesu | Kierownik działu kadr | Reguły wniosków delegacyjnych |
| Użytkownik kluczowy | Specjalista ds. finansowych | Akceptacja finansowa |
| Użytkownik końcowy | Pracownik naukowy | Wygoda wypełniania wniosku |
| IT klienta | Administrator systemów | Logowanie SSO, poczta, kopie zapasowe |

## Proces obecny (AS-IS)

1. Pracownik wypełnia wniosek w Wordzie, drukuje go i zbiera podpisy.
2. Bezpośredni przełożony akceptuje wniosek podpisem.
3. Dział finansów sprawdza, czy w budżecie projektu są środki.
4. Prorektor akceptuje wnioski powyżej 5000 zł.
5. Dział kadr archiwizuje papierowy wniosek.

Zgłoszone problemy: zaginione wnioski, brak informacji o statusie, ręczne przepisywanie danych do innych systemów, średni czas obiegu 6 dni roboczych.

## Wymagania

Priorytety wg MoSCoW: Must (konieczne), Should (ważne), Could (opcjonalne), Won (poza zakresem tego etapu).

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| W-01 | Formularz wniosku z polami: cel, miejsce, data wyjazdu, data powrotu, koszt szacowany, źródło finansowania | Must | Kadry |
| W-02 | Walidacja: data powrotu nie wcześniejsza niż data wyjazdu, koszt większy od zera | Must | Kadry |
| W-03 | Akceptacja przez bezpośredniego przełożonego | Must | Kadry |
| W-04 | Akceptacja finansowa przez dział finansów | Must | Finanse |
| W-05 | Dodatkowa akceptacja prorektora, gdy koszt przekracza 5000 zł | Must | Kanclerz |
| W-06 | Powiadomienie e-mail o każdej zmianie statusu wniosku | Should | Pracownik |
| W-07 | Logowanie kontem uczelnianym (SSO) | Must | IT |
| W-08 | Wnioskodawca widzi tylko własne wnioski, przełożony wnioski swojego zespołu | Must | IT |
| W-09 | Po akceptacji system generuje polecenie wyjazdu służbowego w PDF | Should | Kadry |
| W-10 | Miesięczny raport zestawienia wniosków dla finansów | Could | Finanse |
| W-11 | Import pracowników i struktury organizacyjnej z systemu kadrowego | Must | Kadry |
| W-12 | Zastępstwo przełożonego na czas urlopu | Should | Pracownik |
| W-13 | Aplikacja mobilna | Won | Pracownik |

## Luki (stan docelowy a obecny)

| Obszar | Stan obecny | Stan docelowy | Działanie |
|---|---|---|---|
| Status wniosku | Brak informacji | Widoczny w systemie i w e-mailu | Konfiguracja statusów i powiadomień |
| Dane pracowników | Ręczne wpisywanie | Import z systemu kadrowego | Mapowanie i migracja danych |
| Archiwum | Papier | Elektroniczne, z historią decyzji | Konfiguracja retencji |
| Zastępstwa | Ustne ustalenia | Zastępstwo w systemie | Reguła zastępstw w obiegu |

## Pytania otwarte do klienta

| Nr | Pytanie | Przyjęte założenie do czasu odpowiedzi |
|---|---|---|
| P-1 | Czy przełożony może zaakceptować własny wniosek? | Nie. Wniosek trafia do przełożonego wyższego szczebla. |
| P-2 | Kto zastępuje prorektora? | Drugi prorektor wskazany w słowniku ról. |
| P-3 | Czy trzeba integracji z systemem finansowym? | Nie w tym etapie. Dział finansów sprawdza budżet ręcznie. |
| P-4 | Jak długo przechowywać wnioski? | 5 lat od zakończenia roku budżetowego. |
