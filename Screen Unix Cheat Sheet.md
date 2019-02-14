Install Screen
  
    $ sudo apt install screen

Enter a new Screen Session

    $ screen

Detach from current screen session

Ctrl + a + d 

List screen sessions
  
    $ screen -ls

List the processes
  
    $ ps -e | grep PID_OF_SCREEN_SESSION

Enter a new screen session & giving it the name newScreenSession

    $ screen -S newScreenSession

Reattach to a screen session

    $ screen -r PID_OF_SCREEN_SESSION

Execute a command in a screen session (quit command in this case)

    $ screen -X -S PID_OF_SCREEN_SESSION quit

Kill a session from within it

Ctrl + a + k

It is actually for killing windows from within screen sessions.

New Windows Session from within screen

Ctrl + a + c

List all windows in a session

Ctrl + a + w

Ctrl a "

Ctrl a n: move to next window

Ctrl a p: move to previous window

Kill all windows & session

Ctrl a \

Divide in the panes

Ctrl a |

Move to sibling pane

Ctrl a tab

Divide in the panes Horisontal

Ctrl a S

Remove a pane

Ctrl a X

Lock a session with a password

Ctrl a x

Run a command in a screen
  
    $ screen -d -m python script.py

Screen bindings / help
    
Ctrl a ?

Type a screen binding command

Ctrl a :

