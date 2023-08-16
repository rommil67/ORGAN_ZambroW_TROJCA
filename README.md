# ORGAN_ZambroW_TROJCA
ORGAN_ZambroW_TROJCA
Setzer działa na procesorze Atmega644p. 
Sterowany jest komunikatami midi -NoteOn and -NoteOff.
Wspłpracuje z urządzeniami registrami i płytkami zakupionymi w sklepie Paush-e.de.
Aktualny kod obsługuje 40 registrów, i 256x8 (256 banków po 8 kombinnacji) zapisanych na karcie mikroSD.

NoteOn w zakresie od 36 (C) do 75 (es2), w ł aczaja i wyłańczają podświetlenie registrów jak i poprzez dekoder włącza elektromagnesy registrowe.

Dalsze komunikaty midiOn  - sterują setzerem:
noteOn 76 do 83 - odpowiednio kombinacja 1 do 8
noteOn 84 (c3) - kasownik czyli zero
noteOn 85 (cis3) -  next czyli >
noteOn 86 (d3)  - prev czyli <
noteOn 87 (es3) SET (naciśniecie) noteOff 87 zwolnienie przycisku SET
noteOn 88 (e3) - włącza crescendo (sterowane potenciometrem)
a noteOn89 anuluje (wyłącza) działanie cerscendo i przywraca ostatnio urzywan a kombinację
noteOn od 90 (f3) do 100 mogą być wykożystane do rozbusowy setzera o kolejne registry 

Dwudziesto stopniowe crescendo jest programowane w taki sposób:
Ustawić enkoderem obrotowym Bank nr 1, ustawić registry dla stopnia pierwszego (najcześciej wszystkie wyłączone), i nacisnąć przycisk SET (S) i Crescendo (C).
Natępnie zmienić pokrętłem enkodera Bank nr 2 i ustawić registry dla stopnia drugiego. i znów nacisnąć przycisk SET (S) i Crescendo (C). 
Postępować tak kolejno dla 20 stopni, stopień dwudziesty powinien mieć włączonych najwięcej registrów (prawie wszystkie).
Po zaprogramowaniu wszystkich 20 stopni crescendo nacisnąć Anuluj Crescendo (A) - ustawienie organów wróci do ostatnio używanej kombinacji.  

Aby projekt mógł działać (testowane) ma Atmega32A dodałem w Bibliotece enkoder w pliku interupt_pins.h
w folderze C:\Users\Dell\Documents\Arduino\libraries\Encoder\utility
tę sekcję:


// MightyCore (untested)
#elif defined(__AVR_ATmega64__) || defined(__AVR_ATmega32__)
  #define CORE_NUM_INTERRUPT	2
  #define CORE_INT0_PIN		10
  #define CORE_INT1_PIN		11

  Biblioteka enkoder pochodzi ze strony:
  https://github.com/PaulStoffregen/Encoder
  
http://www.pjrc.com/teensy/td_libs_Encoder.html

http://www.youtube.com/watch?v=2puhIong-cs

http://www.pjrc.com/teensy/td_libs_Encoder_1.jpg
