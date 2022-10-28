### def
This plugin is used to specify and run a default command in any directory of your choice

To use it you can either run `def init` to create the default config file or create a `.def` file in every folder where you want to use the command

## Configuration
The default configuration file is stored in `$XDG_CONFIG_HOME/def/`. If `$XDG_CONFIG_HOME` is not set then it defaults to `$HOME/.config`

The structure of the file is `<folder> <command>` on each line. The folders can be specified as regex. The ~ character is automatically expanded to the `$HOME` directory

If you use a local `.def` file then it should only hold the command to be executed

# Example of a global config
```
/home/vinter/frontend npm run
^/home/vinter/projects/go go build
~/stuff/git git pull
```
Hence typing `def` in `/home/vinter/frontend` will run `npm run` instead

# Example of a local config
```
git init
````
Hence typing `def` in the folder that contains the above `.def` file will run `git init` instead

## Additional commands
You can add a command for the current folder by using `def add [command]`.
```
def add npm run
```

You can remove any commands that match the current folder by using `def remove`. Please note that it **will also remove** any local `.def` files.
