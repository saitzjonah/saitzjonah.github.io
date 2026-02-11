---
layout: single
title: 7-Segment Display Valentine
permalink: /arduino-projects/valentine
author_profile: true
classes: wide
header:
  overlay_image: /assets/arduino.jpeg
  teaser: /assets/arduino.jpeg
date: 2026-02-14
---
### Materials 
* Arduino Uno R3 (or comparable)
* Breadboard
* 8 x 1kΩ resistors
* 12 jumper wires (male-male)

### Video
<details>
<summary><strong>Show video</strong></summary>

<video controls width="600">
    <source src="arduino-valentine.mp4" type="video/mp4">
    
    <!-- Optional: Add a fallback for older browsers -->
    Your browser does not support the video tag.
</video>
<br>
</details>
<a href="arduino-valentine.mp4" download>Download video</a>

### Code
<details>
<summary><strong>Show code</strong></summary>

<pre><code>
  // 4 x 7 segment display pinout
  //  1 - E
  //  2 - D
  //  3 - .
  //  4 - C
  //  5 - G
  //  6 - digit 4 (rightmost)
  //  7 - B
  //  8 - digit 3
  //  9 - digit 2
  //  10 - F
  //  11 - A
  //  12 - digit 1 (leftmost)

  // Define segment pins
  // Arduino D0 / D1 used for RX / TX
  // Arduino pins correspond to pinout + 1
  const int segmentPins[] = {2, 3, 4, 5, 6, 8, 11, 12};

  int scrollPos = 0;

  // digit pins listed in reverse order
  const int digitPins[] = {13, 10, 9, 7};

  const int message[18][8] = {
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {1, 0, 0, 1, 1, 1, 1, 0}, // H,
    {1, 0, 0, 1, 1, 1, 1, 1}, // A, 
    {1, 0, 0, 0, 1, 1, 1, 1}, // P, 
    {1, 0, 0, 0, 1, 1, 1, 1}, // P, 
    {0, 1, 0, 1, 1, 1, 1, 0}, // Y,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {1, 1, 0, 1, 0, 1, 1, 0}, // V, 
    {0, 0, 0, 0, 1, 0, 0, 0}, // -,
    {1, 1, 0, 1, 0, 1, 1, 1}, // D,
    {1, 0, 0, 1, 1, 1, 1, 1}, // A,
    {0, 1, 0, 1, 1, 1, 1, 0}, // Y,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    // {0, 0, 0, 1, 0, 1, 0, 0}, // I,
    // {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    // {1, 1, 0, 0, 0, 0, 1, 0}, // L,
    // {1, 1, 0, 1, 0, 1, 1, 1}, // 0, 
    // {1, 1, 0, 1, 0, 1, 1, 0}, // V,
    // {1, 1, 0, 0, 1, 0, 1, 1}, // E,
    // {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    // {0, 1, 0, 1, 1, 1, 1, 0}, // Y,
    // {1, 1, 0, 1, 0, 1, 1, 1}, // 0,
    // {1, 1, 0, 1, 0, 1, 1, 0}, // U,
    // {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
    {0, 0, 0, 0, 0, 0, 0, 0}, // SPACE,
  };

  void setup() {
    // Set segment pins as output
    for (int s = 0; s < 8; s++) pinMode(segmentPins[s], OUTPUT);
    // Set digit pins as output
    for (int d = 0; d < 4; d++) pinMode(digitPins[d], OUTPUT);
  }

  void loop() {
    // Scroll continuously, with wrap around
    if (scrollPos > 14) scrollPos = 0;
    for (int d = 0; d < 4; d++) {
      // Turn off all digit pins to prevent ghosting
      // Common cathode: HIGH = off
      for (int n = 0; n < 4; n++) digitalWrite(digitPins[n], HIGH);
      for (int pwm = 0; pwm < 32; pwm++){
        for (int s = 0; s < 8; s++){
          digitalWrite(segmentPins[s], message[scrollPos + d][s] ? HIGH : LOW);
        }
        digitalWrite(digitPins[d], LOW);
        delayMicroseconds(10);
      }
    }
      static unsigned long lastScroll = 0;
      // returns time since program started running
      unsigned long now = millis();
      if (now - lastScroll > 500){
        scrollPos += 1;
        lastScroll = now;
      }
  }
</code></pre>
</details>
<a href="seven-segment-four.ino" download>Download code</a>

### Resources
* [7-segment display datasheet (5641AS)](datasheet-5641as.pdf)
* [How to Use a 7-Segment Display with Arduino (arduinointro.com)](https://arduinointro.com/articles/projects/how-to-use-a-7-segment-display-with-arduino-a-complete-beginners-guide)