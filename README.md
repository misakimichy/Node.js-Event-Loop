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

You'll see:
- When `process.nextTick()` will be called
- `setTimeout with 0ms` vs `setImmediate`
- Those in polling phase

## eventloop2.js
Run `$ node eventloop2.js` to visualize unordered version of `eventloop.js`

You'll see the exact same result in your terminal.

Now uncomment the blocking loop in line 33 - 37 then run `$ node eventloop2.js`
You'll see:
- `setTimeout` in polling phase is blocked by blocking loop
- the `setTimeout` takes more than 2 seconds after the Timer 3

## Installation

1. Clone the GitHub repo:
   `git clone https://github.com/misakimichy/nodejs-runtime-checker.git`

2. `cd nodejs-runtime-checker`


