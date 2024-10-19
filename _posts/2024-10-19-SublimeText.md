---
author: clausmalver
Title: Sublime Text
description: Settings and keybindings that I change with a new install of Sublime Text, along with some additional tips & tricks to enhance the daily use of it.
date: 2024-10-19
categories: [Notes, Misc]
tags: [sublimetext, misc, notes]
---
Below are the settings I use that give me the best look and feel of Sublime Text.

## Custom settings

`ctrl`+`shift`+`p` -> Settings -> paste in the `json` below:
```json
{
	"font_size": 16,
	"font_face": "Jetbrains Mono",
	"save_on_focus_lost": true,
	"caret_style": "phase",
	"line_padding_bottom": 3,
	"line_padding_top": 3,
    "translate_tabs_to_spaces": true,
	"color_scheme": "Catppuccin Mocha.sublime-color-scheme",
}
```
## Custom keybindings

`ctrl`+`shift`+`p` -> Keybindings -> paste in the json below:
```json
[
		{ "keys": ["ctrl+m"], "command": "toggle_comment", "args": { "block": false } },
]

```
## Install Catppuccin theme for Sublime Text

Install the package from Github.

1. `ctrl`+`shift`+`p` 
2. Browse Packages 
3. Enter `powershell` in the adress bar and copy in the line below:
```
git clone https://github.com/catppuccin/sublime-text.git Catppuccin
```

## Fold Python
Package that lets you fold Python code for better visibility and management.

1. `ctrl`+`shift`+`p`
2. Package Control: Install Package
3. Install `Fold Python`

## Tips and trick

Select multiple lines at once.
1. Select the lines you want to edit at once
2. `ctrl`+`shift`+`l`

Move the selected line:

`ctrl`+`shift`+`up arrow` (or `down arrow`)

Select text within the following `()`, `{}` or `[]`.

`ctrl`+`m`