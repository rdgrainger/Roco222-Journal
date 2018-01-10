# Learning Git and Hacking a robot

## Part 1 - Git & Lab Journal

### Step 1 - Markdown file
The text below is our first attempt at using the markdown syntax.
ROCO222
Introduction to Sensors and Actuators

**This is an example of bold text**

*This is an example of italics*

~~Strikethrough~~

  1. Item 1
  2. Item 2 
  3. Item 3

### Step 2 - Command-line 101

opened the terminal amd tried a few commands

**$ ls**

This command gives us a list of directories.

**cd /tmp**

This command changes directories, in this case to tmp.

**cd $HOME**

cd is used to change a directory.In this case, the home directory. The dollar sign means a normal user as opposed to a 'root' user.

**mkdir**

mkdir is for making new directories.

**echo "hello" > hello.md**

echo is a built in command that writes its arguments to standard form. This writes "Hello" in a markdown document named hello.md

**cat hello.md**

cat is short for concatenate. cat allows use to create single or multiple diles , view contents of a file, concatenate files and redirect the output in terminal or files. Using this command, the terminal ouput "Hello", thereby showing what we wrote in the markdown document.

**cp hello.md hello-again.md**

This copies the contents of hello.md into a new markdown named hello-again.md

**mv hello-again.md hello-hello.md**

This renames "hello-again.md" to "hello-hello.md"

**rm hello.md**

This has deleted the hello.md directory.

**rm -rf the rm -rf**

is the same as rm -r -f the -r meaning "remove directories and their contents recursively" the -f will "ignore nonexistent files and arguments, never prompt"

**cat /proc/cpuinfo**

This command lists characteristics of the computer's cpu, incluidng number of cores.

### Step 3 - Github Account
An account has been made to push changes to a remote repository

### Step 4 - Git repository

*Picture on username and email configuration:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/Screenshot%20from%202017-09-28%2012-48-30.png

### Step 5 – Your first commit

*Git commit short command:*

### Step 6 - Version Tracking

For this module, we have used git to create a lab journal using the markdown syntax. We have learned the basics on git repositories, including the master branch and practised making additional branches. The text in these branches can be merged with the master branch. We have also begun to commit changes to a repository, adding a description on the updates made. By using git push, we can upload our changes to a remote repository- in this case on our github account.

### Step 7 - Going Social

*Pushing changes to github:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/Screenshot%20from%202017-09-28%2013-05-23.png

## Part 2 - Hacking a robot

The task asked us to interface with a robot using the Linux terminal and some python code. The first step was to connect to the robot itself (named chapman). I used 

*ping chapman.local*
and then
*ssh nao@192.168.0.184*

*Image of this command:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/connectingtobot.png

I entered the required password and was now connected to the robot. The next step was to find a way to send it a message.

I created a python file (named hack4.py) in the terminal and copied the code given:

*from naoqi import ALProxy
tts = ALProxy("ALTextToSpeech", "localhost", 9559)
tts.say("I've hacked you, robot!")*

*Python editing:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/typing%20in%20python.png

*Then I ran the executable hack4.py with:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/makingtherobottalk.png



