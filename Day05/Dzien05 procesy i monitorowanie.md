# Projekt IT37 – Dzień 5

## Temat: Procesy i monitorowanie systemu Linux

**Data:** 26.06.2026

---

## Cel zajęć

Poznanie sposobów wyświetlania, monitorowania oraz zarządzania procesami w systemie Linux.

---

## Wykonane polecenia

### 1. Wyświetlanie procesów

Podstawowe wyświetlenie procesów:

```bash
ps
```

Wyświetlenie wszystkich procesów systemowych:

```bash
ps aux
```

### Wnioski

* `ps` pokazuje procesy aktualnego terminala.
* `ps aux` pokazuje wszystkie uruchomione procesy w systemie.

---

### 2. Sprawdzenie domyślnej powłoki

Polecenie:

```bash
echo $SHELL
```

Wynik:

```bash
/bin/bash
```

### Wniosek

Domyślną powłoką użytkownika jest **bash**.

---

### 3. Filtrowanie procesów za pomocą grep

Wyszukiwanie procesów:

```bash
ps aux | grep systemd
ps aux | grep vmtoolsd
```

### Poznane pojęcia

* `grep` – wyszukuje tekst.
* `|` (pipe) – przekazuje wynik jednego polecenia do drugiego.

Zaobserwowano, że polecenie `grep` odnajduje również własny proces.

---

### 4. Monitorowanie systemu – top

Uruchomienie:

```bash
top
```

Zaobserwowane informacje:

* liczba procesów: około 237,
* pamięć RAM: około 7,4 GB,
* pamięć SWAP: 4 GB,
* proces o największym użyciu CPU: `vmtoolsd`.

---

### 5. Instalacja i uruchomienie htop

Instalacja:

```bash
sudo apt update
sudo apt install htop
```

Uruchomienie:

```bash
htop
```

Zaobserwowane informacje:

* liczba rdzeni CPU: 4,
* pamięć RAM: około 7,2 GB,
* interfejs programu jest bardziej czytelny niż `top`.

---

### 6. Tworzenie i kończenie procesu

Uruchomienie procesu:

```bash
sleep 60 &
```

Wyszukanie procesu:

```bash
ps aux | grep sleep
```

Zakończenie procesu:

```bash
kill PID
```

Po zakończeniu procesu:

```bash
ps aux | grep sleep
```

wyświetlany był już tylko proces `grep`.

---

## Poznane polecenia

| Polecenie     | Zastosowanie                   |                                         |
| ------------- | ------------------------------ | --------------------------------------- |
| `ps`          | wyświetlanie procesów          |                                         |
| `ps aux`      | wszystkie procesy systemowe    |                                         |
| `grep`        | wyszukiwanie tekstu            |                                         |
| `             | `                              | przekazywanie danych między poleceniami |
| `top`         | monitor systemu                |                                         |
| `htop`        | zaawansowany monitor systemu   |                                         |
| `sleep`       | uruchamianie procesu testowego |                                         |
| `kill`        | kończenie procesu              |                                         |
| `echo $SHELL` | sprawdzanie domyślnej powłoki  |                                         |

---

## Podsumowanie

Podczas Dnia 5 nauczyłem się:

* wyświetlać uruchomione procesy,
* filtrować procesy za pomocą `grep`,
* monitorować system za pomocą `top` i `htop`,
* identyfikować procesy po numerze PID,
* uruchamiać procesy w tle,
* kończyć procesy za pomocą polecenia `kill`.

Zdobyte umiejętności stanowią podstawę administracji systemami Linux.
