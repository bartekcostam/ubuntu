# Zestaw Zadań: Administracja Systemami Linux i macOS dla Technikum Informatycznego

## Spis Treści i Przegląd Struktury

### CZĘŚĆ A – UBUNTU SERVER 22.04 (VIRTUALBOX, HOST: WINDOWS)

Zestaw zawiera **40 praktycznych zadań** pogrupowanych w **9 działów**:

| Dział | Tytuł | Liczba Zadań | Zakres Tematyczny |
|-------|-------|--------------|------------------|
| **A1** | Podstawy pracy w konsoli i informacje o systemie | 5 | Logowanie, komendy systemowe, wersje OS |
| **A2** | System plików, ścieżki, tworzenie i usuwanie plików/katalogów | 5 | mkdir, rm, cp, mv, touch, struktury katalogów |
| **A3** | Edytor tekstu w konsoli (nano) | 4 | Tworzenie, edycja, zapisywanie plików tekstowych |
| **A4** | Użytkownicy, grupy i uprawnienia | 8 | Uprawnienia, chmod, chown, grupy, dostęp |
| **A5** | Procesy, usługi, logi | 5 | ps, top, systemctl, journalctl, logi systemowe |
| **A6** | Zarządzanie pakietami (apt) | 4 | apt update, install, remove, search |
| **A7** | Sieć i SSH (podstawy) | 3 | IP, routing, ping, ssh |
| **A8** | Proste skrypty powłoki (bash) | 4 | Skrypty .sh, zmienne, echo, uprawnienia |
| **A9** | Scenariusze podsumowujące (projektowe) | 2 | Złożone zadania łączące wiele działów |

**RAZEM: 40 zadań dla Ubuntu**

---

### CZĘŚĆ B – MacOS (M1, TERMINAL, ZSH)

Zestaw zawiera **13 praktycznych zadań** pogrupowanych w **3 działach**:

| Dział | Tytuł | Liczba Zadań | Zakres Tematyczny |
|-------|-------|--------------|------------------|
| **B1** | Podstawy Terminala na macOS | 4 | pwd, ls, cd, whoami, struktura katalogów |
| **B2** | Pliki, katalogi, uprawnienia na macOS | 5 | mkdir, rm, cp, mv, touch, chmod, nano, open |
| **B3** | Procesy i narzędzia (Homebrew, SSH) | 4 | top, ps, kill, brew, ssh |

**RAZEM: 13 zadań dla macOS**

---

## CZĘŚĆ A: UBUNTU SERVER 22.04

### DZIAŁ A1: Podstawy pracy w konsoli i informacje o systemie

#### Zadanie A1.1 – Logowanie i zmiana hasła

**Tytuł:** Zaloguj się do systemu Ubuntu i zmień swoje hasło

**Cel:** Uczeń ma nauczyć się logowania do systemu tekstowego oraz zarządzania hasłem.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Po uruchomieniu maszyny wirtualnej z Ubuntu Server 22.04 zobaczysz ekran logowania z tekstem podobnym do:
   ```
   Ubuntu 22.04 LTS server1 tty1
   server1 login:
   ```

2. Wpisz swoją nazwę użytkownika (którą ustawiłeś/ustawiłaś podczas instalacji Ubuntu) i wciśnij Enter.

3. Po wyświetleniu monitu na hasło, wpisz hasło (uwaga: hasło się nie wyświetla – to jest normalne).

4. Wciśnij Enter. Powinieneś/powinnać zobaczyć wiersz poleceń w formacie: `username@hostname:~$`

5. Teraz zmień swoje hasło. Wpisz komendę:
   ```
   passwd
   ```

6. System poprosi Cię o wpisanie starego hasła (uwaga: hasło się nie wyświetla).

7. Wpisz nowe hasło dwukrotnie (potwierdzenie).

8. Jeśli wszystko przebiegło prawidłowo, powinieneś/powinnać zobaczyć komunikat potwierdzający zmianę hasła.

**Dowód wykonania:** 
- Zrzut ekranu lub notatka z wynikiem komunikatu potwierdzającego zmianę hasła.
- Zaloguj się ponownie, aby upewnić się, że nowe hasło działa.

---

#### Zadanie A1.2 – Poznaj podstawowe komendy systemowe

**Tytuł:** Sprawdź informacje o systemie i użytkowniku za pomocą podstawowych komend

**Cel:** Uczeń ma nauczyć się używania komend do sprawdzenia podstawowych informacji systemowych.

**Poziom trudności:** Podstawowy

**Treść zadania:**

Po zalogowaniu się do systemu, wykonaj po kolei następujące komendy i zanotuj wyniki:

1. Wpisz `whoami` – zobaczysz swoją bieżącą nazwę użytkownika.

2. Wpisz `hostname` – zobaczysz nazwę komputera (hostname) w sieci.

3. Wpisz `date` – wyświetli się bieżąca data i godzina.

4. Wpisz `uptime` – zobaczysz, jak długo system jest włączony i ile średnio obciążenia ma.

5. Wpisz `uname -a` – wyświetli się szczegółowe informacje o systemie operacyjnym i jądrze Linuksa.

6. Wpisz `pwd` – zobaczysz ścieżkę katalogu, w którym się aktualnie znajdujesz.

**Dowód wykonania:** 
- Utwórz plik tekstowy (zadanie A3 może pomóc) z zapisanymi wynikami tych 6 komend.
- Lub: zrzuty ekranu pokazujące każdy wynik (dowód dla wszystkich 6 komend).

---

#### Zadanie A1.3 – Czytanie plików tekstowych i historia komend

**Tytuł:** Przeczytaj plik tekstowy i przejrzyj historię wpisanych komend

**Cel:** Uczeń ma nauczyć się czytania plików za pomocą `cat`, `less`, `head` i `tail` oraz korzystania z historii komend.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wpisz `cat /etc/os-release` – zobaczysz informacje o wersji systemu operacyjnego.

2. Wpisz `less /etc/os-release` – otworzysz ten sam plik w przeglądarce. Poruszaj się za pomocą strzałek lub spacji, aby przejść do następnej strony. Wciśnij `q`, aby zamknąć przeglądarkę.

3. Wpisz `head /etc/os-release` – zobaczysz pierwsze 10 linii pliku (domyślnie).

4. Wpisz `tail /etc/os-release` – zobaczysz ostatnie 10 linii pliku.

5. Teraz przejrzyj historię komend, którą właśnie wykonałeś/wykonałaś. Wpisz `history` – zobaczysz listę ostatnio wpisanych komend z numerami.

6. Opcjonalnie: wpisz `history | tail -20`, aby zobaczyć tylko ostatnie 20 komend.

**Dowód wykonania:** 
- Wpisz `history | tail -5 > plik_historia.txt` – zapiszesz ostatnie 5 komend do pliku (zadanie A2 może pomóc w zrozumieniu przekierowań).
- Zrzut ekranu pokazujący zawartość tego pliku.

---

#### Zadanie A1.4 – Nawigacja po katalogach głównych systemu

**Tytuł:** Poznaj strukturę katalogów systemowych i ich przeznaczenie

**Cel:** Uczeń ma nauczyć się rozumienia struktury katalogów Unix/Linux.

**Poziom trudności:** Podstawowy

**Treść zadania:**

W systemach Unix/Linux istnieje ustalona hierarchia katalogów. Przejdź do każdego z wymienionych katalogów i sprawdź, co się w nich znajduje:

1. Wpisz `cd /` – przejdziesz do katalogu głównego.

2. Wpisz `ls -la` – zobaczysz listę katalogów systemowych.

3. Przejdź do katalogu `/home` komendą `cd /home` i wpisz `ls` – zobaczysz katalogi domowe użytkowników.

4. Przejdź do katalogu `/tmp` komendą `cd /tmp` i wpisz `ls` – to katalog plików tymczasowych.

5. Przejdź do katalogu `/var/log` komendą `cd /var/log` i wpisz `ls` – tutaj znajdują się logi systemowe.

6. Przejdź do katalogu `/etc` komendą `cd /etc` i wpisz `ls | head -20` – tutaj znajdują się główne pliki konfiguracyjne.

7. Wrócić do katalogu domowego: wpisz `cd ~` lub po prostu `cd`.

**Dowód wykonania:** 
- Utwórz plik tekstowy z opisem co najmniej czterech katalogów (/, /home, /tmp, /var/log, /etc) – co się w nich znajduje i do czego służą.
- Plik powinien zawierać również wyniki `ls` z każdego katalogu.

---

#### Zadanie A1.5 – Wersja systemu i jądra

**Tytuł:** Sprawdź szczegółowe informacje o wersji systemu Ubuntu i jądra Linuksa

**Cel:** Uczeń ma nauczyć się odczytywania i interpretacji informacji o wersji systemu.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wpisz `cat /etc/os-release` – zobaczysz szczegółowe informacje o Ubuntu, m.in. VERSION i VERSION_ID.

2. Wpisz `uname -r` – zobaczysz numer wersji jądra Linuksa (np. 5.15.0-...).

3. Wpisz `lsb_release -a` (jeśli jest zainstalowane) – zobaczysz informacje o dystrybucji.

4. Przeczytaj uważnie te informacje i odpowiedz na pytania:
   - Jaka jest dokładna wersja Ubuntu zainstalowana na Twojej maszynie wirtualnej?
   - Jaka jest wersja jądra Linuksa?
   - Czy to jest wersja LTS (Long Term Support)?

**Dowód wykonania:** 
- Zrzut ekranu lub plik tekstowy zawierający odpowiedzi na powyższe pytania.
- Plik powinien zawierać także wyniki wpisanych trzech komend.

---

### DZIAŁ A2: System plików, ścieżki, tworzenie i usuwanie plików/katalogów

#### Zadanie A2.1 – Ścieżki względne i bezwzględne

**Tytuł:** Rozpoznaj i pracuj ze ścieżkami względnymi i bezwzględnymi

**Cel:** Uczeń ma nauczyć się różnicy między ścieżkami względnymi a bezwzględnymi.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Zaloguj się i przejdź do katalogu domowego: `cd ~`

2. Sprawdź bieżącą ścieżkę: `pwd` – powinna to być ścieżka bezwzględna (zaczynająca się od `/`), np. `/home/username`.

3. Teraz wykonaj: `cd /tmp` i ponownie `pwd` – to jest ścieżka bezwzględna do katalogu `/tmp`.

4. Przejdź z powrotem do domu i utwórz tam katalog o nazwie `test_sciezki`: 
   ```
   cd ~
   mkdir test_sciezki
   cd test_sciezki
   ```

