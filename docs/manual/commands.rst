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
In phrases -- Maybe play note
`````````````````````````````
=========== ==========
First digit Probability (``0``--``F``) for left kit.
Last digit  Probability (``0``--``F``) for note/right kit.
=========== ==========

In tables -- Maybe hop
``````````````````````
=========== ==========
First digit Probability (``0``--``F``) for hop.
Last digit  Destination row (``0``--``F``).
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
Delay (``00``--``FF``) note by ticks.



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