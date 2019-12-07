# Virtual runtimes

Currently, JSBox provides two runtimes, the `JSBox runtime`, and the `Node.js runtime`, it also supports bi-directional communications between two runtimes.

This mechanism can benefit a lot when one runtime has some weakness:

- JSBox script can use Node modules
- Node script can leverage the UI power of JSBox script
- Node script can call Objective-C runtime with JSBox script

It's something similar to executing JavaScript on a WebView in JSBox, we implemented it based on message sending and observing.