5. Jesteś teraz w `/home/username/test_sciezki`. Stwórz katalog o nazwie `podkatalog`:
   ```
   mkdir podkatalog
   ```

6. Teraz pracuj ze ścieżkami względnymi. Wpisz:
   ```
   cd podkatalog
   pwd
   ```
   Powinieneś/powinnać zobaczyć ścieżkę bezwzględną, ale na etapie `cd` użyłeś/użyłaś ścieżki względnej (`podkatalog`).

7. Wpisz `cd ..` – przejdziesz do katalogu nadrzędnego (ścieżka względna `..` oznacza katalog rodzica).

8. Wpisz `cd ./podkatalog` – przejdziesz do `podkatalog` za pomocą ścieżki względnej (`.` oznacza bieżący katalog).

**Dowód wykonania:** 
- Zapisz wyniki `pwd` z każdego kroku w pliku tekstowym.
- Opisz, które były ścieżkami bezwzględnymi, a które względnymi.

---

#### Zadanie A2.2 – Tworzenie struktury katalogów projektu

**Tytuł:** Utwórz strukturę katalogów dla fikcyjnego projektu

**Cel:** Uczeń ma nauczyć się budowania struktur katalogów za pomocą `mkdir`.

**Poziom trudności:** Podstawowy

**Treść zadania:**

Wyobraź sobie, że startujesz projekt webowy. Musisz stworzyć następującą strukturę katalogów w katalogu domowym:

```
projekt1/
├── dokumenty/
├── kod/
│   ├── frontend/
│   └── backend/
├── testy/
└── dane/
```

1. Przejdź do katalogu domowego: `cd ~`

2. Utwórz katalog główny projektu:
   ```
   mkdir projekt1
   cd projekt1
   ```

3. Teraz utwórz katalogi na tym samym poziomie (będąc w `projekt1`):
   ```
   mkdir dokumenty
   mkdir kod
   mkdir testy
   mkdir dane
   ```

4. Teraz przejdź do katalogu `kod` i utwórz w nim podkatalogi:
   ```
   cd kod
   mkdir frontend
   mkdir backend
   cd ..
   ```

5. Sprawdź strukturę, którą utworzyłeś/utworzyłaś, wpisując:
   ```
   tree . 
   ```
   (Jeśli `tree` nie jest zainstalowany, zainstaluj je jako zadanie A6.1)

6. Jeśli `tree` nie działa, użyj zamiast tego:
   ```
   ls -la
   cd kod
   ls -la
   cd ..
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący strukturę za pomocą `tree` lub `ls -la`.

---

#### Zadanie A2.3 – Kopiowanie i przenoszenie plików

**Tytuł:** Skopiuj i przenieś pliki między katalogami

**Cel:** Uczeń ma nauczyć się posługiwania się komendami `cp` i `mv`.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu domowego i stwórz plik testowy:
   ```
   cd ~
   touch test_plik.txt
   echo "To jest zawartość testowa" > test_plik.txt
   ```

2. Skopiuj ten plik do katalogu `/tmp`:
   ```
   cp test_plik.txt /tmp/test_plik.txt
   ```

3. Sprawdź, czy plik został skopiowany:
   ```
   ls -la /tmp/test_plik.txt
   ```

4. Skopiuj plik z `/tmp` do katalogu `projekt1/dokumenty`:
   ```
   cp /tmp/test_plik.txt ~/projekt1/dokumenty/test_plik_kopia.txt
   ```

5. Teraz przenieś oryginalny plik z katalogu domowego do `projekt1`:
   ```
   mv test_plik.txt ~/projekt1/test_plik_przesuniety.txt
   ```

6. Sprawdź, czy plik istnieje w nowej lokalizacji, a nie w starej:
   ```
   ls -la ~/projekt1/test_plik_przesuniety.txt
   ls -la ~/test_plik.txt
   ```
   (Druga komenda powinna pokazać błąd "No such file or directory")

**Dowód wykonania:** 
- Zrzut ekranu pokazujący wyniki ostatniej komendy – potwierdzenie, że plik został przeniesiony.

---

#### Zadanie A2.4 – Usuwanie plików i katalogów

**Tytuł:** Bezpiecznie usuwaj pliki i katalogi

**Cel:** Uczeń ma nauczyć się usuwania plików i katalogów za pomocą `rm` oraz zrozumieć niebezpieczeństwo tej operacji.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu domowego:
   ```
   cd ~
   ```

2. Utwórz kilka plików testowych:
   ```
   touch plik1.txt plik2.txt plik3.txt
   ```

3. Usuń jeden plik:
   ```
   rm plik1.txt
   ```

4. Sprawdź, czy plik został usunięty:
   ```
   ls -la plik*.txt
   ```

5. Teraz spróbuj usunąć wiele plików na raz (ale bezpiecznie):
   ```
   rm -i plik2.txt plik3.txt
   ```
   (Flaga `-i` oznacza "interactive" – system poprosi Cię o potwierdzenie przed usunięciem każdego pliku)

6. Potwierdź każde usunięcie, wpisując `y` (yes).

7. Utwórz katalog testowy z plikami:
   ```
   mkdir test_usun
   touch test_usun/plik1.txt test_usun/plik2.txt
   ```

8. Teraz usuń katalog razem z jego zawartością:
   ```
   rm -r test_usun
   ```

9. Sprawdź, czy katalog został usunięty:
   ```
   ls -la test_usun
   ```
   (Powinna pojawić się informacja o błędzie)

**Dowód wykonania:** 
- Zrzut ekranu pokazujący ostateczny stan – brak usuniętych plików/katalogów.
- Notatka o zagrożeniach związanych z `rm -r`.

---

#### Zadanie A2.5 – Porządkowanie zaśmieconego katalogu

**Tytuł:** Oczyść i zorganizuj chaotycznie rozłożone pliki

**Cel:** Uczeń ma ćwiczyć umiejętność organizowania systemu plików.

**Poziom trudności:** Średni

**Treść zadania:**

1. Przejdź do katalogu domowego i utwórz katalog `chaos`:
   ```
   cd ~
   mkdir chaos
   cd chaos
   ```

2. Utwórz tam wiele plików różnych typów (będzie to odzwierciedlać typowy chaos na dysku):
   ```
   touch dokument1.txt dokument2.txt zdjecie1.jpg zdjecie2.jpg
   touch skrypt.sh dane.csv konfiguracja.conf notatka.txt
   touch zdjecie3.jpg program.py foto.png
   ```

3. Teraz Twoje zadanie polega na zorganizowaniu tego katalogu. Utwórz następujące podkatalogi:
   ```
   mkdir dokumenty
   mkdir obrazy
   mkdir skrypty
   mkdir konfiguracja
   ```

4. Przenieś pliki do odpowiednich katalogów:
   - Pliki `.txt` do `dokumenty`
   - Pliki `.jpg` i `.png` do `obrazy`
   - Pliki `.sh` i `.py` do `skrypty`
   - Pliki `.conf` i `.csv` do `konfiguracja`

5. Po zakończeniu, zweryfikuj strukturę za pomocą:
   ```
   tree .
   ```
   lub `ls -la` + `ls` w każdym podkatalogu.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący ostateczną strukturę i zawartość katalogów.

---

### DZIAŁ A3: Edytor tekstu w konsoli (nano)

#### Zadanie A3.1 – Tworzenie i edycja pliku w nano

**Tytuł:** Utwórz i edytuj prosty plik tekstowy za pomocą edytora nano

**Cel:** Uczeń ma nauczyć się posługiwania się edytorem nano.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu domowego:
   ```
   cd ~
   ```

2. Utwórz nowy plik w nano:
   ```
   nano moj_plik.txt
   ```

3. Wpisujesz się teraz w edytorze nano. Wpisz następujący tekst (lub dowolny inny):
   ```
   Moje pierwsze doświadczenie z edytorem nano
   
   Edytor nano jest prosty i intuicyjny.
   Pozwala na szybkie edytowanie plików tekstowych.
   ```

4. Aby zapisać plik, wciśnij `Ctrl+O` (litera O, nie zero).

5. System poprosi Cię o potwierdzenie nazwy pliku – po prostu wciśnij Enter (nazwa jest już ustawiona na `moj_plik.txt`).

6. Aby zamknąć edytor, wciśnij `Ctrl+X`.

7. Powinieneś/powinnać wrócić do wiersza poleceń. Sprawdź zawartość pliku:
   ```
   cat moj_plik.txt
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący zawartość pliku wyświetlaną przez `cat`.

---

#### Zadanie A3.2 – Edycja istniejącego pliku

**Tytuł:** Otwórz, edytuj i uzupełnij zawartość istniejącego pliku

**Cel:** Uczeń ma nauczyć się edytowania plików i nawigacji w nano.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Otwórz plik, który utworzyłeś/utworzyłaś w zadaniu A3.1:
   ```
   nano moj_plik.txt
   ```

2. Przejdź do końca pliku, wciśnij `Ctrl+End` lub kilka razy Enter.

3. Dodaj nowy akapit:
   ```
   
   To są moje uwagi dotyczące pracy z wierszem poleceń:
   - Trzeba pamiętać o ścieżkach plików
   - Bezpieczeństwo jest ważne
   - Praktyka czyni mistrza
   ```

4. Przejdź do początku pliku (`Ctrl+Home`) i dodaj nagłówek:
   ```
   === NOTATKI Z ADMINISTRACJI SYSTEMÓW ===
   
   ```

5. Zapisz plik (`Ctrl+O` + Enter).

6. Zamknij edytor (`Ctrl+X`).

7. Zweryfikuj zawartość:
   ```
   cat moj_plik.txt
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący pełną zawartość pliku – powinien zawierać nagłówek, oryginalny tekst i nowy akapit.

---

#### Zadanie A3.3 – Tworzenie pliku README projektu

**Tytuł:** Utwórz plik README dla projektu z informacjami o użytkowniku

**Cel:** Uczeń ma nauczyć się tworzenia dokumentacji przy użyciu nano.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu `projekt1`:
   ```
   cd ~/projekt1
   ```

2. Utwórz nowy plik `README.txt`:
   ```
   nano README.txt
   ```

3. Wpisz zawartość zgodnie z poniższym szablonem (uzupełnij własnymi danymi):
   ```
   ========================================
   PROJEKT: Projekt Webowy v1.0
   ========================================
   
   Autor: [Twoje imię i nazwisko]
   Data utworzenia: [dzisiejsza data]
   
   Opis:
   To jest projekt testowy, utworzony w ramach ćwiczeń z administracji systemów Linux.
   
   Struktura:
   - dokumenty/ - dokumentacja i notatki
   - kod/frontend - kod interfejsu użytkownika
   - kod/backend - logika aplikacji
   - testy/ - pliki testów
   - dane/ - dane lub bazy danych
   
   Instrukcje:
   1. Zapoznaj się z dokumentacją w katalogu dokumenty/
   2. Sprawdź kod w katalogu kod/
   3. Uruchom testy z katalogu testy/
   
   Status: W trakcie nauki
   ```

4. Zapisz plik i zamknij edytor.

5. Sprawdź zawartość:
   ```
   cat README.txt
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący zawartość pliku README.txt.

