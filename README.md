# activity-git
Make it look like you're being super productive on your github account. 

```shell

#! /bin/bash

NUM=`shuf -i 1-15 -n 1`
#echo "Random int: $NUM"
cd /home/barney/server-crawler # some private repo

for ((i = 1 ; i <= $NUM ; i++)); do
	echo " " >> README.md
	git add README.md
	git commit -m "Commit $i/$NUM" --quiet
	git push origin master --quiet
done

# crontab expression for daily exec at 1am
# 0 1 * * * /bin/bash /home/barney/activity-git/activity.sh

```
