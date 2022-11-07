# __Function Annotation__

## __1. Create a function__
```js
    const readUsers = (filterInfo, limit) {
        const filteredUsers = return userList.filter((user) => {
            filterUser(filterInfo);
        });
        if(filteredUsers.lengh > limit){
            filteredUsers.slice(0, limit);
        }
        return filteredUsers;
    }
```

## __2. Make an annotation__
```js
    /** Reads a limited number of user lists. */
    const readUsers = (filterInfo, limit) {
        const filteredUsers = return userList.filter((user) => {
            filterUser(filterInfo);
        });
        if(filteredUsers.lengh > limit){
            filteredUsers.slice(0, limit);
        }
        return filteredUsers;
    }
```

## __3. Parameters type__
```js
    /** 
     * Reads a limited number of user lists. 
     * @param {Map} filterInfo
     * @param {number} limit
    */
    const readUsers = (filterInfo, limit) {
        const filteredUsers = return userList.filter((user) => {
            filterUser(filterInfo);
        });
        if(filteredUsers.lengh > limit){
            filteredUsers.slice(0, limit);
        }
        return filteredUsers;
    }
```

## __3. Definitions of each parameter__
```js
    /** 
     * Reads a limited number of user lists. 
     * @param {Map} filterInfo filter to filter users. Ex) { id : 12378, firstName: soap }
     * @param {number} limit number of users you read. Ex) 3: 3 users from the start.
    */
    const readUsers = (filterInfo, limit) {
        const filteredUsers = return userList.filter((user) => {
            filterUser(filterInfo);
        });
        if(filteredUsers.lengh > limit){
            filteredUsers.slice(0, limit);
        }
        return filteredUsers;
    }
```


## __4. Return__
```js
    /** 
     * Reads a limited number of user lists. 
     * @param {Map} filterInfo filter to filter users. Ex) { id : 12378, firstName: soap }
     * @param {number} limit number of users you read. Ex) 3: 3 users from the start.
     * @returns {Array} an array of users that fulfils the conditions.
    */
    const readUsers = (filterInfo, limit) {
        const filteredUsers = return userList.filter((user) => {
            filterUser(filterInfo);
        });
        if(filteredUsers.lengh > limit){
            filteredUsers.slice(0, limit);
        }
        return filteredUsers;
    }
```