# Simagic Profile Manager (SPM)

**Publiczna beta · Windows · SimHub** · [English](README.md)

Simagic Profile Manager to społecznościowa wtyczka do przechowywania setupów baz SIMAGIC w jednym miejscu. Powstała, żeby szybciej przełączać ustawienia między grami i samochodami: importujesz eksporty z SimPro 2, organizujesz i dostrajasz profile w SimHubie, a następnie przypisujesz je do auta lub klasy, by ładowały się automatycznie. Wtyczkę można obsługiwać w oknie SimHuba, na ekranie dotykowym/DDU, telefonie, tablecie albo przyciskami kierownicy.

To repozytorium służy **wyłącznie do dystrybucji plików i aktualizacji**. Kod źródłowy i system budowania pozostają w prywatnym repo deweloperskim.

## Co potrafi

- Przechowuje edytowalne setupy osobno dla każdej gry; importuje wyeksportowane profile SimPro 2 jako niezależne kopie.
- Automatycznie ładuje przypisany setup, gdy SimHub rozpozna grę, auto lub klasę; pozwala też wybrać go ręcznie.
- Pozwala dostrajać obsługiwane ustawienia bazy dotykiem lub przyciskami.
- Wyświetla Profile Manager na ekranie SimHuba, monitorze, telefonie lub tablecie.
- Oferuje konfigurację pierwszego uruchomienia, kopie zapasowe, raporty błędów i aktualizacje beta weryfikowane sumą SHA-256.

Obsługiwane bazy w tej becie: **SIMAGIC Alpha Mini, Alpha i Alpha Ultimate**. Bazy SIMAGIC EVO **nie są obsługiwane**. Rozpoznawanie gry, auta i klasy zależy od danych udostępnianych przez SimHub.

> [!WARNING]
> To wersja beta, która może zmieniać ustawienia bazy. Przed zastosowaniem sprawdź wartości i zachowaj kopię ważnych setupów. **Zalecamy zamknąć SimPro Manager 2 podczas ładowania lub dostrajania setupów przez SPM**, aby obie aplikacje nie sterowały bazą jednocześnie. SimPro 2 nadal służy do eksportu profili, które później importujesz do SPM.

## Pobieranie

Otwórz [najnowsze wydanie beta](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases). Najprostsza instalacja korzysta z pełnego pakietu `SimagicProfileManager-Setup-<wersja>.zip`. W wydaniu są też osobne DLL i dashboard. Pliki do ręcznego pobrania znajdziesz również w katalogu [`manual/`](manual/).

Aktualne pliki do ręcznej instalacji (`0.1.0-beta.3`):

| Plik | Gdzie trafi |
| --- | --- |
| [`User.SimagicProfileV2.dll`](manual/User.SimagicProfileV2.dll) | Katalog instalacyjny SimHuba |
| [`SimagicProfileV2.Core.dll`](manual/SimagicProfileV2.Core.dll) | Katalog instalacyjny SimHuba |
| [`SimagicProfileV2.Devices.dll`](manual/SimagicProfileV2.Devices.dll) | Katalog instalacyjny SimHuba |
| [`Simagic Profile Manager.simhubdash`](manual/Simagic%20Profile%20Manager.simhubdash) | Import w SimHub Dash Studio; **nie** kopiuj obok DLL |

Używaj plików `manual/` **z tej samej wersji**. Nie mieszaj DLL z różnych wydań.

## Instalacja z pakietu (zalecana)

1. Zainstaluj i uruchom SimHub co najmniej raz, następnie zamknij go całkowicie. Zamknij również SimPro Manager 2.
2. Pobierz ZIP z wydania i rozpakuj do zwykłego folderu. Nie uruchamiaj instalatora wewnątrz ZIP-a.
3. Otwórz PowerShell **jako administrator** w rozpakowanym folderze i uruchom `./Install.ps1` (dla niestandardowej lokalizacji: `./Install.ps1 -SimHubPath 'D:\Twoj\SimHub'`).
4. Uruchom SimHub, otwórz **Simagic Profile Manager** i przejdź przez **First Start Setup**.

Instalator kopiuje trzy DLL i instaluje dashboard. Przed zastąpieniem poprzednich plików SPM robi ich kopię. **Nie usuwa** setupów ani przypisań w `%LOCALAPPDATA%\SimagicProfileManager`.

## Ręczne kopiowanie plików

1. Zamknij SimHub i SimPro Manager 2. Pobierz **wszystkie cztery** pliki z [`manual/`](manual/) przyciskiem **Download raw file** dla każdego pliku albo pobierz odpowiadające im osobne pliki z [Releases](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases).
2. Znajdź folder instalacyjny SimHuba — zwykle `C:\Program Files (x86)\SimHub`, zawierający `SimHubWPF.exe`. Zrób kopię dotychczasowych DLL SPM.
3. Skopiuj **trzy DLL** do tego folderu, obok `SimHubWPF.exe`. Zgódź się na zastąpienie starszych DLL SPM. Windows może poprosić o uprawnienia administratora.
4. Zaimportuj `Simagic Profile Manager.simhubdash` przez SimHub Dash Studio. To pakiet dashboardu, **nie** DLL ani plik do skopiowania do głównego folderu SimHuba.
5. Uruchom ponownie SimHub, otwórz **Simagic Profile Manager** i zakończ First Start Setup.

Przy ręcznej aktualizacji wymień **wszystkie trzy DLL** i ponownie zaimportuj dashboard z tej samej wersji. Dane użytkownika w `%LOCALAPPDATA%\SimagicProfileManager` pozostaną bez zmian.

## Konfiguracja

First Start Setup prowadzi przez wybór obsługi dotykiem, przyciskami lub obiema metodami; mapowanie przycisków (opcjonalnie); wybór ekranu/DDU albo telefonu/tabletu (opcjonalnie); oraz import profili SimPro 2 lub rozpoczęcie z pustą biblioteką. Profile SimPro 2 trzeba najpierw **wyeksportować do plików**, a następnie wskazać je podczas importu. Wybierz też grę docelową.

Później w **Profiles** tworzysz, importujesz i edytujesz setupy, a w **Auto Switch** przypisujesz je do auta lub klasy dla wybranej gry. W **Settings → Display** wybierasz ekran SimHuba albo otrzymujesz adres i kod QR dla telefonu/tabletu. Telefon/tablet i komputer z SimHubem muszą działać w tej samej sieci lokalnej; zapora musi pozwalać na połączenia przychodzące do SimHuba. Konfigurację można powtórzyć przez **Settings → First Start Setup** bez kasowania profili.

## Aktualizacje beta i zgłaszanie błędów

SPM sprawdza publiczny [`update-manifest-beta.json`](update-manifest-beta.json), pobiera pakiet i przed instalacją weryfikuje jego sumę SHA-256. Wersje `0.1.0-beta.1` i `0.1.0-beta.2` wskazują poprzedni, teraz prywatny adres aktualizacji. Aby przejść na nowy kanał, trzeba **jednorazowo ręcznie zainstalować `0.1.0-beta.3`**.

Błędy zgłaszaj przez **Beta Report** we wtyczce. Napisz, co robiłeś, w jakiej grze i aucie, oraz co się stało. Przed publikacją logów lub danych w publicznym zgłoszeniu sprawdź, czy nie zawierają prywatnych informacji. Przywracanie backupu nie jest jeszcze dostępne w interfejsie bety.

Simagic Profile Manager jest niezależnym projektem społecznościowym, niepowiązanym z SIMAGIC ani SimHubem. SIMAGIC i SimHub są znakami towarowymi ich właścicieli.
