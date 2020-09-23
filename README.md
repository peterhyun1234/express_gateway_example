# express_gateway_example

## 1. How to install
``` bash
### Install Express Gateway
    $ npm install -g express-gateway

### Create an Express Gateway
    $ eg gateway create

### Follow the prompts and choose the Getting Started server template
    Follow the prompts and choose the Getting Started server template
    ➜ eg gateway create
    ? What is the name of your Express Gateway? my-gateway
    ? Where would you like to install your Express Gateway? my-gateway
    ? What type of Express Gateway do you want to create? (Use arrow keys)
    ❯ Getting Started with Express Gateway
    Basic (default pipeline with proxy)

### Run Express Gateway
    $ cd my-gateway && npm start
```

## 2. create users
```bash
### Create a new Express Gateway user.(게이트 웨어 켜진 상태에서!)
    $ eg users create
    ? Enter firstname [required]: peter
    ? Enter lastname [required]: jeon
    ? Enter username [required]: peterhyun
    ? Enter email:
    ? Enter email: undefined
    ? Enter redirectUri:
    ? Enter redirectUri: undefined
    √ Created 062ef359-ab0a-486a-800f-f963c2d9ee2f
    {
    "isActive": true,
    "username": "peterhyun",
    "id": "062ef359-ab0a-486a-800f-f963c2d9ee2f",
    "firstname": "peter",
    "lastname": "jeon",
    "createdAt": "Wed Sep 23 2020 14:21:09 GMT+0900 (GMT+09:00)",
    "updatedAt": "Wed Sep 23 2020 14:21:09 GMT+0900 (GMT+09:00)"
    }

### Need to create 2 credentials for this user: an OAuth2 credential, and a basic-auth (password) credential
    $ eg credentials create -c 062ef359-ab0a-486a-800f-f963c2d9ee2f -t oauth2
    $ eg credentials create -c (id) -t oauth2
    √ Created 062ef359-ab0a-486a-800f-f963c2d9ee2f
    {
    "isActive": true,
    "createdAt": "Wed Sep 23 2020 14:25:51 GMT+0900 (GMT+09:00)",
    "updatedAt": "Wed Sep 23 2020 14:25:51 GMT+0900 (GMT+09:00)",
    "autoGeneratePassword": true,
    "passwordKey": "secret",
    "id": "062ef359-ab0a-486a-800f-f963c2d9ee2f",
    "secret": "a934fb48-6771-4f47-a1b6-2f0b583432fe"
    }

    $ eg credentials create -c 062ef359-ab0a-486a-800f-f963c2d9ee2f -t basic-auth -p "password=???"
    $ eg credentials create -c (id) -t basic-auth -p "password=???"
    √ Created 062ef359-ab0a-486a-800f-f963c2d9ee2f
    {
    "isActive": true,
    "createdAt": "Wed Sep 23 2020 14:27:40 GMT+0900 (GMT+09:00)",
    "updatedAt": "Wed Sep 23 2020 14:27:40 GMT+0900 (GMT+09:00)",
    "autoGeneratePassword": true,
    "passwordKey": "password",
    "id": "062ef359-ab0a-486a-800f-f963c2d9ee2f"
    }




```

## 2. ref by

### 2.1. adopting micro services 
    https://medium.com/@oyedejipeace/building-a-simple-microservices-app-with-express-gateway-a8fd49d81aeb
### 2.2. adopting security by using oauth2.0
    https://www.express-gateway.io/getting-started-with-oauth2/
