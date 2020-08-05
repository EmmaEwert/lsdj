.. _commands:

Commands
========

Press ``A`` + ``LEFT``/``RIGHT`` to cycle through commands.
Tap ``A``, ``A`` on a command letter to show help text. ``SELECT`` pauses help text.



A -- Table Start/Stop
---------------------
Start (``00``--``1F``) or stop (``20``) table in current channel.



B -- Maybe
----------
Phrases -- Maybe play note
`````````````````````````````
=========== ==========
First digit Probability (``0``--``F``) for left kit.
Last digit  Probability (``0``--``F``) for note/right kit.
=========== ==========

Tables -- Maybe hop
``````````````````````
=========== ==========
First digit Probability (``0``--``F``) for hop.
Last digit  Destination step (``0``--``F``).
=========== ==========



C -- Chord
----------
Pulse and Wave
``````````````
=========== ==========
First digit First arpeggio extended semitone.
Last digit  Second arpeggio extended semitone.
=========== ==========

.. Note:: Slow down using CMD/RATE in instrument screen.
.. Tip:: C47 plays a major chord, C37 plays a minor chord.

Noise
`````
Apply ``S`` command (*Shape*) (``00``--``FF``) every two ticks.



D -- Delay
----------
Delay note by ticks (``00``--``FF``).



E -- Amplitude Envelope
-----------------------
Pulse and Noise
```````````````
=========== ==========
First digit Amplitude (``0``--``F``).
Last digit  Release (``0``--``F``). ``1``--``7`` decreases, ``9``--``F`` increases. ``0`` and ``8`` mean no change.
=========== ==========

Wave
````
Set volume (``00``--``03``).



F -- Wave Frame/Finetune
------------------------
Pulse
`````
=========== ==========
First digit Transpose (``0``--``F``). Pulse 2 only.
Last digit  Finetine (``0``--``F``).
=========== ==========

.. Note:: Pulse 1 detunes downwards. Pulse 2 detunes upwards.

Wave -- Kit
```````````
Set sample position (``00``--``FF``), ``00``--``7F`` steps forward, ``80``--``FF`` steps back.

Wave -- Synth
`````````````
Set wave frame (``00--FF``) relative to current.

.. Tip:: ``F10`` jumps to the next synth.



G -- Groove
-----------
Select groove (``00``--``1F``).



H -- Hop
--------
Phrases
```````
============== ============
``00``--``0F`` Hop to next phrase at destination step.
First digit    Repeat count (``1``--``F``).
Last digit     Destination step.
``FF``         Stop playing song, or channel in live mode.
============== ============

Tables
``````
=========== ============
First digit Repeat count (``0``--``F``). ``0`` means forever.
Last digit  Destination step.
=========== ============

.. Note:: Loops can be nested.



K -- Kill Note
--------------
Stop sound in channel after ticks (``00``--``FF``).

.. Note:: Causes an audible click. The click can be avoided by using the ``E``-command (Amplitude
	Envelope) instead: ``E00`` for the wave channel, and ``E11`` for the pulse and noise channels.



L -- Slide
----------
Slide to note over time (``00``--``FF``).

========= =========
``PITCH`` Value
========= =========
``TICK``  Ticks
Otherwise :math:`\frac{n}{360}`
========= =========

Tables
``````
Slide to relative note based on transpose column.

.. Note:: Can only be used in left table command column.
.. Note:: Transposes and slides are added together independently.



M -- Master volume
------------------
=========== ==========
First digit Volume (``0``--``F``) of left output.
Last digit  Volume (``0``--``F``) of right output.
=========== ==========

Values ``0``--``7`` are absolute volumes, ``9``--``B`` increases relatively, ``C``--``F`` decreases.
``8`` means no change.



O -- Output
-----------
Pan channel to left, right, none, or both outputs.



P -- Pitch Bend
---------------
Pulse, Wave and Kit
```````````````````
Change pitch over time (``00``--``FF``).

========= =========
``PITCH`` Value
========= =========
``DRUM``  Logarithmic pitch bend at 360 Hz.
``FAST``  Linear pitch bend at 360 Hz.
``TICK``  Pitch bend every tick.
``STEP``  Immediate pitch bend.
========= =========

Noise
`````
Apply ``S`` command (*Shape*) (``00``--``FF``) every tick.



R -- Retrig/Resync
------------------
Play last played note.

=========== =========
First digit Modulate pulse/noise volume (``0``--``F``).
Last digit  Retrigger rate (``0``--``F``). ``1`` fastest, ``F`` slowest. ``0`` means retrigger once.
=========== =========

Values ``0``--``7`` increase volume, ``9``--``F`` decrease, ``0`` means no change, ``8`` means restart oscillator at 360 Hz.



S -- Sweep/Shape
----------------
Pulse 1
```````
=========== ===========
First digit Time (``0``--``F``).
Last digit  Pitch increase/decrease (``0``-``F``).
=========== ===========

Kit
```
=========== ==========
First digit Modulate loop offset value.
Last digit  Modulate loop length (``0``--``F``)
=========== ==========

Noise
`````
Alter noise shape relatively.



T -- Tempo
----------
Set tempo (``00``--``FF``).

============== =============
Value          Tempo
============== =============
``28``--``FF`` 40--255 BPM.
``00``--``27`` 256--295 BPM.
============== =============

.. Note:: If the groove has a different number of ticks per note step than 6, the value should be
	adjusted according to :math:`\frac{DesiredBPM \times TicksPerStep}{6}`.



V -- Vibrato
------------
Add vibrato.

=========== ===========
First digit Speed (``0``--``F``).
Last digit  Depth (``0``--``F``).
=========== ===========

===== =========
Depth Semitones
===== =========
``0`` 0.125
``1`` 0.25
``2`` 0.375
``3`` 0.5
``4`` 0.75
``5`` 1
``6`` 1.5
``7`` 2
``8`` 2.5
``9`` 3
``A`` 3.5
``B`` 4
``C`` 5
``D`` 6
``E`` 7
``F`` 8
===== =========



W -- Wave
---------
Pulse
`````
Change duty cycle/wave; 12.5 %, 25 %, 50 %, or 75 %.

.. Note:: Due to a hardware oddity, the instrument ``LENGTH`` timer is reset, possibly extending the
	duration of the sound.

Wave
````
=========== ===========
First digit Synth sound speed (``0``--``F``)
Last digit  Synth sound length
=========== ===========

.. Note:: Synth restarts if length is changed.



Z -- Randomize
--------------
Repeat and add random number (``00``--``FF``) to last non-``H``, non-``Z`` command; each digit
controls the maximum added value for that digit.
