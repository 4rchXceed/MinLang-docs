# MinLang ZED language support

I made a Zed extension, that adds MinLang language support!

Releases on [Github](https://github.com/4rchXceed/MinLang/releases)

## How-To-Install

Since I don't want to add this "shitty" extension to the marketplace, you need to install it manually

### Step 1 (if you want to compile it from source/Step 1-2 doesn't work, you will use the Install Dev Extension)

Download the release

### Step 2

In the release there's a folder named "ZedLangSupport".
Run ./install.sh

### Requirements
Zed's data should be in $HOME/.local/share/zed/

### Windows?
Nope, I don't use Windows and too lazy to make a whole VM, install 60GB Microslop compiler + rustup + zed + figure out the 5000 errors of MSBuild or their tools

### Note if you want to install it from source

Since I did not create a whole github repo for the tree-sitter, you *NEED* to edit the path in extension.toml.sample **AND THEN RUN `./init.sh`**) `repository = `
The path *MUST* be: `file:///absolute-path-to-minlang-grammar`

## How-to-dev

1. Do the part above
2. Enter `Install dev extension`
3. If you want to edit files in languages/minlang or snippets/ -> just edit them and rebuild the extension (Extensions -> MinLang -> Rebuild)
4. If you want to edit files in minlang-grammar: install the tree-sitter prequisites OR if you use NixOS btw, use the shell.nix (inside of minlang-grammar)
5. To update the code and compile tree-sitter, run ../upd.sh
6. Rebuild the extension, and you should be fine
