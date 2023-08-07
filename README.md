# ORGAN_ZambroW_TROJCA
ORGAN_ZambroW_TROJCA

Aby projekt działał ma Atmega32A dodałem w Bibliotece enkoder w pliku interupt_pins.h
w folderze C:\Users\Dell\Documents\Arduino\libraries\Encoder\utility
tę sekcję:

// MightyCore (untested)
#elif defined(__AVR_ATmega64__) || defined(__AVR_ATmega32__)
  #define CORE_NUM_INTERRUPT	2
  #define CORE_INT0_PIN		10
  #define CORE_INT1_PIN		11

  Biblioteka enkoder pochodzi ze strony:
  
http://www.pjrc.com/teensy/td_libs_Encoder.html

http://www.youtube.com/watch?v=2puhIong-cs

http://www.pjrc.com/teensy/td_libs_Encoder_1.jpg