---

#### Zadanie A3.4 – Konfiguracja prostego pliku tekstowego

**Tytuł:** Utwórz plik konfiguracyjny ze zmiennymi

**Cel:** Uczeń ma nauczyć się przygotowywania prostych plików konfiguracyjnych.

**Poziom trudności:** Średni

**Treść zadania:**

1. Przejdź do katalogu `projekt1/konfiguracja` (jeśli go jeszcze nie masz, utwórz go):
   ```
   cd ~/projekt1
   mkdir -p konfiguracja
   cd konfiguracja
   ```

2. Utwórz plik konfiguracyjny `aplikacja.conf`:
   ```
   nano aplikacja.conf
   ```

3. Wpisz następującą konfigurację (możesz dostosować wartości):
   ```
   # Plik konfiguracyjny aplikacji
   # Utworzono w ramach ćwiczeń
   
   # Ustawienia ogólne
   APP_NAME = "Moja Aplikacja"
   VERSION = 1.0
   ENVIRONMENT = development
   
   # Ustawienia bazy danych
   DB_HOST = localhost
   DB_PORT = 5432
   DB_NAME = myapp_db
   DB_USER = admin
   
   # Ustawienia serwera
   SERVER_HOST = 127.0.0.1
   SERVER_PORT = 8080
   DEBUG = true
   
   # Logi
   LOG_LEVEL = info
   LOG_FILE = /var/log/aplikacja.log
   ```

4. Zapisz plik i zamknij edytor.

5. Sprawdź zawartość i uprawnienia:
   ```
   cat aplikacja.conf
   ls -la aplikacja.conf
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący zawartość pliku konfiguracyjnego.

---

### DZIAŁ A4: Użytkownicy, grupy i uprawnienia

#### Zadanie A4.1 – Interpretacja uprawnień plików

**Tytuł:** Przeanalizuj i opisz uprawnienia istniejących plików

**Cel:** Uczeń ma nauczyć się czytania i interpretacji uprawnień Unix (rw-r--r--).

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu domowego i sprawdź uprawnienia kilka plików:
   ```
   cd ~
   ls -la
   ```

2. Zobaczysz wynik podobny do:
   ```
   -rw-r--r--  1 user group  1234 Nov 30 12:34 plik.txt
   drwxr-xr-x  5 user group  4096 Nov 30 12:00 katalog
   ```

3. Przeanalizuj każdy element:
   - Pierwszy znak (`-` lub `d`) - czy to plik (`-`) czy katalog (`d`)?
   - Następne 3 znaki (rw-) - uprawnienia **właściciela** (read, write, execute)
   - Kolejne 3 znaki (r--) - uprawnienia **grupy**
   - Ostatnie 3 znaki (r--) - uprawnienia **innych** użytkowników

4. Utwórz plik do notatek:
   ```
   nano analiza_uprawnien.txt
   ```

5. Wpisz analizę dla co najmniej 5 plików/katalogów z wynika `ls -la`. Dla każdego opisz:
   - Nazwę pliku
   - Typ (plik czy katalog?)
   - Uprawnienia właściciela
   - Uprawnienia grupy
   - Uprawnienia innych

**Dowód wykonania:** 
- Plik `analiza_uprawnien.txt` zawierający prawidłowe interpretacje uprawnień.

---

#### Zadanie A4.2 – Zmiana uprawnień (chmod) – notacja symboliczna

**Tytuł:** Zmień uprawnienia pliku za pomocą chmod w notacji symbolicznej

**Cel:** Uczeń ma nauczyć się posługiwania się `chmod` z notacją symboliczną.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu domowego i utwórz plik testowy:
   ```
   cd ~
   touch plik_test.txt
   echo "Test uprawnień" > plik_test.txt
   ```

2. Sprawdź obecne uprawnienia:
   ```
   ls -la plik_test.txt
   ```

3. Teraz zmień uprawnienia. Wykonaj następujące operacje po kolei i obserwuj zmianę uprawnień:

   a) Usuń uprawnienia do czytania dla grupy i innych:
   ```
   chmod go-r plik_test.txt
   ls -la plik_test.txt
   ```

   b) Dodaj uprawnienia do wykonywania dla właściciela:
   ```
   chmod u+x plik_test.txt
   ls -la plik_test.txt
   ```

   c) Usuń uprawnienia do pisania dla wszystkich z wyjątkiem właściciela:
   ```
   chmod go-w plik_test.txt
   ls -la plik_test.txt
   ```

4. Przeanalizuj zmiany – jak się zmieniała reprezentacja uprawnień?

**Dowód wykonania:** 
- Zrzut ekranu pokazujący wynik `ls -la` po każdej zmianie uprawnień.

---

#### Zadanie A4.3 – Zmiana uprawnień (chmod) – notacja ósemkowa

**Tytuł:** Zmień uprawnienia pliku za pomocą chmod w notacji ósemkowej

**Cel:** Uczeń ma nauczyć się posługiwania się `chmod` z notacją ósemkową (cyfry 0-7).

**Poziom trudności:** Średni

**Treść zadania:**

Notacja ósemkowa: każda cyfra reprezentuje uprawnienia (r=4, w=2, x=1):
- 7 = 4+2+1 = rwx (wszystko)
- 6 = 4+2+0 = rw- (czytanie i pisanie)
- 5 = 4+0+1 = r-x (czytanie i wykonywanie)
- 4 = 4+0+0 = r-- (tylko czytanie)
- 0 = 0+0+0 = --- (brak uprawnień)

1. Utwórz kilka plików testowych:
   ```
   cd ~
   touch plik_700.txt plik_644.txt plik_755.txt
   ```

2. Ustaw uprawnienia za pomocą notacji ósemkowej:

   a) Plik właściciela z pełnymi uprawnieniami:
   ```
   chmod 700 plik_700.txt
   ls -la plik_700.txt
   ```
   (7 dla właściciela = rwx; 0 dla grupy = ---; 0 dla innych = ---)

   b) Plik z uprawnieniami rw-r--r-- (typowe):
   ```
   chmod 644 plik_644.txt
   ls -la plik_644.txt
   ```
   (6 dla właściciela = rw-; 4 dla grupy = r--; 4 dla innych = r--)

   c) Plik wykonywalny z uprawnieniami rwxr-xr-x:
   ```
   chmod 755 plik_755.txt
   ls -la plik_755.txt
   ```
   (7 dla właściciela = rwx; 5 dla grupy = r-x; 5 dla innych = r-x)

3. Interpretuj wyniki i opisz, jakie uprawnienia ma każdy plik.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący wynik `ls -la` dla wszystkich trzech plików po zmianach.
- Plik tekstowy z interpretacją każdego zestawu uprawnień.

---

#### Zadanie A4.4 – Zmiana właściciela i grupy (chown, chgrp)

**Tytuł:** Zmień właściciela i grupę pliku (wymaga sudo)

**Cel:** Uczeń ma nauczyć się `chown` i `chgrp` – uwaga: wymaga uprawnień administratora.

**Poziom trudności:** Średni

**Treść zadania:**

**Uwaga**: Zadanie wymaga uprawnień `sudo`. Upewnij się, że Twój użytkownik ma prawo do używania `sudo`.

1. Utwórz plik testowy:
   ```
   cd ~
   touch plik_wlasciciel.txt
   echo "Test własności" > plik_wlasciciel.txt
   ```

2. Sprawdź obecnego właściciela i grupę:
   ```
   ls -la plik_wlasciciel.txt
   ```

3. Najpierw zobaczysz, jakie grupy istnieją w systemie:
   ```
   cat /etc/group | head -20
   ```

4. Teraz zmień grupę (bez zmiany właściciela):
   ```
   sudo chgrp root plik_wlasciciel.txt
   ls -la plik_wlasciciel.txt
   ```
   (Powinna pojawić się prośba o hasło – wpisz hasło)

5. Jeśli chcesz zmienić zarówno właściciela, jak i grupę (zaawansowane – pomiń, jeśli nie masz uprawnień):
   ```
   sudo chown root:root plik_wlasciciel.txt
   ls -la plik_wlasciciel.txt
   ```

6. Przywróć oryginalnego właściciela:
   ```
   sudo chown $USER:$USER plik_wlasciciel.txt
   ls -la plik_wlasciciel.txt
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący zmiany właściciela i grupy.

---

#### Zadanie A4.5 – Sprawdzenie informacji o użytkowniku i grupach

**Tytuł:** Poznaj swoją tożsamość i grupy, do których należysz

**Cel:** Uczeń ma nauczyć się używania komend `id`, `groups`, `whoami`.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Sprawdź swoją nazwę użytkownika:
   ```
   whoami
   ```

2. Sprawdź identyfikator użytkownika (UID) i grupy (GID):
   ```
   id
   ```

3. Sprawdź, jakie grupy Ci przypisane:
   ```
   groups
   ```

4. Sprawdź informacje o konkretnym użytkowniku (np. root):
   ```
   id root
   ```

5. Utwórz plik z notatkami:
   ```
   nano informacje_uzytkownika.txt
   ```

6. W pliku zapisz:
   - Rezultaty powyższych czterech komend
   - Interpretację UID i GID
   - Opis, jakie grupy Ci przypisane i do czego mogą służyć

**Dowód wykonania:** 
- Plik `informacje_uzytkownika.txt` zawierający wyniki komend i interpretacje.

---

#### Zadanie A4.6 – Katalog współdzielony dla grupy

**Tytuł:** Utwórz katalog z uprawnieniami współdzielonymi dla grupy

**Cel:** Uczeń ma nauczyć się scenariusza, w którym kilku użytkowników współdzieli katalog.

**Poziom trudności:** Średni

**Treść zadania:**

**Uwaga**: To zadanie opisuje teoriię i praktykę, ale jeśli w systemie jest tylko jeden użytkownik, będziesz symulować to zadanie.

1. Utwórz katalog wspólny w `/home`:
   ```
   cd ~
   mkdir katalog_wspolny
   ```

