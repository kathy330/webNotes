## to do
- [ ] wechat alfred workflow. 
- [ ] shell automation.
- [ ] add 9044 to the github

## Create a react app
```zsh
npx create-react-app my-app
cd my-app
npm start

npm install --save react-router-dom
```

## Note
* facebook debug
https://developers.facebook.com/tools/debug/

## find duplicate row in database
```sql
Select * From `wp_usermeta` Group By user_id, meta_key, meta_value Having Count(*) > 1


delete from `wp_usermeta` where umeta_id in
( SELECT * FROM 
    (select min(umeta_id) from `wp_usermeta` group by user_id, meta_key,meta_value having count(*)>1) AS temp_tab
)
```

## Git
* Git Ignore
    1. edit git ignore file
    2. empty the cache `git rm -rf --cached .`
    3. update change`git add .` -> commit -> push
* Git unadd file
    `git reset` will reset all the added file
    `git stash -u` will recovery all the added file before changed.
    `git stash pop` will change all the files before it run `git stash -u`
* Pretty Git Log
    add the following code to the ~/.gitconfig
    ```
    [alias]
    lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
    lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
    lg = !"git lg1"
    ```