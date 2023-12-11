[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![MELPA](https://melpa.org/packages/com-css-sort-badge.svg)](https://melpa.org/#/com-css-sort)
[![MELPA Stable](https://stable.melpa.org/packages/com-css-sort-badge.svg)](https://stable.melpa.org/#/com-css-sort)

# com-css-sort
> Common way of sorting the CSS attributes.

[![CI](https://github.com/jcs-elpa/com-css-sort/actions/workflows/test.yml/badge.svg)](https://github.com/jcs-elpa/com-css-sort/actions/workflows/test.yml)

| Before Sorting                                  |  Type Sorting                                      |  Alphabetic Sorting                                      |
|:-----------------------------------------------:|:--------------------------------------------------:|:--------------------------------------------------------:|
|<img src="./etc/com-css-sort-before.png"/>|<img src="./etc/com-css-sort-type-sort.png"/>|<img src="./etc/com-css-sort-alphabetic-sort.png"/>|

## ❓ How to use?

### Alphabetic Order

1. Just set `com-css-sort-sort-type` to alphabetic-sort.

```el
(setq com-css-sort-sort-type 'alphabetic-sort)
```

### Type Order / Customize Order Your Own

1. Set `com-css-sort-sort-type` to type-sort.

```el
(setq com-css-sort-sort-type 'type-sort)
```

2. Create `sort-order.config` file at the version control root directory.
You can grab a config file from `./config_examples/` directory in this 
repository. If the file does not exists, variable list 
`com-css-sort-default-attributes-order`  will be use as default sorting
order list.

3. Look at the .config file, the order in the file will be the order that
the CSS attributes will be sorted.

## 🧪 Configuration

Type of sorting algorithm you want used when sorting CSS attributes.

* type-sort : Sort in group type. Use 'sort-order.config' if there is one in the 
version control root directory. (Default)

* alphabetic-sort : Sort in alphabetic order. The 'sort-order.config' file will be 
ignore and will not do anything.

```el
(setq com-css-sort-sort-type 'type-sort)        ; Type Sorting
(setq com-css-sort-sort-type 'alphabetic-sort)  ; Alphabetic Sorting
```

If you don't like the path or file name, you can change it too. This variable is
relative path to version control root directory.

```el
(setq com-css-sort-sort-file "sort-order.config")
```

Customize your own sorting order programmatically. If you do not have the
`sort-order.config' file in the version control root directory then this will be use!

```el
;; Default sorting order list.
(setq com-css-sort-default-attributes-order '("display" "position" "top" "right" "bottom" "left" "float" "clear"
                                              "visibility" "opacity" "z-index" "margin" "margin-top" 
                                              "margin-right" "margin-bottom" "margin-left" "outline" "border" 
                                              "border-top" "border-right" "border-bottom" "border-left" 
                                              "border-width" "border-top-width" "border-right-width" 
                                              "border-bottom-width" "border-left-width" "border-style" 
                                              "border-top-style" "border-right-style" "border-bottom-style" 
                                              "border-left-style" "border-color" "border-top-color" 
                                              "border-right-color" "border-bottom-color" "border-left-color" 
                                              "background" "background-color" "background-image" 
                                              "background-repeat" "background-position" "cursor" "padding" 
                                              "padding-top" "padding-right" "padding-bottom" "padding-left" 
                                              "width" "min-width" "max-width" "height" "min-height" "max-height" 
                                              "overflow" "list-style" "caption-side" "table-layout" 
                                              "border-collapse" "border-spacing" "empty-cells" "vertical-align" 
                                              "text-align" "text-indent" "text-transform" "text-decoration" 
                                              "line-height" "word-spacing" "letter-spacing" "white-space" "color" 
                                              "font" "font-family" "font-size" "font-weight" "content" "quotes"))
```

## ⌨️ Key Bindings

Just bind the key if to whatever you feel comfortable with.

```el
;; Sort attributes inside block.
(define-key css-mode-map (kbd "C-k s") #'com-css-sort-attributes-block)

;; Sort attributes through the whole document.
(define-key css-mode-map (kbd "C-k d") #'com-css-sort-attributes-document)
```

## 🛠️ Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Elisp styleguide](https://img.shields.io/badge/elisp-style%20guide-purple)](https://github.com/bbatsov/emacs-lisp-style-guide)
[![Donate on paypal](https://img.shields.io/badge/paypal-donate-1?logo=paypal&color=blue)](https://www.paypal.me/jcs090218)
[![Become a patron](https://img.shields.io/badge/patreon-become%20a%20patron-orange.svg?logo=patreon)](https://www.patreon.com/jcs090218)

If you would like to contribute to this project, you may either 
clone and make pull requests to this repository. Or you can 
clone the project and establish your own branch of this tool. 
Any methods are welcome!

### 🔬 Development

To run the test locally, you will need the following tools:

- [Eask](https://emacs-eask.github.io/)
- [Make](https://www.gnu.org/software/make/) (optional)

Install all dependencies and development dependencies:

```sh
$ eask install-deps --dev
```

To test package's installation:

```sh
$ eask package
$ eask install
```

To test compilation:

```sh
$ eask compile
```

**🪧 The following steps are optional, but we recommend you follow these lint results!**

The built-in `checkdoc` linter:

```sh
$ eask lint checkdoc
```

The standard `package` linter:

```sh
$ eask lint package
```

*📝 P.S. For more information, find the Eask manual at https://emacs-eask.github.io/.*

## ⚜️ License

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

See [`LICENSE`](./LICENSE.txt) for details.
