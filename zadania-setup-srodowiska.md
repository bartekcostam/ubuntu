# Setup Środowiska: Instrukcja Konfiguracji VirtualBox i Ubuntu Server 22.04

## SPIS TREŚCI

1. Wymagania sprzętowe
2. Pobranie VirtualBox i Ubuntu Server
3. Tworzenie i konfiguracja maszyny wirtualnej
4. Instalacja Ubuntu Server 22.04
5. Konfiguracja sieciowa
6. Instalacja przydatnych narzędzi
7. Tworzenie snapshot'ów dla uczniów
8. Rozwiązywanie problemów

---

## 1. WYMAGANIA SPRZĘTOWE

### Minimalne (będzie ciężko)
- CPU: 2 rdzenie
- RAM: 4 GB (z tego 2 GB dla VM)
- Dysk: 30 GB wolnego miejsca

### Zalecane (komfortowo)
- CPU: 4+ rdzenie
- RAM: 8+ GB (z tego 4 GB dla VM)
- Dysk: 100 GB wolnego miejsca

### System hosta
- Windows 10/11 (Home, Pro, Enterprise)
- VirtualBox obsługuje również macOS i Linux

---

## 2. POBRANIE VirtualBox I UBUNTU SERVER

### VirtualBox

1. Przejdź na https://www.virtualbox.org/wiki/Downloads
2. Pobierz **VirtualBox 7.0+** dla Windows
3. Uruchom instalator i postępuj zgodnie z instrukcjami (kliknij Next, Next, Finish)
4. Zainstaluj VirtualBox Extension Pack (opcjonalnie, ale polecane):
   - Pobierz Extension Pack z tej samej strony
   - Otwórz VirtualBox i idź do File → Preferences → Extensions
   - Dodaj pobrany Extension Pack

### Ubuntu Server 22.04 LTS

