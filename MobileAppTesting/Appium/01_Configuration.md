# Konfiguracja środowiska MacOs + Python + Appium

Aby stworzyć pierwszy test w środowisku MacOS z użyciem Pythona i Appium, wykonaj następujące kroki:

1. **Instalacja Homebrew**: Homebrew to menedżer pakietów dla macOS, który ułatwia instalację różnych narzędzi. Otwórz terminal i wpisz:
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Instalacja Pythona**: Użyj Homebrew, aby zainstalować Pythona wpisując w terminalu:
   ```
   brew install python
   ```

3. **Instalacja Java SDK**: Java jest wymagana przez Android SDK. Możesz zainstalować OpenJDK za pomocą Homebrew:
   ```
   brew install openjdk@11
   ```

4. **Instalacja Android SDK**: Jeśli chcesz testować aplikacje Android, potrzebujesz Android SDK. Zainstaluj je za pomocą Homebrew:
   ```
   brew install --cask android-sdk
   ```

5. **Instalacja Xcode**: Jeśli chcesz testować aplikacje iOS, musisz zainstalować Xcode. Możesz to zrobić przez App Store lub używając polecenia:
   ```
   xcode-select --install
   ```

6. **Instalacja Node.js**: Appium działa na platformie Node.js. Zainstaluj go za pomocą Homebrew:
   ```
   brew install node
   ```

7. **Instalacja Appium**: Teraz kiedy masz Node.js, możesz zainstalować Appium za pomocą npm (Node package manager):
   ```
   npm install -g appium
   ```

8. **Instalacja Appium-Python-Client**: Aby korzystać z Appium w Pythonie, potrzebujesz klienta Pythona dla Appium. Zainstaluj go za pomocą pip:
   ```
   pip install Appium-Python-Client
   ```

9. **Konfiguracja zmiennych środowiskowych**: Upewnij się, że ścieżki do JDK i Android SDK są dodane do zmiennej środowiskowej PATH. Możesz to zrobić edytując plik `~/.zshrc` lub `~/.bash_profile` w zależności od używanego terminala.

10. **Uruchomienie serwera Appium**: W terminalu wpisz:
    ```
    appium
    ```
    Pozostaw ten terminal otwarty, gdyż serwer Appium musi być uruchomiony podczas testowania.

Szczegóły konfiguracji mogą się różnić w zależności od wersji narzędzi i specyfiki projektu. Zalecam również zapoznanie się z dokumentacją Appium i Appium-Python-Client dla bardziej zaawansowanych scenariuszy testowych.