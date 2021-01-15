# NoteHandlerClass

The NoteHandler class was developed throughout the construction of Azure Talos, a multi-string mechatronic chordophone. This class is part of the system's firmware, and is responsible for using incoming MIDI note values to look up the robot arm positions and clamping servomotor values that the guitar robot uses to play each note.

## Using the class:

The class is initialized with two arrays of integer values, one that includes the expected MIDI values, and their corresponding robot arm positions. The class also expects a third argument with the size of the arrays.

`NoteHandler handler(midiNotes, posValues, arraySize)`

The class uses the `applyPos` function to perform actions upon receiving a MIDI note values. It expects two arguments, the first is the incoming MIDI note value, and the second is the callback function to be executed after using the MIDI value to look up the robot arm position or clamping servomotor value.

`handler(note, callback)`

This function is overloaded to use the velocity value of the note if needed>

`handler(note, velocity, callback)`

