==== update 11/18/2018 ====
Notice: All programs are only tested on CSIL. Please use CSIL for testing.

The other two baseline programs have been added.
[baseline2]: Minimax with depth=2
[baseline3]: Minimax with depth=2 and basic pruning
They both accept same commandline arguments as RandomHex.py.

==== update 10/31/2018 ====
1. [baseline1]: RandomHex.py implements the basic random algorithm. You can manually play against it or use it for evaluation of your developed algorithm (under the HexReferee program). To run it, type in a terminal:

python3 RandomHex.py [-d] [-p <ai_color>] [-s <board_size>]
or
python3 RandomHex.py [--debug] [--player=<ai_color>] [--size=<board_size>]

-d, --debug: debug mode, if enabled, the program will run step by step and print out game board
-p, --player: (default: RED) specify the color the program uses, can be "RED" or "BLUE"
-s, --size: (default: 7) specify the size of game board, should be integer in [1,26]

Execution Examples:
python3 RandomHex.py -p RED -s 11  # the program plays RED with board size 11 (you play BLUE)
python3 RandomHex.py -p BLUE -s 7  # the program plays BLUE with board size 7 (you play RED)
python3 RandomHex.py -d -p RED -s 17 # enable debug mode, the program plays RED with board size 17 (you play BLUE)

2. HexReferee is a referee command that enables two executable scripts (AI programs) to compete with each other and generate the final result. To run it, type in a terminal:

HexReferee [-d] -r <red_executable> -b <blue_executable> -s <board_size>
or
HexReferee [--debug] --red=<red_executable> --blue=<blue_executable> --size=<board_size>

-d, --debug: debug mode, if enabled, the program will run step by step
-r, --red: specify RED player executable
-b, --blue: specify BLUE player executable
-s, --size: (default: 7) specify the size of game board, should be integer in [1,26]

Execution Examples (assume all files are in current directory):
./HexReferee -r ./RandomHexExecutable.sh -b ./RandomHexExecutable.sh -s 11 # let the RandomHex program plays with itself on a board of size 11
./HexReferee -d -r ./MinimaxHexExecutable.sh -b ./RandomHexExecutable.sh -s 7 # let two different programs play with each other, with debug mode enabled

[IMPORTANT NOTICE]: Currently HexReferee can ONLY be executed on CSIL machines. Use the scp command to upload the HexReferee program to your CSIL machine, or get the latest HexReferee program from the MP website by typing the command in terminal:

wget http://cs.ucsb.edu/~cs165a/mp2/HexReferee

3. To let the HexReferee call your shell scripts successfully, make sure they are executable. If you are not sure, try:

chmod +x <your_executable>
or
chmod a+x <your_executable>

4. Please visit the course website, piazza or MP website (http://cs.ucsb.edu/~cs165a/) for more information and updates.
