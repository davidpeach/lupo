# Lupo

Lupo is a basic static website generator written in Bash. It will
copy a hierarchy of files and folders, converting any markdown files
into HTML files.

Once configured, you can write / edit pages locally; build the new
pages, or do a full website build; then deploy straight to your server.

You can even run the `live` command and Lupo will watch your source files 
for changes and automatically convert and push those files to your 
remote server.

## Installation
```bash
git clone https://github.com/davidpeach/lupo
cd ./lupo
./install
cd ../
rm -rf ./lupo
```

## Dependancies
- [Pandoc](https://pandoc.org/installing.html) is **required** for convert markdown files into html. This is quite a hefty requirement along with its own dependancies, I am looking for alternatives.
- [rsync](https://rsync.samba.org/) is **required** for using the `push` command.
- [inotifywait](https://man.archlinux.org/man/inotifywait.1) is **required** for using the `watch` command.
- [docker](https://docs.docker.com/engine/install/) is **required** for using the `serve` command.

## Usage

Examples are for Linux-based systems, but can be altered for Mac / Windows based ones.

## Creating your first page
1. Install `lupo` as per the directions above.
2. run `mkdir my-website && cd my-website`.
3. Run `lupo init`.
4. Create a file in your `src` directory called `index.md`.
5. Add the following content to it:
```markdown
---
title: My Website
---

Welcome to my website!
```
6. Run `lupo build` from the root of your project.
7. A new file should now be present at `./html/index.html`.
8. That html directory is the one to deploy to a remote server.

## Creating a full website
The steps above can be used to create any size website.

Any website structure you create will be replicated in the output html.
Images / CSS / JavaScript files will be copied across as they are in your source directory.
Your markdown files will be converted to html before being copied across.

for example:

```
src/
    |-- index.md
    |-- style.css
    |-- about/ 
            |-- index.md
            |-- me.jpg
    |-- blog/
            |-- my-post-one.md
            |-- my-post-two.md
```
will create:
```
html/
    |-- index.html
    |-- style.css
    |-- about/ 
            |-- index.html
            |-- me.jpg
    |-- blog/
            |-- my-post-one.html
            |-- my-post-two.html
```

You are completely free to structure your website exactly how you want to.

## Deploying to your remote server

You can set Lupo up to easily deploy to a remote server that you control.

```
lupo push
```

Setting the following configuration items in your `.config` file will allow you to do this:

- remote_user - This is the user who owns the directory where the html files will be sent to.
- ssh_identity_key - This is the path to the private key file on your computer that pairs with the public key on your remote server.
- domain_name - The domain name pointing to your server.
- remote_directory - The full path to the directory where your html files are served from on your server.

## Watching for incremental changes

```
lupo watch
```

## Pushing live changes on save

```
lupo live
```
