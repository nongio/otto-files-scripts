# Otto Files scripts

Extra commands for [Otto Files](https://nongio.github.io/otto/). Each file here
is a small script that adds commands to the Files command palette and the
right-click menu.

## Install

Copy the scripts you want into `~/.config/otto/files-scripts/` and make them
executable:

```sh
mkdir -p ~/.config/otto/files-scripts
cp contact-sheet pdf ~/.config/otto/files-scripts/
chmod +x ~/.config/otto/files-scripts/*
```

Open a new Files window and the commands are there.

## Scripts

| Script | Command | What it does | Needs |
|---|---|---|---|
| `pdf` | PDF from Pictures | Turns the selected pictures into one PDF, a page each, in the order they were selected. Asks for the file name, shows progress page by page, and can be undone. | `img2pdf`, `pikepdf` (Python) |
| `pdf` | Searchable PDF from Pictures | The same, with a text layer read by tesseract so the PDF can be searched and copied from. Asks which language to read; only offered when tesseract is installed. | `img2pdf`, `pikepdf`, `tesseract` and its language data |
| `contact-sheet` | Make Contact Sheet | Lays the selected pictures out on one page, four across, each labelled with its name, and saves it as a JPEG next to them. Shows a preview of the pictures it will use, progress while it works, and can be undone. | ImageMagick (`montage`) |

## Write your own

A script is any executable, in any language, that reads and writes JSON. Files
asks it to `describe` its commands, then sends `preview` and `run` requests
with the selection. The guide is
[Custom Commands in Files](https://nongio.github.io/otto/files-custom-commands/).

Pull requests with new scripts are welcome.
