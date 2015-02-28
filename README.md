# gitmirror
gitmirror
## instruction
precondition: need to create an empty git repo in target site
``` bash
#!/bin/bash
declare -a arr=("modulename1" "modulename2" "modulename3")

for i in "${arr[@]}"
do
    echo "$i"
    git clone  --bare git@github.sourcesite.com:nodejs/"$i".git
    cd "$i".git 
    git push --mirror git@github.targetsite.com:nodejs/"$i".git
    cd ..
done
```
