# Phoenix - a simple template for markdown documents and pandoc

## Setup
1. Install `pandoc` for your platform.
2. Place the `phoenix.latex` file inside the `~/.pandoc/templates` directory
   (create the directory if it does not exist yet).

## Usage
You can tell pandoc to use the `phoenix` template using the `--template
phoenix` argument. The most basic pandoc command hence looks like this:

```
pandoc xxx.md -o xxx.pdf --template phoenix
```

![Example output](https://github.com/mariuskiessling/phoenix-template/blob/master/example.png)

### Parameters
The template provides some variables you can set inside the YAML meta data
block. The block is surrounded by `---` and can be located anywhere inside your
markdown document. In most cases the block is located at the beginning of your
document.

You can also completely remove the meta data block. In this case the default
values apply. The following code block shows a simple YAML meta data block:

```
title: Using the phoenix template with panoc
author: Marius Kießling
titlepage: yes
header:
  - left: I appear in the upper left corner on every page
```

---

**`title`**: Set the title displayed on the title page and PDF meta data

**`author`**: Set the author displayed on the title page and PDF meta data

**`date`**: Set the date displayed on the title page

**`titlepage`** (_yes_ or _no_): Enable or disable the title page

**`colorlinks`**: (_yes_ or _no_): Enable or disable colorful links

**`header`** (list): `left`, `center`, `right` keys specify the values
displayed in the corresponding location.

**`footer`** (_yes_ or _no_ or list): If a boolean is given the footer is
displayed or hidden. If the boolean simply set to _yes_ the footer displays the
author(s) in the lower left corner and the current page in the lower right
corner. This behavior can be overwritten by providing a list of values that
specify the content of the footer. The list consists out of the keys `left`,
`center`, `right`.

**`margin`**: If no margin option is supplied the default margins (top &
bottom: 1.25cm, left & right: 2cm) are used. They can be overwritten by
supplying a list consisting of the keys `top`, `right`, `bottom`, `left`. The values provided in the list have to include a valid LaTeX unit.

## Trivia
The name of this project is derived from the old _Phoenix_ coal mining area
inside my hometown that is now partially rebuild and repurposed; something old
now serves a new and more general purpose.
