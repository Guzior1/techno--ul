# Techno Żul z filmu — Cardputer z Bruce i GitHub

W paczce jest gotowa zapętlona animacja ASCII z 226 klatek wcześniej
przetworzonego filmu (nie trzeba instalować Pythona na komputerze z Windows).
Zatrzymujesz animację: `Ctrl+C`.

## WARIANT A — GitHub + Cardputer Bruce (internet, bez własnego serwera)

1. Na GitHubie utwórz **publiczne** repozytorium `techno-zul`.
2. Prześlij `techno_zul_ascii.cmd` do głównego katalogu gałęzi `main`.
3. Otwórz `bruce_github.txt` i podmień **TWOJ_LOGIN** na swój login GitHub.
   Dokładny adres pliku będzie wyglądał tak:
   `https://raw.githubusercontent.com/TWOJ_LOGIN/techno-zul/main/techno_zul_ascii.cmd`
   Możesz go sprawdzić w przeglądarce albo skopiować z przycisku **Raw** na GitHubie.
4. Umieść `bruce_github.txt` na karcie microSD Cardputera. W Bruce uruchom
   `BadUSB` i wybierz ten plik z menu (lokalizacja zależy od wersji Bruce).
5. Po podłączeniu Cardputera do własnego komputera Windows, Bruce otworzy CMD,
   pobierze plik do `%TEMP%` przez `curl.exe` i uruchomi animację.

Ten wariant **nie wymaga** Cloudflare, Pythona, GitHub Pages ani serwera
włączonego w domu. Wymaga dostępu do `raw.githubusercontent.com`.

## WARIANT B — całkowicie offline z microSD Cardputera

1. Skopiuj na kartę microSD oba pliki: `techno_zul_ascii.cmd` i `bruce_offline.txt`.
2. W Bruce wybierz **Files > Mass Storage**. Podłącz urządzenie przez USB;
   Windows zobaczy pamięć Cardputera jako dysk (w obsługiwanej wersji Bruce).
3. Na **własnym komputerze** utwórz folder `C:\Techno` i skopiuj do niego
   plik `techno_zul_ascii.cmd` z widocznego dysku USB.
4. Bezpiecznie zakończ tryb Mass Storage na Cardputerze, następnie wybierz
   **BadUSB** i uruchom `bruce_offline.txt`.
5. CMD otworzy już skopiowany plik z lokalnego dysku; internet nie jest potrzebny.

UWAGA: Zwykły Bruce dokumentuje Mass Storage i BadUSB jako osobne funkcje.
Nie zakładaj, że możesz jednocześnie wystawić dysk USB i wysyłać klawisze
HID w tej samej chwili. Dlatego tu jest **kopiowanie najpierw**, a BadUSB później.

## Ważne

* Windows 10 i 11 mają zwykle `curl.exe`, a animacja korzysta z wbudowanego
  PowerShell. Nie potrzebujesz FFmpeg ani Python na komputerze docelowym.
* `techno_zul_ascii.cmd` to plik wykonywalny. Obejrzyj jego treść i uruchamiaj
  go jedynie na swoim urządzeniu lub za zgodą właściciela.
* Plik nie jest prawdziwym serwerem `ascii.live`: GitHub przechowuje
  **plik animacji**, który lokalny komputer odtwarza po pobraniu.
* Jeśli masz inny układ klawiatury w Bruce, sprawdź poprawne wpisywanie znaków
  `\`, `:` i `"` w CMD — DuckyScript używa układu z ustawień HID.

Dokumentacja Bruce:
https://wiki.bruce.computer/features/others/
https://wiki.bruce.computer/features/files/