2. Ustaw uprawnienia, aby właściciel mógł robić wszystko, a grupa mogła czytać i pisać:
   ```
   chmod 770 katalog_wspolny
   ls -la katalog_wspolny
   ```

3. Utwórz plik w tym katalogu:
   ```
   cd katalog_wspolny
   echo "Plik wspólny" > plik_wspolny.txt
   ```

4. Zmień uprawnienia pliku, aby był dostępny dla grupy:
   ```
   chmod 660 plik_wspolny.txt
   ls -la plik_wspolny.txt
   ```

5. Przeczytaj zawartość (powinna być dostępna):
   ```
   cat plik_wspolny.txt
   ```

6. Opisz w notatniku scenariusz: kto może robić co w tym katalogu i dlaczego uprawnienia 770 są odpowiednie.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący strukturę katalogów i uprawnienia.
- Plik tekstowy opisujący scenariusz współdzielenia.

---

#### Zadanie A4.7 – Uprawnienia specjalne: sticky bit

**Tytuł:** Zrozum i zastosuj sticky bit na katalogu

**Cel:** Uczeń ma nauczyć się specjalnych uprawnień – sticky bit.

**Poziom trudności:** Średni

**Treść zadania:**

Sticky bit (reprezentowany przez `t` w uprawnień) powoduje, że w katalogu każdy może tworzyć pliki, ale tylko właściciel pliku może go usunąć.

1. Utwórz katalog testowy:
   ```
   cd ~
   mkdir katalog_sticky
   ```

2. Ustaw uprawnienia bez sticky bit:
   ```
   chmod 777 katalog_sticky
   ls -la | grep katalog_sticky
   ```

3. Teraz dodaj sticky bit:
   ```
   chmod +t katalog_sticky
   ls -la | grep katalog_sticky
   ```
   (Powinieneś zobaczyć `t` zamiast `x` w ostatnich uprawnieniach, czyli `drwxrwxrwt`)

4. Alternatywnie, używając notacji ósemkowej (1777 = sticky bit + 777):
   ```
   chmod 1777 katalog_sticky
   ls -la | grep katalog_sticky
   ```

5. Utwórz w tym katalogu plik:
   ```
   cd katalog_sticky
   echo "Test sticky bit" > test.txt
   ```

6. Opisz, co się dzieje z plikami w katalogu z sticky bit – kto może je usunąć?

**Dowód wykonania:** 
- Zrzut ekranu pokazujący katalog z sticky bitem (widoczny `t`).
- Notatka opisująca scenariusz użycia sticky bit.

---

#### Zadanie A4.8 – Przegląd pliku /etc/passwd i /etc/group

**Tytuł:** Przejrzyj bazy danych użytkowników i grup systemu

**Cel:** Uczeń ma nauczyć się czytania systemowych baz użytkowników.

**Poziom trudności:** Średni

**Treść zadania:**

1. Przejrzyj plik `/etc/passwd`, który zawiera informacje o użytkownikach:
   ```
   cat /etc/passwd
   ```

2. Każda linia ma format: `użytkownik:x:UID:GID:Info:Home:Shell`
   - Np: `root:x:0:0:root:/root:/bin/bash`

3. Wyświetl tylko kilka linii:
   ```
   head /etc/passwd
   ```

4. Przejrzyj plik `/etc/group`, który zawiera informacje o grupach:
   ```
   cat /etc/group
   ```

5. Każda linia ma format: `grupa:x:GID:użytkownicy`

6. Znajdź swoją linię w `/etc/passwd`:
   ```
   grep $(whoami) /etc/passwd
   ```

7. Utwórz plik notatek:
   ```
   nano analiza_passwd_group.txt
   ```

8. Zapisz w nim:
   - Swoją linię z `/etc/passwd` i jej interpretacja
   - Kilka linii z `/etc/group` i ich interpretacja
   - Wyjaśnienie, co oznaczają kolumny `x` (hasło) i liczby (UID, GID)

**Dowód wykonania:** 
- Plik `analiza_passwd_group.txt` zawierający prawidłową interpretację.

---

### DZIAŁ A5: Procesy, usługi, logi

#### Zadanie A5.1 – Wyświetlanie procesów

**Tytuł:** Wyświetl listę bieżących procesów i zidentyfikuj ich PID

**Cel:** Uczeń ma nauczyć się używania `ps` do przeglądania procesów.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wyświetl wszystkie procesy bieżącego użytkownika:
   ```
   ps
   ```

2. Powinieneś zobaczyć kilka procesów, np. bash, ps itd. Dla każdego widać PID (Process ID).

3. Wyświetl więcej szczegółów:
   ```
   ps aux
   ```

4. Ta komenda pokazuje wszystkie procesy na systemie z dodatkowymi informacjami: CPU, RAM itp.

5. Wyszukaj konkretny proces (np. SSH):
   ```
   ps aux | grep ssh
   ```

6. Spróbuj znaleźć swój shell:
   ```
   ps aux | grep bash
   ```

7. Utwórz plik notatek:
   ```
   nano notatka_procesy.txt
   ```

8. Zapisz w nim:
   - Wynik `ps` – znaczenie każdej kolumny (PID, TTY, TIME, CMD)
   - Wynik `ps aux` – dodatkowymi kolumnami
   - Wyjaśnienie, co to jest PID i TTY

**Dowód wykonania:** 
- Plik notatek z prawidłową interpretacją polecenia `ps` i jego kolumn.

---

#### Zadanie A5.2 – Monitoring procesów w realnym czasie (top)

**Tytuł:** Obserwuj procesy i obciążenie systemu w realnym czasie za pomocą top

**Cel:** Uczeń ma nauczyć się używania `top` do monitorowania systemu.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Uruchom program `top`:
   ```
   top
   ```

2. Zobaczysz tabelę z bieżącymi procesami. Zwróć uwagę na:
   - Górny wiersz – uptime, liczba użytkowników, load average
   - Druga sekcja – użycie CPU i RAM
   - Lista procesów – PID, użytkownik, CPU%, MEM%, polecenie

3. W `top` możesz:
   - Wcisnąć `q`, aby wyjść
   - Wcisnąć `h`, aby wyświetlić pomoc
   - Wcisnąć `M`, aby sortować po pamięci RAM
   - Wcisnąć `P`, aby sortować po CPU

4. Wciśnij `M` (sortuj po RAM), obserwuj kilka sekund, potem wciśnij `P` (sortuj po CPU).

5. Zauważ, jak zmieniają się pozycje procesów na liście.

6. Wciśnij `q`, aby wyjść z `top`.

7. Utwórz plik notatek:
   ```
   nano notatka_top.txt
   ```

8. Opisz, co widziałeś/widziałaś: jakie procesy używały dużo CPU/RAM?

**Dowód wykonania:** 
- Zrzut ekranu pokazujący program `top` w działaniu.
- Plik notatek z obserwacjami.

---

#### Zadanie A5.3 – Uruchamianie procesu w tle i kontrola zadań

**Tytuł:** Uruchom proces w tle i dowiedz się o kontroli zadań

**Cel:** Uczeń ma nauczyć się uruchamiania procesów w tle i obsługi sygnałów SIGSTOP/SIGCONT.

**Poziom trudności:** Średni

**Treść zadania:**

1. Uruchom proces, który będzie działać przez kilka sekund:
   ```
   sleep 300 &
   ```
   (Ampersand `&` oznacza uruchomienie w tle. Proces będzie czekać przez 300 sekund = 5 minut)

2. Sprawdź, czy proces jest w tle:
   ```
   jobs
   ```

3. Zobaczysz listę zadań (jobs). Wpisz `ps` lub `ps aux | grep sleep`, aby znaleźć PID tego procesu.

4. Teraz uruchom kolejny proces w tle:
   ```
   sleep 600 &
   ```

5. Sprawdź ponownie `jobs`:
   ```
   jobs
   ```

6. Powinieneś zobaczyć dwa zadania.

7. Zakończ pierwsze zadanie (ze sleep 300). Wpisz:
   ```
   kill %1
   ```
   (Komenda `kill %1` wysyła sygnał SIGTERM do zadania nr 1)

8. Sprawdź `jobs` ponownie – pierwsze zadanie powinno zniknąć.

9. Zakończ drugie zadanie:
   ```
   kill %2
   ```

10. Sprawdź `jobs` – lista powinna być pusta.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący wynik `jobs` z kilkoma procesami w tle.
- Notatka opisująca znaczenie `&` i komendy `kill`.

---

#### Zadanie A5.4 – Sprawdzanie statusu usług (systemctl)

**Tytuł:** Sprawdź status systemowych usług za pomocą systemctl

**Cel:** Uczeń ma nauczyć się zarządzania usługami w Ubuntu za pomocą systemctl.

**Poziom trudności:** Średni

**Treść zadania:**

1. Sprawdź status usługi SSH:
   ```
   systemctl status ssh
   ```

2. Powinieneś zobaczyć, czy usługa jest aktywna (active) czy nie.

3. Wyświetl listę kilku ważnych usług:
   ```
   systemctl list-units --type=service | head -20
   ```

4. Sprawdź status usługi cron (planowanie zadań):
   ```
   systemctl status cron
   ```

5. Sprawdź usługę networking:
   ```
   systemctl status networking
   ```

6. Jeśli chcesz przeglądać wszystkie dostępne usługi:
   ```
   systemctl list-unit-files --type=service | grep enabled
   ```

7. Utwórz plik notatek:
   ```
   nano notatka_uslugi.txt
   ```

8. Zapisz:
   - Status SSH, cron, networking
   - Wyjaśnienie, co oznaczają stany: active, inactive, enabled, disabled
   - Znaczenie każdej usługi

**Dowód wykonania:** 
- Plik notatek z interpretacją statusu usług.

---

#### Zadanie A5.5 – Przegląd logów systemowych

**Tytuł:** Przejrzyj logi systemowe i wyszukaj w nich informacje

**Cel:** Uczeń ma nauczyć się czytania logów systemowych.

**Poziom trudności:** Średni

**Treść zadania:**

1. Wyświetl ostatnie 20 linii logu systemowego:
   ```
   tail -20 /var/log/syslog
   ```

2. Jeśli używasz Ubuntu z systemd (moderniejszy system):
   ```
   journalctl -n 20
   ```

3. Wyszukaj informacje o usłudze SSH w logach:
   ```
   grep -i ssh /var/log/syslog | tail -10
   ```

4. Lub za pomocą journalctl:
   ```
   journalctl -u ssh | tail -20
   ```

