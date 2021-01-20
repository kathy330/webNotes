## to do
- [ ] wechat alfred workflow. 
- [ ] shell automation.


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

## Create a react app
```zsh
npx create-react-app my-app
cd my-app
npm start

npm install --save react-router-dom
```
