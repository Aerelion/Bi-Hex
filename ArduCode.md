#include <TinkerKit.h>

TKButton tkButton_I0(I0);
TKButton tkButton_I1(I1);
TKButton tkButton_I2(I2);
TKButton tkButton_I3(I3);

void setup()
{
  pinMode( O0 , OUTPUT);
  pinMode( O1 , OUTPUT);
  pinMode( O2 , OUTPUT);
}

void loop() {
  if (tkButton_I0.get()) {
    
    if (tkButton_I1.get()) {
      digitalWrite( O0 , HIGH );
    } else {
      digitalWrite( O0 , LOW );
    }
    if (tkButton_I2.get()) {
      digitalWrite( O1 , HIGH );
    } else {
      digitalWrite( O1 , LOW );
    }
    if (tkButton_I3.get()) {
      digitalWrite( O2 , HIGH );
    } else {
      digitalWrite( O2 , LOW );
    }
  } else {
    digitalWrite( O0 , LOW );
    digitalWrite( O1 , LOW );
    digitalWrite( O2 , LOW );
  }
}

