---
author: clausmalver
title: Sublime Text, settings, keybindings and tips and tricks
description: Settings that I change with a new install of Sublime Text, along with some additional tips and tricks to enhance it a bit.
date: 2024-10-19
categories: [Notes, Misc]
tags: [sublimetext, misc, notes]
---
# Sublime Text

Below are the settings I use that give me the best look and feel of Sublime Text.

## Custom settings

`ctrl`+`shift`+`p` -> Settings -> paste in the json below
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

`ctrl`+`shift`+`p` -> Keybindings -> paste in the json below
```json
[
		{ "keys": ["ctrl+m"], "command": "toggle_comment", "args": { "block": false } },
]

```
## Install Catppuccin theme for Sublime Text

Install the package from Github.

`ctrl`+`shift`+`p` -> Browse Packages -> Enter `powershell` in the adress bar and copy in the line below.
```
git clone https://github.com/catppuccin/sublime-text.git Catppuccin
```

## Fold Python
Package that lets you fold Python code for better visibility and management.

`ctrl`+`shift`+`p` -> Package Control: Install Package -> Install `Fold Python`

## Tips and trick

Select multiple lines at once.
1. Select the lines you want to edit at once
2. `ctrl`+`shift`+`l`

Move the selected line:
`ctrl`+`shift`+`up arrow` (or `down arrow`)

Select text within the following `()`, `{}` or `[]`.
`ctrl`+`m`