# commits per author
git shortlog -s -n 


# Total lines of code 
git log --author="Pankaj Tanwar" --oneline --shortstat | grep 'insertions(+)' | awk -F ' ' '{ addition+=$4; remove+=$6 } END { print addition, remove; }'


# creation date = first commit date
git log --reverse
