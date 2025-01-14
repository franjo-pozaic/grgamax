# grgamax
grgamax is a Live granular playground Max/MSP patch designed for live performance of experimental music. It features a polyphonic granular engine which is controlled by a combination of random and manual control. The original purpose is for live performance use with a footcontroller, which makes it suitable for performers that have their hands already busy.

Features
* recording to a single buffer
* parameters
   * grain pitch
   * size
   * spread
   * pitch variation speed
   * buffer position
* 1-click randomization for
   * pitch, pitch variation
   * size, spread and speed
* manual control over
   *   pitch - octave up/down
   *   speed - doubling/halving

## Controlling the patch

This is a description what each footswitch does.

* 1
  - records to the buffer
* 2
   - short  - randomize pitch + pitch variation (if turned on)  
   - long - toggle pitch variation randomization on/off
* 3 
   - short - move buffer position (when turned on)
   - long  - change buffer position modulation type between (linear movement, manual press, onset detection)
* 4
   - short - randomize *grain* trigger period + spread + size
* 5
   - short - activate ground zero patch
* 6
   - short - pitch octave down
* 7
   - short - pitch octave up
* 8
   - short - grain speed / 2
* 9
   - short - grain speed * 2
* 10
   - short - activate saved patch
   - long  - save current patch

## MIDI Controller setup

It's programmed for use with the **Behringer FCB1010** MIDI foot controller, but this can be changed as appropriate.   
All messages are received on channel 1.

The controller is setup as follows:

1 - Toggles MIDI CC messages 0 to 1  
2 - Plays MIDI note 2, velocity not important, must be > 1  
3 - Plays MIDI note 3, velocity not important, must be > 1  
4 - Plays MIDI note 4, velocity not important, must be > 1  
5 - Plays MIDI note 5, velocity not important, must be > 1  
6 - Plays MIDI note 6, velocity not important, must be > 1  
7 - Plays MIDI note 7, velocity not important, must be > 1  
8 - Plays MIDI note 8, velocity not important, must be > 1  
9 - Plays MIDI note 9, velocity not important, must be > 1  
10 - Plays MIDI note 10, velocity not important, must be > 1  

Button 1 functions like a latching switch.  
Other buttons function like a momentary switch. The max patch **fcb1010-note** handles the logic to trigger a bang for each of the buttons. It provides a short and long press functionality, where the long press is triggered by holding more then 500ms. The actual bang is triggered on release, which means that you can time the long press precisely.