5. Przejrzyj logi związane z logowaniem (auth):
   ```
   tail -20 /var/log/auth.log
   ```

6. Utwórz plik notatek:
   ```
   nano notatka_logi.txt
   ```

7. Zapisz:
   - Ostatnie 5 linii z `/var/log/syslog` (lub journalctl)
   - Ostatnie 5 linii z `/var/log/auth.log`
   - Wyjaśnienie, co oznaczają logi i jakie informacje zawierają

**Dowód wykonania:** 
- Plik notatek zawierający rzeczywiste logi i ich interpretację.

---

### DZIAŁ A6: Zarządzanie pakietami (apt)

#### Zadanie A6.1 – Zainstaluj narzędzie (tree)

**Tytuł:** Zainstaluj pakiet tree za pomocą apt i używaj go do wizualizacji katalogów

**Cel:** Uczeń ma nauczyć się instalowania pakietów i używania `tree`.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Najpierw sprawdź, czy `tree` jest zainstalowany:
   ```
   tree --version
   ```
   Jeśli nie jest, zobaczysz błąd "command not found".

2. Jeśli trzeba zainstalować, najpierw zaktualizuj listę pakietów:
   ```
   sudo apt update
   ```
   (Pojawi się prośba o hasło – wpisz je)

3. Teraz zainstaluj `tree`:
   ```
   sudo apt install tree
   ```

4. Wpisz `y` (yes), aby potwierdzić instalację.

5. Po instalacji sprawdź wersję:
   ```
   tree --version
   ```

6. Teraz używaj `tree` do wizualizacji struktury katalogów:
   ```
   cd ~
   tree -L 2
   ```
   (Flaga `-L 2` pokazuje maksymalnie 2 poziomy głębokości)

7. Spróbuj z inną głębokością:
   ```
   tree -L 3 projekt1
   ```

8. Utwórz plik notatek z opisem, jak zainstalowaliśmy pakiet i jakie są główne flagi `tree`.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący zainstalowane `tree` i jego użycie.

---

#### Zadanie A6.2 – Szukanie pakietu w repozytorium

**Tytuł:** Wyszukaj pakiet w repozytorium apt przed zainstalowaniem

**Cel:** Uczeń ma nauczyć się przeszukiwania dostępnych pakietów.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wyszukaj pakiet `htop` (zaawansowana wersja `top`):
   ```
   apt search htop
   ```

2. Powinieneś zobaczyć wyniki wyszukiwania. Czytaj uważnie – każdy pakiet ma opis.

3. Sprawdź szczegółowe informacje o pakiecie przed zainstalowaniem:
   ```
   apt show htop
   ```

4. Zobaczysz informacje takie jak: Version, Size, Depends (zależności) itp.

5. Wyszukaj pakiet `ncdu` (analizator używanego miejsca na dysku):
   ```
   apt search ncdu
   ```

6. Sprawdź jego szczegóły:
   ```
   apt show ncdu
   ```

7. Utwórz plik notatek z porównaniem trzech pakietów:
   - `tree`
   - `htop`
   - `ncdu`

   Dla każdego zapisz: opis, wersję, rozmiar.

**Dowód wykonania:** 
- Plik notatek z porównaniem pakietów.

---

#### Zadanie A6.3 – Aktualizacja i usunięcie pakietu

**Tytuł:** Zaktualizuj system i usuń zainstalowany pakiet

**Cel:** Uczeń ma nauczyć się zarządzania pakietami – aktualizacje i usunięcia.

**Poziom trudności:** Średni

**Treść zadania:**

1. Sprawdź, czy dostępne są aktualizacje:
   ```
   sudo apt update
   ```
   (Aktualizuje listę pakietów z repozytorium)

2. Zobaczysz, ile pakietów ma dostępne aktualizacje.

3. Zainstaluj `ncdu`:
   ```
   sudo apt install ncdu
   ```

4. Potwierdź wpisaniem `y`.

5. Po zainstalowaniu, sprawdź, czy pakiet jest zainstalowany:
   ```
   ncdu --version
   ```

6. Teraz usuń pakiet:
   ```
   sudo apt remove ncdu
   ```

7. Potwierdź `y`.

8. Sprawdź, czy pakiet został usunięty:
   ```
   ncdu --version
   ```
   (Powinna pojawić się informacja "command not found")

9. Utwórz notatki opisujące proces instalacji i usunięcia.

**Dowód wykonania:** 
- Zrzuty ekranu pokazujące proces instalacji i usunięcia.
- Notatki opisujące kroki.

---

#### Zadanie A6.4 – Lista zainstalowanych pakietów

**Tytuł:** Wyświetl listę zainstalowanych pakietów i wyszukaj konkretny

**Cel:** Uczeń ma nauczyć się przeglądania zainstalowanych pakietów.

**Poziom trudności:** Średni

**Treść zadania:**

1. Wyświetl wszystkie zainstalowane pakiety:
   ```
   apt list --installed
   ```

2. Lista będzie długa – spróbuj filtrować. Wyszukaj pakiety związane z Python:
   ```
   apt list --installed | grep python
   ```

3. Policz, ile pakietów Python jest zainstalowanych:
   ```
   apt list --installed | grep python | wc -l
   ```

4. Wyszukaj pakiety związane z openssh:
   ```
   apt list --installed | grep openssh
   ```

5. Sprawdź, czy `tree` jest zainstalowany:
   ```
   apt list --installed | grep tree
   ```

6. Wyświetl ostatnio zainstalowane pakiety:
   ```
   apt list --installed | tail -20
   ```

7. Utwórz plik notatek z:
   - Liczbą zainstalowanych pakietów Python
   - Zainstalowanymi pakietami SSH
   - Innymi interesującymi pakietami, które znaleźliśmy

**Dowód wykonania:** 
- Plik notatek zawierający informacje o zainstalowanych pakietach.

---

### DZIAŁ A7: Sieć i SSH (podstawy)

#### Zadanie A7.1 – Informacje o sieciowych interfejsach

**Tytuł:** Sprawdź konfigurację sieciową maszyny wirtualnej

**Cel:** Uczeń ma nauczyć się diagnostyki sieciowej – IP, routing, interfejsy.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wyświetl informacje o interfejsach sieciowych:
   ```
   ip a
   ```

2. Powinieneś/powinnać zobaczyć kilka interfejsów:
   - `lo` (loopback – wewnętrzny interfejs 127.0.0.1)
   - `eth0` lub `enp0s...` (interfejs Ethernet)

3. Dla każdego interfejsu zobaczysz:
   - Link encap (rodzaj interfejsu)
   - HWaddr (adres MAC)
   - inet addr (adres IP)
   - Netmask (maska podsieci)
   - Broadcast
   - UP/DOWN (czy jest włączony)

4. Alternatywnie, możesz używać starej komendy (jeśli `net-tools` jest zainstalowany):
   ```
   ifconfig
   ```

5. Wyświetl tabelę routingu:
   ```
   ip route
   ```

6. Zobaczysz domyślną bramę (default via).

7. Utwórz plik notatek z:
   - Swoimi adresami IP dla każdego interfejsu
   - Maską podsieci
   - Domyślną bramą
   - Wyjaśnieniem każdego pola

**Dowód wykonania:** 
- Plik notatek z informacjami sieciowymi.

---

#### Zadanie A7.2 – Testowanie połączenia sieciowego (ping)

**Tytuł:** Przetestuj połączenie sieciowe za pomocą ping

**Cel:** Uczeń ma nauczyć się diagnostyki połączenia – ping.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Sprawdź, czy jest połączenie internetowe. Pinguj publiczny DNS:
   ```
   ping -c 4 8.8.8.8
   ```
   (Flaga `-c 4` oznacza wysłanie 4 pakietów; bez niej ping będzie działać w nieskończoność)

2. Jeśli ping działa, zobaczysz odpowiedzi z czasami (ms – milisekundy).

3. Jeśli ping nie działa, może nie być połączenia internetowego w maszynie wirtualnej – to normalne dla istniejących bez konfiguracji sieciowej.

4. Pinguj swój lokalny interfejs (loopback):
   ```
   ping -c 4 127.0.0.1
   ```
   (To zawsze powinno działać)

5. Pinguj domyślną bramę (znalezioną w zadaniu A7.1), np.:
   ```
   ping -c 4 192.168.0.1
   ```
   (Zastąp IP swoją bramą)

6. Utwórz plik notatek z:
   - Wynikami ping dla 8.8.8.8 (lub innymi)
   - Wynikami ping dla 127.0.0.1
   - Wyjaśnieniem, co oznaczają czasy odpowiedzi (ms)

**Dowód wykonania:** 
- Plik notatek z wynikami ping.

---

#### Zadanie A7.3 – Status usługi SSH

**Tytuł:** Sprawdź, czy SSH server jest uruchomiony i działający

**Cel:** Uczeń ma nauczyć się zarządzania usługą SSH.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Sprawdź status usługi SSH:
   ```
   systemctl status ssh
   ```

2. Powinieneś zobaczyć coś w rodzaju:
   ```
   ● ssh.service - OpenBSD Secure Shell server
   Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: enabled)
   Active: active (running) since ...
   ```

3. Jeśli SSH nie jest uruchomiony, możesz go uruchomić (wymaga sudo):
   ```
   sudo systemctl start ssh
   ```

4. Aby SSH uruchamiał się automatycznie przy starcie systemu:
   ```
   sudo systemctl enable ssh
   ```

5. Aby zatrzymać SSH (wymaga sudo):
   ```
   sudo systemctl stop ssh
   ```
   (Nie rób tego, jeśli logujesz się zdalnie!)

6. Sprawdź, na którym porcie słucha SSH:
   ```
   sudo ss -tlnp | grep ssh
   ```

7. Utwórz plik notatek z:
   - Statusem SSH
   - Portem, na którym słucha SSH (zwykle 22)
   - Wyjaśnieniem, co oznaczają stany "active", "enabled" itp.

**Dowód wykonania:** 
- Plik notatek zawierający informacje o SSH.

---

### DZIAŁ A8: Proste skrypty powłoki (bash)

#### Zadanie A8.1 – Stwórz pierwszy skrypt (Hello World)

**Tytuł:** Utwórz i uruchom prosty skrypt powłoki

**Cel:** Uczeń ma nauczyć się tworzenia i wykonywania skryptów bash.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Utwórz nowy plik skryptu:
   ```
   nano hello_world.sh
   ```

2. Wpisz zawartość:
   ```bash
   #!/bin/bash
   # To jest mój pierwszy skrypt
   
   echo "Cześć świecie!"
   echo "Mam nadzieję, że administracja systemami to fajne!"
   ```

