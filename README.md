# karma-electron-launcher

> Launcher for electron.

---

Small and experimental launcher based on [Karma Nodewebkit Launcher](https://raw.githubusercontent.com/intelligentgolf/karma-nodewebkit-launcher). Is not official nor super tested and it follows the "it works for me"(tm) philosophy.

---

## Installation

The easiest way is to keep `karma-electron-launcher` as a devDependency in your `package.json`.


    {
      "devDependencies": {
        "karma": "~0.10",
        "karma-electron-launcher": "~0.0.3"
      }
    }


You can do it on the command line by:

    npm install karma-electron-launcher --save-dev

## Configuration

    // karma.conf.js
    module.exports = function(config) {
      config.set({
        browsers: ['Electron']
      });
    };


You can pass list of browsers as a CLI argument too:

    karma start --browsers Electron

## Locally-installed Node modules

If you're using locally-installed Node modules via `require` in your code in the `node_modules` directory, you should be able to just `require` them, and they should be found by the testing environment.

## Configuring the Electron BrowserWindow

Options passed to the `new BrowserWindow()` constructor can be defined by adding an `electronOpts` object to your karma config. Eg.

    // karma.conf.js
    module.exports = function(config) {
      config.set({
        browsers: ['Electron'],
        electronOpts: {
          title: 'my window title',
          // ...
        }
      });
    };

Available options are specified 
[in the Electron docs](https://github.com/atom/electron/blob/master/docs/api/browser-window.md#new-browserwindowoptions). By default, only the window dimensions (400x300) are set.
