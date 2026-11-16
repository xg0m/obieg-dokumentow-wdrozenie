# Wdrożenie systemu obiegu dokumentów. Case study

> Projekt edukacyjny. Klient, dane i wymagania są fikcyjne. Repozytorium pokazuje, jak przeprowadzić wdrożenie od analizy do przekazania systemu. Nie dotyczy żadnego konkretnego produktu komercyjnego.

## Scenariusz

Akademia Techniczna w Przykładowie (ok. 1200 pracowników) zastępuje papierowe i mailowe wnioski delegacyjne systemem elektronicznego obiegu dokumentów. Cele wdrożenia:

- skrócić średni czas akceptacji wniosku z 6 do 2 dni roboczych,
- mieć pełną historię decyzji w jednym miejscu,
- ograniczyć błędy w formularzach przez walidację pól.

## Etapy i dokumenty

| Etap | Dokument |
|---|---|
| 1. Analiza przedwdrożeniowa | [docs/01-wymagania.md](docs/01-wymagania.md) |
| 2. Projekt rozwiązania | [docs/02-proces.md](docs/02-proces.md), [process/wniosek-delegacyjny.bpmn](process/wniosek-delegacyjny.bpmn) |
| 3. Konfiguracja i dane startowe | [docs/03-konfiguracja.md](docs/03-konfiguracja.md) |
| 4. Testy akceptacyjne (UAT) | [docs/04-uat.md](docs/04-uat.md) |
| 5. Instrukcja i szkolenie | [docs/05-instrukcja-i-szkolenie.md](docs/05-instrukcja-i-szkolenie.md) |
| 6. Stabilizacja i przekazanie | [docs/06-status-i-przekazanie.md](docs/06-status-i-przekazanie.md) |

Migracją danych startowych zajmuje się osobny projekt: [migration-validator](https://github.com/xg0m/migration-validator).

## Jak pracuję z AI

Szkice dokumentów powstawały z pomocą narzędzi AI w terminalu. Reguły i kontekst pracy opisuje [AGENTS.md](AGENTS.md). Każdy dokument przechodzi moją weryfikację, a decyzje projektowe podejmuję sam.

## Autor

Oliwier Sieniuc, [@xg0m](https://github.com/xg0m). Licencja MIT.
