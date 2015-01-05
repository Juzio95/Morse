Morse
=====

Hello KMI
Cześć wszystkim
	Z tej strony Michał, Patryk i Filip. Jesteśmy nowymi członkami Koła Młodych Informatyków. Jesteśmy studentami automatyki i robotyki, którzy w tym semestrze rozpoczęli swoją przygodę ze studiami na wydziale EEIA.
 	Jako nasz powitalny projekt dostaliśmy za zadanie napisanie programu w okresie przerwy świątecznej, który będzie za pomocą  diody w Intel Galileo przetwarzał litery alfaberu na kod Morse'a. Jako, iż jesteśmy laikami jak na razie, dlatego zastanawialiśmy się początkowo jak za pomocą metody prób i błędów udałoby nam się osiągnąć zamierzony efekt. Pierwsze problemy polegały na odczycie kodu Morse'a z sygnału świetlnego. Idąc na przeciw problemom postanowiliśmy zastąpić sygnał świetlny z LED'a na sygnał dźwiękowy, który jest odtwarzany poprzez PC buzzer. Do jego odczytu wykorzystaliśmy aplikację na system android o nazwie "Morse Code Reader". Pierwotnie próbowaliśmy stworzyć słowo "HELLO KMI" wykorzystując funkcję pętli. która realizowała sygnał jako kropka-kreska. Kod wyglądał wtedy tak:


	Pomimo, że program już działał i bez problemu mógł wysyłać informację w kodzie Morse'a był ograniczony prymitywnością. Jeśli ktoś chciałby zmienić przesyłane słowo należałoby napisać całą pętlę od nowa korzystając przy tym ze znajomości kodu Morse'a. Wtedy wpadliśmy na następny pomysł. A co gdyby uprościć program w taki sposób, by wysyłający sygnał nie musiał mieć żadnej wiedzy na temat kodu Morse'a i mógł zmienić wysyłane słowo zmieniając jedynie jedną linijkę kodu? W tym celu postanowiliśmy wykonać funkcję dla każdej litery alfabetu przypisując jej odpowiadającą jej kombinację kropek i kresek. Od tego momentu aby wysłać ciąg liter wystarczy z funkcji pętli wypisać ciąg liter na które składa się wyraz i oddzielić je funkcją delay(1000), 1 sekunda wystarczy aby Morse Code Reader przyjął, że wysyłany jest już następny wyraz. Jedynym ograniczeniem w tym momencie był sprzęt odczytujący ten sygnał czyli jakość mikrofonu z telefonie. Aby program jeszcze lepiej rozróżniał wyrazy postanowiliśmy wykorzystać bibliotekę "pitches.h" z środowiska Arduino. Od tego momentu przy każdej następnej literze w wyrazie należy przypisać po kolei inną na zmianę częstotliwość (nutki z pitches.h zdefiniowane jako a i b). W praktyce wygląda to tak, że każda następna litera, a więc odpowiadający jej ciąg kropek i kresek ma raz wysoką a raz niską częstotliwość. Kod wygląda tak:



Tutaj film prezentujący działanie układu oraz program Morse Code Reader odczytujący sygnał:
