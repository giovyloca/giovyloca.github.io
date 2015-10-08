git checkout master
git pull --rebase
git branch -D ephemeral/stage
git checkout -b ephemeral/stage

for i in `git branch -r | grep 'integration\/'`; do
    echo $i
    git merge --no-edit $i
done

