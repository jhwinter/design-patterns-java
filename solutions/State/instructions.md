# Media Player Application Exercise

You are designing a Media Player Application that allows users to play, pause, and stop audio tracks. The media player transitions between different states (e.g., Playing, Paused, Stopped), and each state dictates how the player behaves when the user interacts with the play, pause, or stop buttons.

For example:

* In the Playing state, pressing the pause button will pause the track, while pressing the stop button will stop it.
* In the Paused state, pressing the play button will resume the track, and pressing the stop button will stop it.
* In the Stopped state, pressing the play button will start the track from the beginning.

**Task**:

Implement the Media Player using the State Design Pattern. Ensure that each state (Playing, Paused, Stopped) is handled by a separate class, and that transitioning between states is done without modifying the behavior of the individual states. Your implementation should allow for easy extension in the future, where more states (e.g., Fast-Forward, Rewind) can be added.

**Output**:

After executing the code, it will simulate the following sequence of state transitions:

1. Start playing the track.
2. Pause the track.
3. Stop the track.

Each state transition should be clearly reflected in the output, showing how the media player responds to these predefined transitions.

**Instructions**:
* You only need to complete the TODOs mentioned in the code.
* Please do not modify any existing code outside of the specified TODO sections.
