# Lupo

A static website generator written in Bash.

## Installation
```bash
git clone https://github.com/davidpeach/lupo
cd ./lupo
./install
```

## Directories
- `./src/`: Your source website files written in Markdown, CSS and JavaScript.
- `./html/`: The built website root.
- `./.templates/`: Your template files for building your website.
- `./.config/`: Any configuration-related files.
  - `./.config/vars.template.bash`: the variables that will be available when indexing the website.

## Usage
### lupo init
This will initialise the current working directory as a new "lupo" site.
It will scaffold the following files and folders:
- `./src/` directory
- `./.templates` directory
- `./.config/` directory with initial configuration files in.
