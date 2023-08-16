# ORGAN_ZambroW_TROJCA
SETZER 
The setter runs on the Atmega644p processor. The controlled now communicates midi -NoteOn and -NoteOff. It works with individual registers and indicator analyzes in the Paush-e.de store. The current number is 40 registers, and 256x8 (256 banks for 8 combinations) saved for the provision of microSD.

Note In the range from 36 (C) to 75 (es2), they turn the register backlight on and off, and turn on the register solenoids via the decoder.

Further midiOn messages - control the setzer: noteOn 76 to 83 - respectively 1 to 8 noteOn 84 (c3) - eraser i.e. zero noteOn 85 (cis3) - next i.e. > noteOn 86 (d3) - prev i.e. < noteOn 87 (es3) SET (press) noteOff 87 release SET station noteOn 88 (e3) - enable crescendo (potentiometer controlled) and noteOn89 cancels (disables) cerscendo and returns the last used combination noteOn from 90 (f3) to 1 00 can be used to boot the setzler at then register

The 20-step crescendo is programmed as follows: Set the rotary encoder to Bank #1, set the register for step one (usually all signals), and press the SET (S) and Crescendo (C) buttons. Then turn the encoder knob to Bank #2 and set the register for the step. and again uses the SET (S) and Crescendo (C) buttons. Proceed so early for 20 degrees, the twentieth degree should have above records (almost all). The day after tomorrow all 20 degrees crescendo suddenly Cancel Crescendo (A) - device setting is back to last trip.


For the project to work (tested) it has Atmega32A I added in the Library the encoder in the file interrupt_pins.h in the folder C:\Users\Dell\Documents\Arduino\libraries\Encoder\utility this section:

// MightyCore (untested) #elif defined(AVR_ATmega64) || defined (AVR_ATmega32) # define CORE_NUM_INTERRUPT 2 # define CORE_INT0_PIN 10 # define CORE_INT1_PIN 11

The encoder library comes from: https://github.com/PaulStoffregen/Encoder

http://www.pjrc.com/teensy/td_libs_Encoder.html

http://www.youtube.com/watch?v=2puhLong-cs

http://www.pjrc.com/teensy/td_libs_Encoder_1.jpg


*************************** tłumaczenie na język polski*****************************
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

Przyciski next (>) oraz prev (<) służą do zmiany kombinacji na kolejną do przodu i do tyłu. Next diała tak, że po 8 kombinacji następuje pierwsza kombinacja następnego banku. podobnie prev ale w odwrotnym kierunku.
Nacisniecie SET i jednego z powyżej opisanych przycisków zmienia Bank na kolejny, pozostawiając ten sam nr kombinacji.
kręcenie enkoderem umożliwia szybką zmianę banku na dalsze pozycje, lecz nowa kombinacja włączy się dopiero po nacisniećiu przycisko kombinacji 1 do 8.
Naciśniecie przycisku SET i jednego z ośmiu  przycxisków kombinacji powoduje zapisanie aktualnego ustawienia registrów do danej kombinacji w aktoalnioe wyświetlonym banku. 

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
