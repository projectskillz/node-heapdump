node-heapdump
===

Make a dump of the V8 heap for later inspection.

### Install

    npm install heapdump

### Build

    node-gyp configure build

### Usage

Load the add-on in your application:

    require('heapdump');

The module does not export any properties. Now send the node process a SIGUSR2
signal:

    $ kill -USR2 <pid>

A heapdump-xxxx.xxxx.heapsnapshot is written to the application's current
directory.

Open [Google Chrome](https://www.google.com/intl/en/chrome/browser/) and press
F12 to open the developer toolbar. Go to the `Profiles` tab, right-click in the
tab pane and select `Load profile...`. Select the dump file and click `Open`.
You can now inspect the heap snapshot at your leisure.
