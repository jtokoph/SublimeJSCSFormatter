[SublimeJSCSFormatter](https://github.com/TheSavior/SublimeJSCSFormatter) for Sublime Text 3
=================

Sublime Text 3 Plugin to autoformat your javascript code according to the JSCS configuration files you already have.


## Installation

### Linter installation
JSCS (with autoformatting) must be installed on your system before this plugin will work. To install `jscs`, do the following:

1. Install [Node.js](http://nodejs.org) (and [npm](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager) on Linux).

1. Install `jscs` by typing the following in a terminal:
   ```
   npm install -g jscs
   ```

1. If you are using `nvm` and `zsh`, ensure that the line to load `nvm` is in `.zshenv` and not `.zshrc`.

1. If you are using `zsh` and `oh-my-zsh`, do not load the `nvm` plugin for `oh-my-zsh`.

### Plugin installation

Please use [Package Control](https://sublime.wbond.net/installation) to install the linter plugin. This will ensure that the plugin will be updated when new versions are available. If you want to install from source so you can modify the source code, you probably know what you are doing so we won’t cover that here.

To install via Package Control, do the following:

1. Within Sublime Text, bring up the [Command Palette](http://docs.sublimetext.info/en/sublime-text-3/extensibility/command_palette.html) and type `install`. Among the commands you should see `Package Control: Install Package`. If that command is not highlighted, use the keyboard or mouse to select it. There will be a pause of a few seconds while Package Control fetches the list of available plugins.

1. When the plugin list appears, type `jscs format`. Among the entries you should see `JSCSFormatter`. If that entry is not highlighted, use the keyboard or mouse to select it.


## Commands
**Command palette:**

- JSCSFormatter: Format this file

**Shortcut key:**

* Linux/Windows: [Ctrl + Shift + H]
* Mac: [Cmd + Shift + H]

## Settings

By default, JSCSFormatter will supply the following settings:

```javascript
{
  // The Nodejs installation path
  "node_path": {
    "windows": "node.exe",
    "linux": "/usr/bin/nodejs",
    "osx": "/usr/local/bin/node"
  },

  // The location of the the globally installed jscs package
  "jscs_path": {
    "windows": "%APPDATA%/npm/node_modules/jscs/bin/jscs",
    "linux": "/usr/bin/jscs",
    "osx": "/usr/local/bin/jscs"
  },

  // Specify this path to a JSCS config file to override the default behavior.
  // Passed to JSCS as --config. Read more here:
  // http://jscs.info/overview.html#-config-
  "config_path": "",

  // Automatically format when a file is saved.
  "format_on_save": false,

  // Only attempt to format files whitelisted extensions on save.
  // Leave empty to disable the check
  "format_on_save_extensions": [
    "js",
    "jsx",
    "es",
    "es6",
    "babel",
    "flow"
  ]
}
```

* Modify any settings within the `Preferences -> Package Settings -> JSCS Formatter -> Settings - User` file.

**Project-specific settings override**

To override global plugin configuration for a specific project, add a settings object with a `JSCS-Formatter` key in your `.sublime-project`. This file is accessible via `Project -> Edit Project`.

For example:

```
{
  "folders": [
    {
      "path": "."
    }
  ],
  "settings": {
    "JSCS-Formatter": {
      "format_on_save": true
    }
  }
}
```

## Contributing

If you find any bugs feel free to report them [here](https://github.com/TheSavior/SublimeJSCSFormatter/issues).

Pull requests are also encouraged.