3. Wyjaśnienie:
   - `#!/bin/bash` – pierwszy wiersz (shebang) mówi systemowi, jaki interpreter użyć
   - `#` – komentarz (system to ignoruje)
   - `echo` – wypisuje tekst na ekran

4. Zapisz plik i zamknij edytor.

5. Sprawdź zawartość:
   ```
   cat hello_world.sh
   ```

6. Spróbuj uruchomić skrypt (najpierw bez uprawnień do wykonywania):
   ```
   bash hello_world.sh
   ```

7. Powinieneś zobaczyć wynik. Teraz dodaj uprawnienia do wykonywania:
   ```
   chmod +x hello_world.sh
   ```

8. Teraz uruchom bezpośrednio:
   ```
   ./hello_world.sh
   ```

9. Powinien zadziałać w ten sam sposób.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący wynik skryptu.

---

#### Zadanie A8.2 – Skrypt ze zmiennymi i parametrami

**Tytuł:** Utwórz skrypt, który używa zmiennych i pobiera parametry

**Cel:** Uczeń ma nauczyć się zmiennych w skryptach bash.

**Poziom trudności:** Średni

**Treść zadania:**

1. Utwórz nowy skrypt:
   ```
   nano skrypt_zmienne.sh
   ```

2. Wpisz:
   ```bash
   #!/bin/bash
   # Skrypt ze zmiennymi
   
   # Zmienne zdefiniowane w skrypcie
   NAZWA_AUTORA="Jan Kowalski"
   DATA_DZISIAJ=$(date +%Y-%m-%d)
   
   # Zmienne z parametrów (argumentów skryptu)
   IMIE=${1:-"Użytkowniku"}  # Pierwszy parametr, domyślnie "Użytkowniku"
   
   # Wypisz informacje
   echo "Witaj $IMIE!"
   echo "Autor: $NAZWA_AUTORA"
   echo "Data dzisiejsza: $DATA_DZISIAJ"
   echo "Liczba parametrów przekazanych: $#"
   ```

3. Zapisz i zamknij.

4. Dodaj uprawnienia do wykonywania:
   ```
   chmod +x skrypt_zmienne.sh
   ```

5. Uruchom bez parametrów:
   ```
   ./skrypt_zmienne.sh
   ```

6. Uruchom z parametrem (Twoim imieniem):
   ```
   ./skrypt_zmienne.sh "Bartłomiej"
   ```

7. Zaobserwuj, jak zmienia się wyjście.

8. Utwórz plik notatek opisujący zmienne i ich znaczenie.

**Dowód wykonania:** 
- Zrzuty ekranu pokazujące wynik skryptu z różnymi parametrami.

---

#### Zadanie A8.3 – Skrypt tworzący strukturę katalogów

**Tytuł:** Utwórz skrypt, który automatycznie tworzy strukturę katalogów i plików

**Cel:** Uczeń ma nauczyć się automatyzacji poprzez skrypty.

**Poziom trudności:** Średni

**Treść zadania:**

1. Utwórz nowy skrypt:
   ```
   nano skrypt_projektowy.sh
   ```

2. Wpisz:
   ```bash
   #!/bin/bash
   # Skrypt tworzący strukturę projektu
   
   NAZWA_PROJEKTU=${1:-"moj_projekt"}
   
   echo "Tworzę projekt: $NAZWA_PROJEKTU"
   
   # Utwórz katalog główny
   mkdir -p "$NAZWA_PROJEKTU"
   cd "$NAZWA_PROJEKTU"
   
   # Utwórz podkatalogi
   mkdir -p dokumenty
   mkdir -p kod/{frontend,backend,testy}
   mkdir -p dane
   
   # Utwórz pliki README w każdym katalogu
   echo "# Dokumentacja" > dokumenty/README.md
   echo "# Kod przedniego końca" > kod/frontend/README.md
   echo "# Kod tylnego końca" > kod/backend/README.md
   
   echo "Projekt '$NAZWA_PROJEKTU' został utworzony!"
   echo "Struktura:"
   tree . 2>/dev/null || ls -la
   ```

3. Zapisz i zamknij.

4. Dodaj uprawnienia:
   ```
   chmod +x skrypt_projektowy.sh
   ```

5. Uruchom skrypt:
   ```
   ./skrypt_projektowy.sh "moj_nowy_projekt"
   ```

6. Sprawdź, czy struktura została utworzona:
   ```
   tree moj_nowy_projekt
   ```

7. Utwórz plik notatek opisujący, co robi skrypt i jakie komendy są w nim użyte.

**Dowód wykonania:** 
- Zrzut ekranu pokazujący utworzoną strukturę.

---

#### Zadanie A8.4 – Skrypt z kopią zapasową

**Tytuł:** Utwórz skrypt, który tworzy kopię zapasową pliku z datą

**Cel:** Uczeń ma nauczyć się tworzenia prostych narzędzi do automatyzacji.

**Poziom trudności:** Średni

**Treść zadania:**

1. Utwórz nowy skrypt:
   ```
   nano skrypt_backup.sh
   ```

2. Wpisz:
   ```bash
   #!/bin/bash
   # Skrypt tworzący kopię zapasową z datą
   
   PLIK=${1:?'Musisz podać nazwę pliku!'}
   
   if [ ! -f "$PLIK" ]; then
       echo "Błąd: Plik '$PLIK' nie istnieje!"
       exit 1
   fi
   
   # Utwórz katalog backupu (jeśli nie istnieje)
   mkdir -p backup
   
   # Nazwa pliku z datą
   DATA=$(date +%Y%m%d_%H%M%S)
   BACKUP_FILE="backup/${PLIK%.txt}_${DATA}.txt"
   
   # Skopiuj plik
   cp "$PLIK" "$BACKUP_FILE"
   
   echo "Kopia zapasowa utworzona: $BACKUP_FILE"
   ls -la "$BACKUP_FILE"
   ```

3. Zapisz i zamknij.

4. Dodaj uprawnienia:
   ```
   chmod +x skrypt_backup.sh
   ```

5. Utwórz plik testowy:
   ```
   echo "Ważne dane" > wazny_plik.txt
   ```

6. Uruchom skrypt:
   ```
   ./skrypt_backup.sh wazny_plik.txt
   ```

7. Uruchom kilka razy – każda kopia będzie miała inną datę w nazwie.

8. Sprawdź zawartość folderu backup:
   ```
   ls -la backup/
   ```

**Dowód wykonania:** 
- Zrzut ekranu pokazujący katalog backup z wieloma kopiami.

---

### DZIAŁ A9: Scenariusze podsumowujące (projektowe)

#### Zadanie A9.1 – Projekt administracyjny: Przygotowanie nowego konta i środowiska

**Tytuł:** Zaloguj się, przygotuj konto użytkownika, strukturę katalogów, uprawnienia i raport

**Cel:** Integracja wszystkich umiejętności z działów A1–A8.

**Poziom trudności:** Trudniejszy

**Treść zadania:**

Wyobraź sobie, że jesteś administratorem systemu. Nowy pracownik (lub programista) właśnie dołączył do zespołu. Musisz przygotować dla niego środowisko pracy.

**Etap 1: Przygotowanie informacji systemowych**

1. Zaloguj się do systemu.

2. Przygotuj dokument zawierający:
   - Bieżący czas/datę (`date`)
   - Nazwę hosta (`hostname`)
   - Wersję systemu (`cat /etc/os-release | grep PRETTY_NAME`)
   - Dostępne dyski/partycje (`df -h`)

**Etap 2: Struktura katalogów projektu**

3. W katalogu domowym utwórz strukturę projektu dla nowego pracownika:
   ```
   projekt_nowy_pracownik/
   ├── kod/
   │   ├── aplikacja/
   │   └── testy/
   ├── dokumentacja/
   ├── dane/
   ├── logi/
   └── backup/
   ```

**Etap 3: Uprawnienia**

4. Ustaw uprawnienia:
   - Katalog główny: 755 (właściciel może wszystko, inni tylko czytać/wchodzić)
   - Katalog kod/aplikacja: 770 (właściciel + grupa mogą wszystko)
   - Katalog dane: 700 (tylko właściciel)
   - Katalog logi: 755

**Etag 4: Pliki konfiguracyjne i dokumentacja**

5. Utwórz pliki w każdym katalogu:
   - W `dokumentacja/` utwórz `README.md` z opisem struktury
   - W `kod/` utwórz `INSTRUKCJA.txt` z wytycznymi kodowania
   - W `dane/` utwórz plik `.gitignore` lub `INDEX.txt`

**Etap 5: Skrypt instalacyjny**

6. Utwórz skrypt `setup.sh`, który robi kroki 3–5 automatycznie.

**Etap 6: Raport końcowy**

7. Utwórz plik `RAPORT_PRZYGOTOWANIA.txt` zawierający:
   - Kiedy został przygotowany (data/czas)
   - Dla kogo (nowy pracownik)
   - Kompletną strukturę katalogów (wynik `tree`)
   - Uprawnienia każdego katalogu (wynik `ls -la`)
   - Listę utworzonych plików konfiguracyjnych
   - Instrukcję, jak pracownik powinien korzystać z tego środowiska

**Dowód wykonania:**
- Struktura katalogów (zrzut `tree`)
- Raport PDF/TXT zawierający wszystkie informacje
- Skrypt `setup.sh` zautomatyzujący proces

---

#### Zadanie A9.2 – Projekt: System monitorowania logów i alertów

**Tytuł:** Stwórz system, który zbiera, analizuje i raportuje logi systemowe

**Cel:** Integracja umiejętności z działów A5, A6, A8.

**Poziom trudności:** Trudniejszy

**Treść zadania:**

**Etap 1: Przygotowanie struktury**

1. Utwórz katalog dla systemu monitorowania:
   ```
   mkdir -p ~/monitoring/{logi,skrypty,raporty}
   ```

**Etap 2: Skrypt zbierający logi**

2. Utwórz skrypt `zbierz_logi.sh`, który:
   - Pobiera ostatnie 50 linii z `/var/log/syslog`
   - Pobiera ostatnie 50 linii z `/var/log/auth.log`
   - Pobiera informacje o procesach (`ps aux | grep -E "cpu|mem"`)
   - Zapisuje wszystko do pliku timestampowanego w katalogu `monitoring/logi/`

**Etap 3: Skrypt analizujący logi**

3. Utwórz skrypt `analiza_bledow.sh`, który:
   - Wyszukuje błędy w logach (linie zawierające "error", "ERROR", "failed")
   - Liczy ich ilość
   - Wyszukuje ostrzeżenia (warning, WARNING)
   - Tworzy raport w `monitoring/raporty/`

