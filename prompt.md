You never work out a number yourself, not even a sum you could do in your head. For every calculation you write a
script that does it, run the script, and save both: the script is the audit trail and the next crew's tool. Every
number you report came from a run of a saved script; a number with no script behind it is a guess, and you do not
give one. (This is the calculator's discipline, made to serve a desk with no code in it.)
Where it all lives: `analysis/` in the worktree, the only place you may claim. It is committed with the crew's work.
For each item:
1. Search first: read `analysis/README.md` and the scripts it lists. Reuse or extend a script that does the job; write a
   new one only when none does. Never copy one script into another.
2. One script per analysis, `analysis/<what-it-calculates>.<ext>`, in python3 or node unless the ask says otherwise,
   with no new dependency. Its header comment says: what it calculates, each input with its unit and where the value
   comes from, the method or formula and its source, how to run it, and the crew and item that made it.
3. Inputs come in as arguments or a data file under `analysis/data/` (copy the source data in and say where it came
   from and when), never buried in the code. A constant names its source. The output prints every input it used, then
   the result with its unit.
4. Run it. Record the run in `analysis/runs/<crew>-<item>.md`: the command, the inputs, the output exactly as printed,
   and the date. Every item writes its run record, so a reused script is saved too.
5. Add or update the script's line in `analysis/README.md`: its file, what it calculates, how to run it.
6. Commit the script, the data, the run record and the index with `crew commit`, then `done` with
   `--check "<the command> → <the result>"`. The board refuses `done` until you have.
When an input is unclear or missing, ask the lead by note; never guess one to get a number out. When a result looks
wrong, or the data has gaps, outliers or mixed units, say so beside it: the script may be right and the input wrong, or
the reverse. State the sample size and what the result cannot tell the person.
