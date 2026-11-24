<p align="center"><img src="logo-kmt.png" alt="Grupa KMT" width="260"></p>

# Załączniki do FV – wydania

Program dla rejestracji medycyny pracy. Z zestawienia świadczeń wyeksportowanego z mMedica (plik `.slk`)
tworzy osobny PDF „Załącznik do faktury” dla każdej firmy, a gotowe PDF-y zabezpiecza hasłem (AES-256)
i – na życzenie – przygotowuje w Thunderbirdzie wiadomość do firmy z załącznikiem. Program niczego nie wysyła sam.

To repozytorium zawiera tylko wydania programu (plik exe) i instrukcję. Kodu źródłowego tu nie ma.

## Wymagania

- Windows 10 lub 11
- .NET Framework 4.8 (wbudowany w Windows 10 od wersji 1903 i w Windows 11)
- bez instalatora i bez uprawnień administratora
- do opcji „Szyfruj i wyślij”: Thunderbird

## Pobranie i uruchomienie

1. Wejdź w [Wydania (Releases)](https://github.com/milosz-klement/ZalacznikiFV-wydania/releases/latest)
   i pobierz `ZalacznikiFV.exe`.
2. Zapisz plik w wybranym folderze (np. `Dokumenty\ZalacznikiFV`) albo na udziale sieciowym i uruchom go dwuklikiem.
3. Przy pierwszym uruchomieniu wpisz dane przychodni w **Ustawienia → Wystawca** (pojawiają się w nagłówku PDF), np.:
   „Przychodnia Przykładowa Sp. z o.o.”, „ul. Zmyślona 1”, „00-000 Przykładów”, „NIP 0000000000”.

Nowsze wersje program sprawdza sam (raz na dobę, można to wyłączyć w Ustawieniach) albo z menu „Sprawdź aktualizacje…”.
Pobiera je dopiero po kliknięciu „Zaktualizuj teraz”.

### Ostrzeżenie SmartScreen

Plik exe nie jest podpisany certyfikatem, dlatego przy pierwszym uruchomieniu Windows może pokazać okno
„System Windows ochronił Twój komputer”. Jeśli plik pochodzi z tej strony, kliknij **Więcej informacji → Uruchom mimo to**.

### Suma SHA-256

Każde wydanie ma plik `ZalacznikiFV.exe.sha256` z sumą kontrolną. Sprawdzenie w PowerShell:

```
(Get-FileHash .\ZalacznikiFV.exe -Algorithm SHA256).Hash
```

Wynik musi być taki sam jak zawartość pliku `ZalacznikiFV.exe.sha256` (wielkość liter nie ma znaczenia).
Program przy automatycznej aktualizacji sprawdza tę sumę sam.

## Instrukcja

[Instrukcja_ZalacznikiFV.pdf](https://github.com/milosz-klement/ZalacznikiFV-wydania/blob/main/Instrukcja_ZalacznikiFV.pdf)
– ten sam link otwiera menu „Pomoc (instrukcja)…” w programie.

---

Wszelkie prawa zastrzeżone © 2026 Grupa KMT
