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
   *   pitch variation - on/off, increasing by 0.25

## Controlling the patch

This is a description what each footswitch does.

* 1/2/3 - sample slots - for recording live
  - short press: trigger sample/copy to granular buffer
  - long press: start recording - short press to stop recording
* 4
   - short press: freeze all params
   - long press: toggle immediate granular buffer switch
* 5  
   - short press: activate random param movement
   - long press: activate init patch params
* 6
   - short - pitch divider / 2 (divided by 2)
* 7
   - short - pitch multiplier * 2 (multiply by 2)
* 8
   - short - advance buffer position - moves through quarters 0/4, 1/4, 2/4, 3/4
   - long - change buffer position modulation type between linear movement, manual press, random movement
* 9
   - short - steps through random pitch variation values from 0.0, 0.25, 0.5, 0.75, 1.0
   - long - toggles random pitch variation on/off - when turned off, the values for pitch and random pitch variation are set to 1 and 0, respectively
* 10
   - short - toggles sample trigger from live audio
   

## MIDI Controller setup

It's programmed for use with the **Behringer FCB1010** MIDI foot controller, but this can be changed as appropriate.   
All messages are received on channel 1.

The controller is setup as follows:

1 - Plays MIDI note 1, velocity not important, must be > 1  
2 - Plays MIDI note 2, velocity not important, must be > 1  
3 - Plays MIDI note 3, velocity not important, must be > 1  
4 - Plays MIDI note 4, velocity not important, must be > 1  
5 - Plays MIDI note 5, velocity not important, must be > 1  
6 - Plays MIDI note 6, velocity not important, must be > 1  
7 - Plays MIDI note 78, velocity not important, must be > 1  
8 - Plays MIDI note 8, velocity not important, must be > 1  
9 - Plays MIDI note 9, velocity not important, must be > 1  
10 - Plays MIDI note 10, velocity not important, must be > 1  

Buttons function like a momentary switch. The max patch **fcb1010-note** handles the logic to trigger a bang for each of the buttons. It provides a short and long press functionality, where the long press is triggered by holding more then 500ms. The actual bang is triggered on release, which means that you can time the long press precisely.
