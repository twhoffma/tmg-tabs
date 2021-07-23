# tmg-tabs
This is a simple mirror of the raw files from http://www.themountaingoats.net/wiki. It goes down from time to time, and it would break my heart if it suddenly disappeared.
The script used for downloading is also in the repo. 
Keep only listening to The Mountain Goats (and friends).


### AWK
'BEGIN {FS = "\]\]"} $0 ~ /\[\[tabs\:[^\]]+?/ {printf "%s\n", $1}'

Then use system() to run wget ozw.

### SED
-rn 's/\[\[(tabs:[^]]+?)\]\]/\1/p'

not entirely sure how to get it done if there are multiple on a single line in an elegant way - but can always use SED :)

### GREP
-A option 

and be used to introduce a newline after context? 

Then loop, wget, regenerate README-md based on index.html raw, git add ., git commit -m "...", git push
