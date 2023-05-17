# Lupo

Lupo is a basic static website generator written in Bash. It will
copy a hierarchy of files and folders, converting any markdown files
into HTML files.

It can also parse certain markdown frontmatter array values into archive
pages: for example, if there are posts that have a tag of "websites", a
"websites" archive page will be created with a list of the tagged posts
contained.

Once configured, you can write / edit pages locally; build the new
pages, or do a full website build; then deploy straight to your server.

## Installation
```bash
git clone https://github.com/davidpeach/lupo
cd ./lupo
./install
```

## Usage example - creating your first single homepage
1. Install `lupo` as per the directions above.
2. Go into a directory that you want to use as your website.
3. Run `lupo init`.
4. Go into your `src` directory and create a file called `index.md`
5. Add the following content:
```markdown
---
title: My Website
---

Welcome to my website!
```
6. Run `lupo build`
7. A new file should be present in `./html/index.html`.

## Available Commands

### lupo init
This will initialise the current working directory as a new "lupo" site.
It will scaffold the required files and folders.

## lupo index
## lupo build
## lupo post
## lupo edit