**Etap 4: Raport podsumowujący**

4. Utwórz `raport_systemu.txt` zawierający:
   - Godzinę/datę generowania raportu
   - Uptime systemu
   - Obciążenie CPU
   - Użycie pamięci RAM
   - Liczbę błędów w systemie (ostatnie 24h)
   - Liczbę ostrzeżeń
   - Rekomendacje dla administratora

**Etap 5: Automatyzacja**

5. Utwórz skrypt `kron_monitoring.sh`, który uruchamia wszystkie powyższe skrypty i generuje raport dziennie.

**Dowód wykonania:**
- Struktura katalogów `monitoring`
- Trzy skrypty (`zbierz_logi.sh`, `analiza_bledow.sh`, `kron_monitoring.sh`)
- Raport z monitorowania zawierający rzeczywiste dane systemowe
- Wyjaśnienie, jak można to zautomatyzować w cron job

---

## CZĘŚĆ B: MacOS (M1, TERMINAL, ZSH)

### DZIAŁ B1: Podstawy Terminala na macOS

#### Zadanie B1.1 – Otwórz Terminal i sprawdź informacje systemowe

**Tytuł:** Uruchom Terminal na macOS i poznaj podstawowe komendy

**Cel:** Uczeń ma nauczyć się otwierania Terminala i sprawdzania informacji systemowych.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Otwórz Terminal:
   - Wciśnij `Cmd + Space` (Spotlight Search)
   - Wpisz "Terminal" i wciśnij Enter

2. Alternatywnie: Otwórz Finder → Applications → Utilities → Terminal

3. Po otwarciu zobaczysz wiersz poleceń. Powinieneś/powinnać widzieć `$` i kursor.

4. Wpisz `whoami` i wciśnij Enter – zobaczysz swoją nazwę użytkownika.

5. Wpisz `hostname` – zobaczysz nazwę komputera.

6. Wpisz `uname -a` – zobaczysz szczegóły macOS i procesora (M1 powinien być widoczny jako `arm64`).

7. Sprawdź wersję macOS:
   ```
   sw_vers
   ```

8. Utwórz plik notatek na biurku:
   ```
   nano ~/Desktop/informacje_mac.txt
   ```

9. Zapisz wyniki powyższych komend i wyjaśnij znaczenie każdej.

**Dowód wykonania:**
- Plik na biurku zawierający informacje systemowe.

---

#### Zadanie B1.2 – Nawigacja po katalogach macOS

**Tytuł:** Poruszaj się po katalogach macOS i poznaj strukturę

**Cel:** Uczeń ma nauczyć się nawigacji w systemie plików macOS.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Sprawdź, gdzie się znajdujesz:
   ```
   pwd
   ```
   (Powinna to być ścieżka do Twojego katalogu domowego, np. `/Users/username`)

2. Wyświetl zawartość:
   ```
   ls -la
   ```

3. Zobaczysz katalogi takie jak:
   - `Desktop` – biurko
   - `Documents` – dokumenty
   - `Downloads` – pobrane pliki
   - `Library` – biblioteka aplikacji (ukryta)
   - `Applications` – aplikacje zainstalowane

4. Przejdź do katalogu Desktop:
   ```
   cd Desktop
   ```

5. Sprawdzaj `pwd` – powinieneś/powinnać widzieć zmianę ścieżki.

6. Wyświetl zawartość:
   ```
   ls -la
   ```

7. Wróć do katalogu domowego:
   ```
   cd ~
   ```

8. Przejdź do `/Applications`:
   ```
   cd /Applications
   ```

9. Wyświetl zainstalowane aplikacje:
   ```
   ls -la | head -20
   ```

10. Utwórz plik notatek opisujący strukturę katalogów macOS i znaczenie głównych katalogów.

**Dowód wykonania:**
- Plik notatek opisujący strukturę macOS.

---

#### Zadanie B1.3 – Historia komend i aliasy

**Tytuł:** Przejrzyj historię wpisanych komend i utwórz alias

**Cel:** Uczeń ma nauczyć się pracy z historią i ułatwiać sobie pracę poprzez aliasy.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Wyświetl historię komend:
   ```
   history
   ```

2. Zobaczysz listę ostatnio wpisanych komend z numerami.

3. Wyświetl tylko ostatnie 10 komend:
   ```
   history | tail -10
   ```

4. Spróbuj skrótu – wciśnij kilka strzałek w górę (↑), aby cofnąć się w historii.

5. Utwórz alias (skrót) dla często używanej komendy. Otwórz plik `.zshrc`:
   ```
   nano ~/.zshrc
   ```

6. Przejdź na koniec pliku (Ctrl+End) i dodaj:
   ```
   alias ll="ls -la"
   alias doc="cd ~/Documents"
   alias desk="cd ~/Desktop"
   ```

7. Zapisz i zamknij (Ctrl+O, Enter, Ctrl+X).

8. Załaduj nową konfigurację:
   ```
   source ~/.zshrc
   ```

9. Teraz spróbuj nowego aliasu:
   ```
   ll
   ```
   (Powinno to być równoważne `ls -la`)

10. Spróbuj `doc` i `desk` – powinieneś/powinnać przejść do tych katalogów.

**Dowód wykonania:**
- Zrzut ekranu pokazujący działające aliasy.

---

#### Zadanie B1.4 – Otwieranie plików z Terminala w Finder

**Tytuł:** Otwórz katalogi i pliki w Finderze bezpośrednio z Terminala

**Cel:** Uczeń ma nauczyć się integracji Terminala z GUI macOS.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Będąc w dowolnym katalogu, otwórz go w Finderze:
   ```
   open .
   ```
   (Powinna otworzyć się ikona Finder z bieżącym katalogiem)

2. Przejdź do katalogu aplikacji w Terminalu i otwórz go w Finderze:
   ```
   cd /Applications
   open .
   ```

3. Utwórz plik tekstowy w Terminalu:
   ```
   cd ~/Desktop
   echo "Cześć z Terminala!" > test.txt
   ```

4. Teraz otwórz ten plik w domyślnym edytorze tekstowym:
   ```
   open test.txt
   ```

5. Plik powinien otworzyć się w domyślnym edytorze (np. TextEdit).

6. Możesz specyfikować edytor. Aby otworzyć w nano:
   ```
   nano test.txt
   ```

7. Aby otworzyć w konkretnej aplikacji:
   ```
   open -a TextEdit test.txt
   ```

8. Utwórz notatki opisujące użyteczność polecenia `open` w integracji CLI z GUI.

**Dowód wykonania:**
- Zrzut ekranu pokazujący otwarte okna Finder i edytora.

---

### DZIAŁ B2: Pliki, katalogi, uprawnienia na macOS

#### Zadanie B2.1 – Tworzenie i organizacja katalogów projektu

**Tytuł:** Utwórz strukturę katalogów na biurku dla projektu

**Cel:** Uczeń ma nauczyć się organizacji projektów na macOS.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź na biurko:
   ```
   cd ~/Desktop
   ```

2. Utwórz katalog projektu:
   ```
   mkdir projekt_mac
   cd projekt_mac
   ```

3. Utwórz podkatalogi:
   ```
   mkdir dokumenty kod dane backup
   ```

4. Przejdź do katalogu `kod`:
   ```
   cd kod
   ```

5. Utwórz podkatalogi:
   ```
   mkdir app skrypty testy
   ```

6. Wróć do projektu i przejrzyj strukturę:
   ```
   cd ..
   tree . 2>/dev/null || find . -type d | sort
   ```

7. Otwórz projekt w Finderze:
   ```
   open .
   ```

8. Sprawdź, czy struktura jest widoczna w Finderze.

**Dowód wykonania:**
- Zrzut ekranu pokazujący strukturę w Finderze.

---

#### Zadanie B2.2 – Tworzenie i edycja plików w nano

**Tytuł:** Utwórz i edytuj pliki konfiguracyjne w nano

**Cel:** Uczeń ma nauczyć się edycji plików w Terminalu na macOS.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do projektu:
   ```
   cd ~/Desktop/projekt_mac
   ```

2. Utwórz plik README:
   ```
   nano README.md
   ```

3. Wpisz zawartość (markdown):
   ```
   # Mój Projekt na macOS
   
   ## Opis
   To jest projekt testowy przygotowany na macOS z procesorem M1.
   
   ## Struktura
   - dokumenty/ - dokumentacja
   - kod/ - kod źródłowy
   - dane/ - pliki danych
   - backup/ - kopie zapasowe
   
   ## Status
   W trakcie nauki
   ```

4. Zapisz (Ctrl+O, Enter) i zamknij (Ctrl+X).

5. Otwórz plik i przeczytaj go:
   ```
   cat README.md
   ```

6. Teraz utwórz plik konfiguracyjny:
   ```
   nano config.ini
   ```

7. Wpisz zawartość:
   ```
   [Aplikacja]
   nazwa=Mój Projekt
   wersja=1.0
   autor=Ja
   
   [Serwer]
   host=localhost
   port=8080
   ```

8. Zapisz i zamknij.

**Dowód wykonania:**
- Zrzut ekranu pokazujący pliki w Finderze.

---

#### Zadanie B2.3 – Kopiowanie i przenoszenie plików

**Tytuł:** Skopiuj i przenieś pliki w projekcie

**Cel:** Uczeń ma nauczyć się operacji na plikach: cp, mv.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do projektu:
   ```
   cd ~/Desktop/projekt_mac
   ```

2. Utwórz plik testowy:
   ```
   echo "Zawartość testowa" > test.txt
   ```

3. Skopiuj plik do katalogu backup:
   ```
   cp test.txt backup/test_backup.txt
   ```

4. Sprawdź, czy kopia się znajduje:
   ```
   ls -la backup/
   ```

5. Przenieś oryginalny plik do katalogu dane:
   ```
   mv test.txt dane/test_przesuniety.txt
   ```

6. Sprawdź, czy plik został przeniesiony:
   ```
   ls -la dane/
   ```

7. Utwórz kilka plików dokumentacji:
   ```
   echo "Dokumentacja v1" > dokumenty/intro.md
   echo "Dokumentacja v2" > dokumenty/advanced.md
   ```

8. Skopiuj wszystkie pliki dokumentacji do backup:
   ```
   cp dokumenty/* backup/
   ```

9. Sprawdź zawartość backup:
   ```
   ls -la backup/
   ```

**Dowód wykonania:**
- Zrzut ekranu pokazujący zawartość katalogów po operacjach.

