# Allegro Universal Importer

Publiczna dokumentacja techniczna wewnętrznego narzędzia do pracy z **Allegro REST API**.

## Cel projektu

Projekt służy do pobierania i lokalnego przetwarzania struktury Allegro potrzebnej do przygotowywania danych produktowych i ofertowych do masowego importu.

Zakres obejmuje w szczególności:

- pobieranie drzewa kategorii Allegro,
- pobieranie parametrów kategorii,
- pobieranie parametrów produktowych,
- pobieranie wartości słownikowych parametrów,
- zachowanie informacji o parametrach wymaganych i warunkowo wymaganych,
- tworzenie lokalnego snapshotu schematu Allegro,
- walidację danych przed przygotowaniem plików importowych,
- docelowo generowanie plików CSV zgodnych z mechanizmem Allegro **„Importuj i wystaw”**.

## Sposób użycia API

Aplikacja korzysta z oficjalnego **Allegro REST API**. Na obecnym etapie wykorzystuje operacje odczytu potrzebne do pobierania struktury kategorii i parametrów.

Główne wykorzystywane zasoby:

- `/sale/categories`
- `/sale/categories/{categoryId}/parameters`
- `/sale/categories/{categoryId}/product-parameters`

Do operacji dostępnych dla tokenu aplikacyjnego wykorzystywany jest OAuth 2.0 `client_credentials`.

## Identyfikacja aplikacji

Repozytorium pełni również funkcję publicznej strony dokumentacyjnej aplikacji na potrzeby identyfikacji żądań wysyłanych do Allegro REST API, w tym nagłówka `User-Agent`.

Wartość `User-Agent` jest konfigurowana lokalnie i powinna odpowiadać nazwie aplikacji zarejestrowanej w panelu Allegro Developer.

## Bezpieczeństwo

Repozytorium **nie zawiera i nie powinno zawierać**:

- `Client Secret`,
- tokenów OAuth,
- plików `.env` z danymi dostępowymi,
- danych logowania,
- danych klientów lub zamówień.

Dane uwierzytelniające są przechowywane wyłącznie lokalnie i przekazywane aplikacji przez bezpieczną konfigurację środowiska.

## Status

Projekt jest rozwijany etapowo. Aktualny etap koncentruje się na pobraniu, walidacji i utrzymaniu aktualnego schematu kategorii oraz parametrów Allegro.

W kolejnych etapach planowane są:

- uniwersalny arkusz roboczy do przygotowywania ofert,
- walidacja wymaganych parametrów zależnie od kategorii,
- obsługa wartości słownikowych,
- generator finalnych plików CSV do masowego importu ofert.

## Informacja

Projekt jest narzędziem wewnętrznym i nie jest oficjalnym produktem Allegro. Nazwa Allegro oraz Allegro REST API należą do ich odpowiednich właścicieli.
