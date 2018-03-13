# 2017PrisonersDilemma
Computer Science Course Prisoner's Dilemma 2017

This iterated prisoner's dilemma depends on `pandas`, which you can install with:

```
python -m pip install pandas
```

It's possible that your Python 3 is installed as `python3`, so use that.

It also runs strictly in Python 3.6, because it depends on `importlib.util`.

Run `iterated-dilemma` with the names of your modules. For example, if you have team modules named:

```
foo.py
bar.py
WinningTeam666.py
/home/Documents/my-python-modules/weSuck.py
```

run `./iterated-dilemma foo.py bar.py WinningTeam666.py /home/Documents/my-python-modules/weSuck.py`. Any number of modules can be given.

Alternately, if you've got a directory that contains your modules, and the only *.py files in it are your modules, you can use the command-line flag `-d <directory-path>`:

```
./iterated-dilemma -d modules
```

Note: because Windows is weird and I don't understand how to make executables in it, in Windows do something like:

```
python iterated-dilemma.py -d modules
python iterated-dilemma.py foo.py bar.py Winningteam666.py /home/Documents/my-python-modules/weSuck.py
python iterated-dilemma.py
```

Each team's module should conform to Python 3.6 and must provide several things:

`team_name`: a string, no more than 16 characters long, containing no newlines or other weird blank space

`strategy_name`: a string, no more than 20 characters long, containing no newlines or other weird blank space

`strategy_description`: a string containing no newlines or other weird blank space

`move(my_moves, their_moves, my_score, their_score)`: a function that returns either `'b'` or `'c'` for BETRAY or COLLUDE. You can also `import GLOBALS` and return `GLOBALS.BETRAY` or `GLOBALS.COLLUDE`. `my_moves` and `their_moves` are strings containing the moves that each player has taken so far in this iterated dilemma, and `my_score` and `their_score` are ints that will usually be negative containing each player's score so far in this round.