---

#### Zadanie B2.4 – Uprawnienia do plików na macOS

**Tytuł:** Zmień uprawnienia plików na macOS

**Cel:** Uczeń ma nauczyć się `chmod` na macOS.

**Poziom trudności:** Średni

**Treść zadania:**

1. Przejdź do projektu:
   ```
   cd ~/Desktop/projekt_mac
   ```

2. Utwórz plik testowy:
   ```
   echo "#!/bin/bash" > skrypt.sh
   echo "echo 'Hello'" >> skrypt.sh
   ```

3. Sprawdź uprawnień:
   ```
   ls -la skrypt.sh
   ```

4. Zauważ, że plik nie ma uprawnień do wykonywania (`x`).

5. Dodaj uprawnienia do wykonywania:
   ```
   chmod +x skrypt.sh
   ```

6. Sprawdź ponownie:
   ```
   ls -la skrypt.sh
   ```

7. Teraz powinieneś/powinnać widzieć `x` w uprawnień (np. `-rwxr-xr-x`).

8. Uruchom skrypt:
   ```
   ./skrypt.sh
   ```

9. Ustaw uprawnienia na 644 (rw-r--r--):
   ```
   chmod 644 skrypt.sh
   ls -la skrypt.sh
   ```

10. Teraz spróbuj uruchomić skrypt – powinna pojawić się informacja o błędzie (permission denied).

**Dowód wykonania:**
- Zrzut ekranu pokazujący zmiany uprawnień.

---

#### Zadanie B2.5 – Usuwanie plików i katalogów

**Tytuł:** Bezpiecznie usuwaj pliki i katalogi na macOS

**Cel:** Uczeń ma nauczyć się usuwania plików.

**Poziom trudności:** Podstawowy

**Treść zadania:**

1. Przejdź do katalogu dane:
   ```
   cd ~/Desktop/projekt_mac/dane
   ```

2. Utwórz kilka plików testowych:
   ```
   touch plik1.txt plik2.txt plik3.txt
   ```

3. Usuń jeden plik:
   ```
   rm plik1.txt
   ```

4. Sprawdź, czy plik został usunięty:
   ```
   ls -la
   ```

5. Usuń wiele plików z potwierdzeniem:
   ```
   rm -i plik2.txt plik3.txt
   ```

6. Wpisz `y` (yes) dla każdego pliku.

7. Wróć do projektu:
   ```
   cd ~/Desktop/projekt_mac
   ```

8. Utwórz katalog testowy:
   ```
   mkdir tymczasowy
   touch tymczasowy/test1.txt tymczasowy/test2.txt
   ```

9. Usuń katalog razem z zawartością:
   ```
   rm -r tymczasowy
   ```

10. Sprawdź, czy katalog został usunięty:
    ```
    ls -la
    ```

**Dowód wykonania:**
- Zrzut ekranu pokazujący ostateczny stan projektu.

---

### DZIAŁ B3: Procesy, narzędzia (Homebrew, SSH)

#### Zadanie B3.1 – Przeglądanie i zarządzanie procesami

**Tytuł:** Sprawdź uruchomione procesy i zarządzaj nimi

**Cel:** Uczeń ma nauczyć się `ps`, `top`, i `kill` na macOS.

**Poziom trudności:** Średni

**Treść zadania:**

1. Wyświetl procesy bieżącego użytkownika:
   ```
   ps
   ```

2. Powinieneś/powinnać zobaczyć kilka procesów, w tym shell i sam proces `ps`.

3. Wyświetl wszystkie procesy na systemie:
   ```
   ps aux
   ```

4. Lista będzie długa. Spróbuj filtrować – znajdź procesy Chrome (jeśli jest uruchomiony):
   ```
   ps aux | grep -i chrome
   ```

5. Otwórz program `top` do monitorowania w realnym czasie:
   ```
   top
   ```

6. Obserwuj procesy przez kilka sekund. Zwróć uwagę na:
   - Procesy z najwyższym CPU%
   - Procesy z najwyższym MEM%

7. Wciśnij `q`, aby wyjść z `top`.

8. Spróbuj alternatywy – `Activity Monitor` (GUI) lub use `ps` z dodatkowymi filtrami:
   ```
   ps aux | sort -k 3 -r | head -10
   ```
   (Sortuj po CPU i pokaż top 10)

9. Utwórz notatki opisujące procesy i ich monitorowanie.

**Dowód wykonania:**
- Zrzut ekranu pokazujący proces `top` lub wyniki `ps aux`.

---

#### Zadanie B3.2 – Instalacja narzędzi przez Homebrew

**Tytuł:** Zainstaluj narzędzia za pomocą Homebrew

**Cel:** Uczeń ma nauczyć się zarządzania pakietami na macOS.

**Poziom trudności:** Średni

**Treść zadania:**

1. Najpierw sprawdź, czy Homebrew jest zainstalowany:
   ```
   brew --version
   ```

2. Jeśli nie jest zainstalowany, zainstaluj go (instrukcja: https://brew.sh):
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

3. Po zainstalowaniu sprawdź wersję:
   ```
   brew --version
   ```

4. Wyszukaj narzędzie `tree`:
   ```
   brew search tree
   ```

5. Zainstaluj `tree`:
   ```
   brew install tree
   ```

6. Sprawdź, czy `tree` jest zainstalowany:
   ```
   tree --version
   ```

7. Teraz używaj `tree` do wizualizacji katalogów:
   ```
   tree ~/Desktop/projekt_mac -L 2
   ```

8. Zainstaluj inne przydatne narzędzie, np. `tldr` (dokumentacja komend):
   ```
   brew install tldr
   ```

9. Spróbuj:
   ```
   tldr ls
   ```

10. Utwórz plik notatek z listą zainstalowanych narzędzi i ich opisem.

**Dowód wykonania:**
- Zrzut ekranu pokazujący zainstalowane narzędzia.

---

#### Zadanie B3.3 – Tworzenie prostych skryptów na macOS

**Tytuł:** Utwórz skrypt bash działający na macOS

**Cel:** Uczeń ma nauczyć się tworzenia skryptów na macOS.

**Poziom trudności:** Średni

**Treść zadania:**

1. Przejdź do Desktop:
   ```
   cd ~/Desktop
   ```

2. Utwórz skrypt:
   ```
   nano info_mac.sh
   ```

3. Wpisz zawartość:
   ```bash
   #!/bin/bash
   # Skrypt informacyjny dla macOS
   
   echo "=== Informacje o macOS ==="
   echo ""
   echo "Użytkownik: $(whoami)"
   echo "Komputer: $(hostname)"
   echo "System: $(sw_vers -productName) $(sw_vers -productVersion)"
   echo "Procesor: $(uname -m)"
   echo ""
   echo "Uptime: $(uptime)"
   echo ""
   echo "Dyski:"
   df -h | head -5
   ```

4. Zapisz i zamknij.

5. Dodaj uprawnienia do wykonywania:
   ```
   chmod +x info_mac.sh
   ```

6. Uruchom skrypt:
   ```
   ./info_mac.sh
   ```

7. Powinieneś/powinnać zobaczyć informacje o systemie.

8. Teraz utwórz bardziej zaawansowany skrypt – `kopia_desktop.sh`:
   ```
   nano kopia_desktop.sh
   ```

9. Wpisz:
   ```bash
   #!/bin/bash
   # Skrypt tworzy kopię zapasową Desktop
   
   ZRODLO="$HOME/Desktop"
   BACKUP_DIR="$HOME/Desktop_Backup_$(date +%Y%m%d_%H%M%S)"
   
   echo "Tworzę kopię zapasową..."
   cp -r "$ZRODLO" "$BACKUP_DIR"
   
   echo "Gotowe! Backup w: $BACKUP_DIR"
   ls -la "$BACKUP_DIR"
   ```

10. Uruchom:
    ```
    chmod +x kopia_desktop.sh
    ./kopia_desktop.sh
    ```

**Dowód wykonania:**
- Zrzut ekranu pokazujący działające skrypty.

---

#### Zadanie B3.4 – Połączenie SSH do serwera (jeśli dostępny)

**Tytuł:** Nawiąż połączenie SSH do zdalnego serwera

**Cel:** Uczeń ma nauczyć się łączenia się z systemami zdalnymi.

**Poziom trudności:** Średni

**Treść zadania:**

**Uwaga**: To zadanie wymaga dostępu do zdalnego serwera. Jeśli go nie masz, przeprowadź go teoretycznie lub użyj Ubuntu Server z VirtualBox.

1. Podstawowa składnia SSH:
   ```
   ssh username@hostname_lub_ip
   ```

2. Przykład (do maszyny Ubuntu Server w VirtualBox):
   ```
   ssh student@192.168.0.50
   ```
   (Zastąp IP i username własnymi wartościami)

3. System poprosi o hasło – wpisz je.

4. Po zalogowaniu się, powinieneś/powinnać być w shell zdalnego serwera.

5. Sprawdź, że jesteś na innym systemie:
   ```
   hostname
   uname -a
   whoami
   ```

6. Wykonaj kilka komend na zdalnym systemie (jak się zalogowałeś):
   ```
   ls ~
   pwd
   date
   ```

7. Wyloguj się z serwera:
   ```
   exit
   ```

8. Powrócisz do macOS.

9. Utwórz plik notatek z opisem procesu SSH i jakie są korzyści ze zdalnego dostępu.

**Dowód wykonania:**
- Zrzut ekranu pokazujący logowanie przez SSH i wykon komendy na serwerze.

---

## PODSUMOWANIE

Zestawu zawiera **53 praktyczne zadania** (40 dla Ubuntu + 13 dla macOS) podzielone na 12 działów. Każde zadanie zawiera:

- **Tytuł i cel** – co uczeń ma się nauczyć
- **Poziom trudności** – od podstawowego do trudniejszego
- **Szczegółową treść** – krok po kroku, ale wymagającą samodzielnego myślenia
- **Dowód wykonania** – co powinno być wynikiem

Zadania można realizować sekwencyjnie lub wybierać selektywnie. Materiały są dostosowane do umiejętności 2–3 klasy technikum informatycznego.

---

**Dokument ten stanowi CZĘŚĆ 1: Główny Zestaw Zadań**

**Dalsze części zawierają:**
- CZĘŚĆ 2: Dodatki dla nauczyciela (wskazówki, rozwiązania, typ owe błędy)
- CZĘŚĆ 3: Setup środowiska (instrukcja konfiguracji VirtualBox i Ubuntu Server)

Czekaj na następne pliki Markdown...