1. Przejdź na https://ubuntu.com/download/server
2. Pobierz **Ubuntu Server 22.04 LTS** (wybierz ISO image)
3. Zapisz plik ISO (około 1.5 GB) w łatwo dostępnym miejscu (np. `C:\ISO\`)

---

## 3. TWORZENIE MASZYNY WIRTUALNEJ

### Krok 1: Uruchomienie VirtualBox i Tworzenie Nowej VM

1. Otwórz VirtualBox
2. Kliknij **New** (lub Ctrl+N)
3. Wypełnij poniższe pola:

| Pole | Wartość |
|------|---------|
| **Name** | `Ubuntu-Server-22.04-Student-1` |
| **Machine Folder** | Domyślna (lub własna ścieżka) |
| **ISO Image** | Wybierz pobrany obraz Ubuntu 22.04 |
| **Type** | Linux |
| **Version** | Ubuntu (64-bit) |
| **Memory Size** | 2048 MB (2 GB) – minimum |
| **Processors** | 2 (jeśli masz) |
| **Hard Disk** | Create a Virtual Hard Disk Now |
| **Hard Disk Size** | 20 GB |

4. Kliknij **Finish**

### Krok 2: Dodatkowe Ustawienia Sieci

1. Maszyna została utworzona. Zaznacz ją i kliknij **Settings**
2. Przejdź do karty **Network**

**Adapter 1 (NAT – dostęp do internetu):**
- Attached to: **NAT**
- (To domyślne – pozwala VM na dostęp do internetu)

**Adapter 2 (Host-Only – połączenie z hostem):**
- Kliknij na **Adapter 2**
- Zaznacz **Enable Network Adapter**
- Attached to: **Host-only Adapter**
- Name: **vboxnet0** (lub istniejący)

3. Przejdź do karty **Storage**
- Sprawdzenie, czy Ubuntu ISO jest zmapowane do "Optical Drive"
- Jeśli nie, kliknij na **Empty** (CD ikonę) i wybierz obraz

4. Kliknij **OK**

---

## 4. INSTALACJA UBUNTU SERVER 22.04

### Krok 1: Uruchomienie VM i Instalacja

1. Kliknij **Start** (lub dwa razy na maszynę)
2. Maszyna uruchomi się z instalatora Ubuntu

### Krok 2: Menu Instalacji

Postępuj zgodnie z poniższymi krokami:

**1. Język:**
- Wybierz **English** (lub Polski, jeśli dostępny)
- Kliknij **Done**

**2. Klawiatura:**
- Wybierz **English (US)** lub swoją
- Kliknij **Done**

**3. Typ instalacji:**
- Wybierz **Ubuntu Server**
- Kliknij **Done**

**4. Sieć (Network):**
- System powinien auto-detect interfejsy
- Kliknij **Done**

**5. Proxy (jeśli nie masz, pomiń):**
- Zostaw puste
- Kliknij **Done**

**6. Ubuntu Archive Mirror:**
- Ustaw domyślny
- Kliknij **Done**

**7. Storage:**
- Wybierz **Use An Entire Disk**
- Zaznacz jedyny dysk VirtualBox
- Kliknij **Done**
- Potwierdź destructive action: **Continue**

**8. Profile Setup (WAŻNE!):**
- Your name: `Student` (lub imię ucznia)
- Your server's hostname: `ubuntu-server`
- Pick a username: `student` (mała litera!)
- Choose a password: `student123` (lub inne, ale zapamiętaj!)
- Confirm password: (powtórz)
- Kliknij **Done**

**9. SSH Setup:**
- Zaznacz **Install OpenSSH server** (POLECANE!)
- Kliknij **Done**

**10. Featured Server Snaps:**
- Pomiń (nie zaznaczaj nic)
- Kliknij **Done**

**11. Instalacja:**
- System zaczyna instalować
- Czekaj (może zająć 5-15 minut)
- Kliknij **Reboot Now**, gdy instalacja się skończy

### Krok 3: Pierwsza Rozruch

1. Po rebootcie zobaczysz prompt logowania:
   ```
   Ubuntu 22.04 LTS server tty1
   
   ubuntu-server login:
   ```

2. Zaloguj się:
   - Username: `student`
   - Password: `student123`

3. Powinieneś/powinnać zobaczyć prompt:
   ```
   student@ubuntu-server:~$
   ```

4. Gratulacje! Instalacja jest ukończona.

---

## 5. KONFIGURACJA SIECIOWA

### Sprawdzenie Adresu IP

1. Zaloguj się do VM jako `student`

2. Wpisz:
   ```
   ip a
   ```

3. Powinieneś zobaczyć coś w rodzaju:
   ```
   1: lo: <LOOPBACK,UP,LOWER_UP>
       inet 127.0.0.1/8
   
   2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP>
       inet 10.0.2.15/24
   
   3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP>
       inet 192.168.56.101/24
   ```

- `eth0` = NAT (do internetu)
- `eth1` = Host-only (do hosta)

### Konfiguracja Host-Only Network (opcjonalnie)

Jeśli chcesz stały IP na Host-Only:

1. Na maszynie wirtualnej:
   ```
   sudo nano /etc/netplan/00-installer-config.yaml
   ```

2. Zmień zawartość na:
   ```yaml
   network:
     version: 2
     ethernets:
       eth1:
         dhcp4: no
         addresses: [192.168.56.10/24]
         gateway4: 192.168.56.1
         nameservers:
           addresses: [8.8.8.8, 8.8.4.4]
   ```

3. Zapisz (Ctrl+O, Enter, Ctrl+X)

4. Zastosuj:
   ```
   sudo netplan apply
   ```

### SSH z Hosta do VM (Windows)

1. Na hoście (Windows) otwórz cmd/PowerShell:
   ```
   ssh student@192.168.56.101
   ```

2. Wpisz hasło: `student123`

3. Powinieneś być zalogowany na VM zdalnie!

---

## 6. INSTALACJA PRZYDATNYCH NARZĘDZI

Po zalogowaniu się, zainstaluj podstawowe narzędzia:

```bash
# Aktualizacja listy pakietów
sudo apt update

# Instalacja przydatnych narzędzi dla uczniów
sudo apt install -y build-essential curl wget git net-tools tree htop nano vim

# Wyjaśnienie:
# - build-essential: narzędzia do kompilowania
# - curl, wget: pobieranie plików
# - git: kontrola wersji
# - net-tools: narzędzia sieciowe (ifconfig, netstat itp.)
# - tree: wizualizacja katalogów
# - htop: zaawansowany top
# - nano, vim: edytory tekstu
```

---

## 7. TWORZENIE SNAPSHOT'ÓW

### Dlaczego Snapshot'y?

- Przed każdym zadaniem możesz zrobić snapshot
- Jeśli coś pójdzie nie tak, przywracasz snapshot
- Każdy uczeń może mieć swoją kopię

### Jak Zrobić Snapshot?

1. Wyłącz VM (z wiersza poleceń):
   ```
   sudo shutdown -h now
   ```
   Lub kliknij na VM i wybierz **Close** → **Power off the machine**

2. W VirtualBox, zaznacz VM i kliknij **Snapshots** (prawy panel)

3. Kliknij **Take Snapshot**

4. Wpisz nazwę:
   - `Fresh-Install` – czysta instalacja
   - `After-A1` – po zadaniu A1
   - `Before-A4` – przed zadaniem A4

5. Kliknij **OK**

### Jak Przywrócić Snapshot?

1. W panelu **Snapshots**, zaznacz snapshot
2. Kliknij **Restore**
3. Potwierdź
4. Maszyna wróci do stanu z tamtego snapshot'u

---

## 8. KLONOWANIE VM PENTRU UCZNIÓW

Jeśli chcesz, aby każdy uczeń miał swoją kopię VM:

1. W VirtualBox, zaznacz VM
2. Prawy klik → **Clone**
3. Wpisz nową nazwę: `Ubuntu-Server-Student-2`
4. Zaznacz **Full Clone** (pełna kopia, nie linked clone)
5. Kliknij **Clone**
6. Czekaj (może zająć kilka minut)

Teraz masz dwie niezależne maszyny wirtualne!

---

## 9. CZEKLIST PRZED LEKCJĄ

Przed rozpoczęciem lekcji, sprawdź:

- [ ] VirtualBox jest zainstalowany i działa
- [ ] Ubuntu Server 22.04 jest zainstalowany
- [ ] Możesz się zalogować na VM
- [ ] SSH działa (`ssh student@IP`)
- [ ] Internet działa na VM (`ping 8.8.8.8`)
- [ ] `tree`, `htop` i inne narzędzia są zainstalowane
- [ ] Zrobiłeś snapshot "Fresh-Install"
- [ ] Masz kopie VM dla każdego ucznia (lub wiesz, jak je klonować)

---

## 10. ROZWIĄZYWANIE PROBLEMÓW

### Problem: "VirtualBox nie chce się zainstalować"

**Przyczyna:** Możliwe, że masz zainstalowaną starszą wersję lub konflikt z innym oprogramowaniem.

**Rozwiązanie:**
1. Odinstaluj poprzednią wersję VirtualBox
2. Zrestartuj komputer
3. Zainstaluj nową wersję z administratorem

### Problem: "VM rusza się bardzo wolno"

**Przyczyna:** Za mało RAM przydzielono VM, lub procesor jest słaby.

**Rozwiązanie:**
1. W VirtualBox, Settings → System
2. Zwiększ Memory Size (ale zostawiaj co najmniej 2 GB dla hosta)
3. Zwiększ Processors, jeśli możliwe

### Problem: "Nie mogę się zalogować na VM"

**Przyczyna:** Zapomniałeś hasła lub błąd podczas instalacji.

**Rozwiązanie:**
1. Zresetuj hasło (boot do recovery mode) – zaawansowane
2. Odtwórz z snapshot'u
3. Zainstaluj VM od nowa

### Problem: "SSH nie działa"

**Przyczyna:** SSH nie jest zainstalowany lub firewall blokuje.

**Rozwiązanie:**
1. Na VM, zainstaluj SSH:
   ```
   sudo apt install openssh-server
   sudo systemctl start ssh
   sudo systemctl enable ssh
   ```

2. Sprawdź IP VM:
   ```
   ip a
   ```

3. Na hoście, spróbuj:
   ```
   ssh student@IP_Z_VM
   ```

### Problem: "Nie mogę usunąć pliku – permission denied"

**Przyczyna:** Brak uprawnień.

**Rozwiązanie:**
```bash
# Sprawdzenie uprawnień
ls -la plik

# Dodanie uprawnień (jeśli jesteś właścicielem)
chmod u+w plik

# Lub użycie sudo (jeśli to plik systemowy)
sudo rm plik
```

### Problem: "VM jest za mała (mało dysku)"

**Przyczyna:** 20 GB jest za mało dla wszystkich zadań.

**Rozwiązanie:**
1. W VirtualBox, zaznacz VM i kliknij **Settings** → **Storage**
2. Zaznacz dysk VirtualBox
3. Kliknij na ikonę dysku (prawy panel)
4. Zwiększ rozmiar (np. do 50 GB)
5. Na VM, użyj `resize2fs` (zaawansowane) lub zainstaluj VM od nowa

---

## 11. BACKUP I BEZPIECZEŃSTWO

### Backup VM

1. Zamknij VM
2. Skopiuj plik `.vdi` (dysk VM) do bezpiecznego miejsca:
   - Ścieżka: `C:\Users\YourUser\VirtualBox VMs\Ubuntu-Server-22.04-Student-1\`
   - Skopiuj plik `.vdi` do np. `D:\Backups\`

### Restoracja VM z Backupu

1. Skopiuj plik `.vdi` z backupu do oryginalnej lokalizacji
2. Otwórz VirtualBox i kliknij **New**
3. Przy tworzeniu VM, w kroku Storage, zaznacz **Use an existing virtual hard disk file**
4. Wybierz skopiowany plik `.vdi`
5. Gotowe!

---

## 12. KONFIGURACJA DLA WIELU UCZNIÓW

### Scenariusz: Pracownia komputerowa z 20 uczniami

**Rozwiązanie 1: Każdy uczeń ma swoją VM (idealne, ale wymaga dużo sprzętu)**

1. Utwórz template VM ("Master")
2. Sklonuj go 20 razy (zmień nazwy: Student-1, Student-2 itd.)
3. Każdy uczeń dostaje swoją VM

**Rozwiązanie 2: Zainstaluj na jednym komputerze, uczniowie pracują na ssh**

1. Uruchom VM na jednym potężnym komputerze
2. Każdy uczeń zaloguje się przez SSH z innego komputera
3. Wszyscy pracują na tej samej VM (mniej bezpieczeństwa, ale oszczędza zasoby)

**Rozwiązanie 3: Mix – VM na każdym komputerze, ale template na dysku sieciowym**

- Każdy komputer ma VirtualBox
- Każdy ma kopię VM z dysku sieciowego (szybka konfiguracja)

---

## KONIEC INSTRUKCJI SETUP'U

Jeśli coś nie działa, sprawdź:
1. Oficjalną dokumentację VirtualBox: https://www.virtualbox.org/wiki/Documentation
2. Ubuntu documentation: https://ubuntu.com/server/docs
3. Fora internetowe (Stack Overflow, Ask Ubuntu itp.)

Powodzenia!
