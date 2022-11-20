Mycodo to open-source'owy system monitorowania i regulacji środowiska, który został zbudowany do działania na komputerach jednopłytkowych, a konkretnie na [Raspberry Pi](https://en.wikipedia.org/wiki/Raspberry_Pi).

Pierwotnie opracowany do uprawy grzybów jadalnych, Mycodo rozwinął się do znacznie większych możliwości. System składa się z dwóch części, backendu (demona) i frontu (serwera internetowego). Backend wykonuje takie zadania, jak pobieranie pomiarów z czujników i urządzeń oraz koordynacja różnorodnych reakcji na te pomiary, w tym możliwość modulowania wyjść (przełączanie przekaźników, generowanie sygnałów PWM, obsługa pomp, przełączanie gniazdek bezprzewodowych, publikowanie/podpisywanie się do MQTT, między innymi), regulowanie warunków środowiskowych za pomocą kontroli PID, harmonogramy, przechwytywanie zdjęć i strumieniowanie wideo, wyzwalanie działań, gdy pomiary spełniają określone warunki, i wiele innych. Frontend hostuje interfejs webowy, który umożliwia podgląd i konfigurację z dowolnego urządzenia obsługującego przeglądarkę.

Istnieje wiele różnych zastosowań dla Mycodo. Niektórzy użytkownicy po prostu przechowują pomiary czujników, aby zdalnie monitorować warunki, inni regulują warunki środowiskowe w przestrzeni fizycznej, a jeszcze inni rejestrują fotografię aktywowaną ruchem lub poklatkową, wśród innych zastosowań.

Kontrolery wejściowe pozyskują pomiary i przechowują je w bazie danych serii czasowych InfluxDB. Pomiary pochodzą zazwyczaj z czujników, ale mogą być również skonfigurowane tak, aby używać wartości zwrotnej poleceń Linux Bash lub Python, lub równań matematycznych, co sprawia, że jest to bardzo dynamiczny system pozyskiwania i generowania danych.

Kontrolery wyjść wytwarzają zmiany na pinach ogólnego wejścia/wyjścia (GPIO) lub mogą być skonfigurowane do wykonywania poleceń Linux Bash lub Python, umożliwiając wiele potencjalnych zastosowań. Istnieje kilka różnych typów wyjść: proste przełączanie pinów GPIO (HIGH/LOW), generowanie sygnałów modulowanych w szerokości impulsu (PWM), sterowanie pompami perystaltycznymi, publikowanie MQTT i inne.

Gdy wejścia i wyjścia są połączone, sterowniki funkcyjne mogą być używane do tworzenia pętli sprzężenia zwrotnego, które wykorzystuje urządzenie wyjściowe do modulowania warunków środowiskowych mierzonych przez wejście. Niektóre wejścia mogą być połączone z niektórymi wyjściami, aby stworzyć wiele różnych zastosowań w zakresie sterowania i regulacji. Poza prostą regulacją, Metody mogą być używane do tworzenia zmieniających się w czasie wartości zadanych, umożliwiając takie rzeczy jak termocyklery, piece rozpływowe, symulację środowiska dla terrariów, fermentację żywności i napojów lub utwardzanie, oraz gotowanie żywności ([sous-vide](https://en.wikipedia.org/wiki/Sous-vide)), aby wymienić tylko kilka.

Wyzwalacze można ustawić tak, aby aktywowały zdarzenia w oparciu o określone daty i godziny, według czasu trwania lub wschodu/zachodu słońca na określonej szerokości i długości geograficznej.

Mycodo zostało przetłumaczone na kilka języków. Domyślnie język przeglądarki określa, który język jest używany, ale może być nadpisany w ustawieniach ogólnych, na stronie `[Gear Icon] -> Configure -> General`. Jeśli znajdziesz jakiś problem i chciałbyś poprawić tłumaczenie lub chciałbyś dodać kolejny język, można to zrobić na stronie [https://translate.kylegabriel.com](http://translate.kylegabriel.com:8080/engage/mycodo/).