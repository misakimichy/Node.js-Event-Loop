# Node.js Event Loop
Six Phases of The Event Loop
Phase 1: -Timers- - executes callbacks using timers.
Phase 2: -Pending- - internal phase
Phase 3: -Idle/Prepare - internal phase
Phase 4: -Poll- - process input/output callbacks
Phase 5: -Check- - execute any `setImmediate` timers added in the Poll phase.
Phase 6: -Close- - the loop closes and the process ends when all timers and input/output calls are done. Until then, loop continues.

### Polling Phase
- if there are no tiers left to execute when the polling phase is reached, the poll phase will wait for I/O callbacks.
- if the I/O contains synchronous code, this code will not be added to the call stack till the polling phase is reached.
- if `setImmediate` is reached, the polling phase will end and the check phase will begin.
- if `setImmediate` is not called, the polling phase will continue to wait for a bit, then move on through the next phase to execute additional timers and so forth.

## eventloop.js
Run`$ node eventloop.js` to visualize Event Loop.

You'll know:
- When `process.nextTick()` will be called
- 


## Installation

1. Clone the GitHub repo:
   `git clone https://github.com/misakimichy/nodejs-runtime-checker.git`

2. `cd nodejs-runtime-checker`

3.

