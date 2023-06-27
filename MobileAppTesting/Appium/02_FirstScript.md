
### Krok 1: Uruchomienie emulatora Androida
1. Upewnij się, że masz zainstalowane Android Studio i Android Emulator (automatycznie powinien zainstalować się wraz z Android Studio).
2. Otwórz Android Studio.
3. Przejdź do "Tools" > "Device Manager".
4. Kliknij "Create Device" jeśli nie masz już skonfigurowanego emulatora lub kliknij trójkąt (play button) obok nazwy emulatora, aby uruchomić istniejący emulator.

![Device Manger](MobileAppTesting/Appium/images/AndroidStudio_DeviceManager.png)


Alternatywnie, możesz uruchomić emulator z wiersza poleceń:
```sh
emulator -avd NAZWA_TWOJEGO_EMULATORA
```
Należy zastąpić `NAZWA_TWOJEGO_EMULATORA` nazwą Twojego emulatora, którą można znaleźć w AVD Manager.

### Krok 2: Uruchomienie serwera Appium z dodatkową flagą
Uruchom serwer Appium z wiersza poleceń z flagą `--allow-insecure`, która pozwala na niestandardowe ustawienia bezpieczeństwa potrzebne do automatycznego pobierania Chromedrivera.
```sh
appium --allow-insecure=chromedriver_autodownload
```

### Krok 3: Uruchomienie skryptu testowego
Przygotuj skrypt testowy w Pythonie, który używa Appium do wykonania testów na uruchomionym emulatorze. Poniżej znajduje się przykładowy skrypt:

```python
from appium import webdriver

desired_caps = {
    'platformName': 'Android',
    'deviceName': 'emulator-5554', # Tu powinieneś wpisać nazwę swojego urządzenia/emulatora
    'browserName': 'Chrome',
    'chromedriverAutodownload': True,
}

print ('Running webdriver...')
driver = webdriver.Remote('http://localhost:4723/wd/hub', desired_caps)

print ('Open page')
# Otwórz stronę google.com
driver.get('https://www.google.com')

print ('Search word') #If you are using a Web browser for the first time, you will need to add a step to accept a policy.
search_box = driver.find_element_by_name('q')
search_box.send_keys('TestSpring Appium')


driver.quit()
```

Następnie uruchom skrypt:
```sh
python NAZWA_TWOJEGO_SKRYPTU.py
```

lub dla najnowszej wersji Pythona
```sh
python3 NAZWA_TWOJEGO_SKRYPTU.py
```

Należy zastąpić `NAZWA_TWOJEGO_SKRYPTU` nazwą pliku skryptu, który chcesz uruchomić.
