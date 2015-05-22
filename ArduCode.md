#include <TinkerKit.h>
// Geeft aan dat input 0-3 knopjes zijn.
TKButton tkButton_I0(I0);
TKButton tkButton_I1(I1);
TKButton tkButton_I2(I2);
TKButton tkButton_I3(I3);

void setup()
{
  // Geeft aan dat output 0-2 digital output zijn.
  pinMode( O0 , OUTPUT);
  pinMode( O1 , OUTPUT);
  pinMode( O2 , OUTPUT);
}

void loop() {

  if (tkButton_I0.get()) { // Checkt knop 1 (duim)
    // Voer 3 andere checks uit als knop 1 is ingedrukt
    
    if (tkButton_I1.get()) { // Checkt knop 2 (wijsvinger)
      digitalWrite( O0 , HIGH ); // Zet lamp 1 aan, als knop 2 is ingedrukt.
    } else {
      digitalWrite( O0 , LOW ); // Zet lamp 1 uit, als knop 2 niet is ingedrukt.
    }
    if (tkButton_I2.get()) { // Checkt knop 3 (middelvinger)
      digitalWrite( O1 , HIGH ); // Zet lamp 2 aan, als knop 3 is ingedrukt.
    } else {
      digitalWrite( O1 , LOW ); // Zet lamp 2 uit, als knop 3 niet is ingedrukt.
    }
    if (tkButton_I3.get()) { // Checkt knop 4 (ringvinger)
      digitalWrite( O2 , HIGH ); // Zet lamp 3 aan, als knop 4 is ingedrukt.
    } else {
      digitalWrite( O2 , LOW ); // Zet lamp 3 uit, als knop 4 niet is ingedrukt.
    }
  } else {
    // Zet alle lampjes uit, als knop 1 niet is ingedrukt.
    digitalWrite( O0 , LOW );
    digitalWrite( O1 , LOW );
    digitalWrite( O2 , LOW );
  }
}

