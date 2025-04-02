# NTPD - 4
# Gabriela Myszkowiak, 120669

W celu wykonania zadania pierwszego tworzę plik *requirements* oraz *Dockerfile*
Następnie tworzę i uruchamiam obraz. Aplikacja uruchamia się poprawnie, nie generują się błędy.
Jedyną zmianą w kodzie jakiej dokonałam to dodanie zawartości nawiasów dla *app.run(host='0.0.0.0', port=5000)*

Sprawdzenie endpoint'a /predict dla:
* cURL
![image](https://github.com/user-attachments/assets/2e3fb71b-8d5a-47f1-83fe-ecbc1633c423)

* Postman
  ![image](https://github.com/user-attachments/assets/3e155376-9fc6-4b47-969b-9450e3b451b5)

Wyniki kolejnych testów są pozytywne.

# Instrukcje uruchamiania aplikacji

## Wymagania systemowe
- Python 3.9+
- Docker & Docker Compose
- PostgreSQL (jeśli planujemy serwis bazy danych)

## Uruchamianie aplikacji
1. Uruchamianie lokalne
-> Sklonuj repozytorium
-> Utwórz wirtualne środowisko i pobierz zależności
-> Uruchom aplikację

Aplikacja powinna działać na `http://127.0.0.1:5000` (domyślnie)

2. Uruchamianie z pomocą Dockera
-> Zbuduj obraz Dockera: docker build -t ntpd4 .
-> Uruchom kontener: docker run -p 5000:5000 ntpd4 (możesz dostosować mapowanie portów)
-> Sprawdź działanie aplikacji np. za pomocą cURL lub Postman (komendy do cURL'a widoczne powyżej i w poprzednim labie)

3. Uruchamianie z pomocą Docker Compose
-> Uruchom aplikację i bazę danych: docker-compose up --build -d
-> Sprawdź działanie endpoint'u np. za pomocą cURL lub Postman

### Pamiętaj żeby wszystkie pliki (plik aplikacji, pliki dockerowe i z zależnościami) znajdowały się w jednym folderze

## Zmienne środowiskowe
* FLASK_ENV - określa tryb działania aplikacji (development/production)
* DATABASE_URL - określa URL do bazy danych PostgreSQL

Zmienne te można dostosować w pliku docker-compose.yml

Należy również pamiętać o odpowiednim uzupełnieniu wszystkich informacji dotyczących bazy danych (hasło itp)
