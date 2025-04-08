# Lab 6 — Docker, BuildKit & GitHub CLI

[🇬🇧 English](#english-version) | [🇵🇱 Polski](#wersja-polska)

---

## English version

### Part 1
#### Git initialization  
![Image](https://github.com/user-attachments/assets/403a0662-6739-42fd-9adb-c051d7182270)

#### Creating a public repository using the GitHub CLI
```bash
gh repo create pawcho6 --public --source=. --remote=origin --push
```
![Image](https://github.com/user-attachments/assets/dd1df948-fe1d-4a0f-83e2-4e858dd971a5)

#### Changes in `Dockerfile_stage_1_and_2`
SSH support and cloning of a private repository have been added. See `Dockerfile_stage_1_and_2` for full modifications.

---

### Part 2
#### Enabling BuildKit
```bash
set DOCKER_BUILDKIT=1
```
![Image](https://github.com/user-attachments/assets/38e91828-a479-46f6-baf3-95489dfcbf6b)

#### Building the image
```bash
docker build --ssh default -f Dockerfile_stage_1_and_2 -t ghcr.io/adamdawi/pawcho6:lab6 .
```
![Image](https://github.com/user-attachments/assets/d15652cf-00c6-4194-bcb7-008b6d72ff80)

#### Confirming the image build
![Image](https://github.com/user-attachments/assets/65c6282b-a8f7-4f7c-bd0b-3d2303f032d0)

#### Pushing the image
```bash
docker push ghcr.io/adamdawi/pawcho6:lab6
```
![Image](https://github.com/user-attachments/assets/e197cacb-5685-4ae4-a3ed-f44250561132)

The image visibility has been changed from private to public and linked to the repository. It’s available under the **Packages** tab.

#### Running the container
```bash
docker run -d --rm --name lab6_test -p 80:80 ghcr.io/adamdawi/pawcho6:lab6
```
![Image](https://github.com/user-attachments/assets/d06f39ac-bcca-4ef0-830d-52d1b428e590)

#### Viewing running containers
```bash
docker ps
```
#### Example output:
![Image](https://github.com/user-attachments/assets/f66538f3-a7bc-4d90-a203-f8e61aaba1d8)

#### Screenshot of the running web app:
![Image](https://github.com/user-attachments/assets/2d6f6d64-0cbd-4661-b513-ca4410a17548)

---

## Wersja polska

### Część 1
#### Inicjalizacja git  
![Image](https://github.com/user-attachments/assets/403a0662-6739-42fd-9adb-c051d7182270)

#### Stworzenie publicznego repozytorium z użyciem programu gh
```bash
gh repo create pawcho6 --public --source=. --remote=origin --push
```
![Image](https://github.com/user-attachments/assets/dd1df948-fe1d-4a0f-83e2-4e858dd971a5)

#### Wprowadzenie zmian w `Dockerfile_stage_1_and_2`
Dodano obsługę SSH i klonowanie prywatnego repozytorium. Zmiany można zobaczyć w pliku `Dockerfile_stage_1_and_2`.

---

### Część 2
#### Włączenie BuildKit
```bash
set DOCKER_BUILDKIT=1
```
![Image](https://github.com/user-attachments/assets/38e91828-a479-46f6-baf3-95489dfcbf6b)

#### Zbudowanie obrazu
```bash
docker build --ssh default -f Dockerfile_stage_1_and_2 -t ghcr.io/adamdawi/pawcho6:lab6 .
```
![Image](https://github.com/user-attachments/assets/d15652cf-00c6-4194-bcb7-008b6d72ff80)

#### Potwierdzenie zbudowania obrazu
![Image](https://github.com/user-attachments/assets/65c6282b-a8f7-4f7c-bd0b-3d2303f032d0)

#### Wysłanie obrazu
```bash
docker push ghcr.io/adamdawi/pawcho6:lab6
```
![Image](https://github.com/user-attachments/assets/e197cacb-5685-4ae4-a3ed-f44250561132)

Widoczność wysłanego obrazu została zmieniona z `private` na `public` i przypisana do repozytorium. Obraz można zobaczyć w zakładce **Packages**.

#### Polecenie do uruchomienia kontenera:
```bash
docker run -d --rm --name lab6_test -p 80:80 ghcr.io/adamdawi/pawcho6:lab6
```
![Image](https://github.com/user-attachments/assets/d06f39ac-bcca-4ef0-830d-52d1b428e590)

#### Polecenie do wyświetlenia uruchomionych kontenerów:
```bash
docker ps
```
#### Wynik działania polecenia `ps`:
![Image](https://github.com/user-attachments/assets/f66538f3-a7bc-4d90-a203-f8e61aaba1d8)

#### Zdjęcie pokazujące działanie aplikacji webowej:
![Image](https://github.com/user-attachments/assets/2d6f6d64-0cbd-4661-b513-ca4410a17548)
