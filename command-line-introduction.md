# The Command Line Terminal

The command line terminal is a useful and vital tool for interacting with your computer. While you're most likely used to a Graphical User Interface (GUI) in which you move around and click things to interact with the computer, the terminal is completely text-based (we sometimes call it a Command Line Interface). It may seem dated, but it's actually extremely helpful and necessary to be successful developer.

## Opening the Terminal

In linux, click on the menu button in the upper left hand corner.
In the search bar, type "terminal" and click on "terminal emulator" when it appears in the search results.

## Basic commands

To perform operations, you enter _commands_ in the terminal. This is _input_. Try it now:

`whoami`

(Press enter or return after typing each command to run it)

This display some text - the username of the active user. This is _output_.

Here are some other commands you can try out now:

`pwd`- displays the current directory
`ls` - displays the contents of the current directory

Some commands take one or more _parameters_ which are often shown in side of [square brackets]. When you enter the parameter, don't use the square brackets:

- `mkdir [directoryName]` - creates a new directory and names it whatever you enter as the parameter.
For example: `mkdir myNewDirectory` creates a new directory under the current location named `myNewDirectory`.

- `cd [directoryName]` changes the current directory to the one specified as a parameter.
For example: `cd myNewDirectory` will move you into the directory you just created above.

- `touch [fileName]` creates a new file.
For example: `touch hello.txt`. Now enter `ls` and verify the file was created.

- `rm [fileName]` deletes a file.
For example: `rm hello.txt`. Now enter `ls` and verify the file was deleted.

- `rmdir [directoryName]` deletes a directory, but only if it is empty.
For example: `rmdir myNewDirectory`. Now enter `ls` and verify the directory was deleted.

- `man [commandName]` will display the command's manual. The terminal will display the information inside of a text editor. To exit, type 'q'.

Commands can accept multiple parameters. For instance,

- `cp [sourceFile] [targetFile]` will copy the sourceFile to the targetFile.
- `cp [sourceFile] [targetDirectory]` will copy the sourceFile into the targetDirectory.
- `mv [sourceFile] [targetFile]` will _move_ the sourceFile into the targetDirectory.

Commands can also accept _flags_ which are one or more characters prefaced by a dash `-`.
Remember that the `rmdir` command can only delete a directory if it is not empty. Using flags, we can get around this limitation:

First create a test directory:

- `mkdir test`

Now add some files into the directory:

- `touch test/one.txt`
- `touch test/two.txt`

You can check the directory contents from outside the directory by:

- `ls test`

The results should show the two files you created.

Now let's delete them all at once:

- `rm -rf test`

List the directory contents to verify:

- `ls`

## History

Most terminals store a history of your commands. You can work back through your command history by pressing the up arrow, and then can move forward in time by pressing the down arrow. You can also search for a particular command by entering `control+r` and then typing some search terms. If there's a match in your history, the full command will appear and you can hit enter to run it.
