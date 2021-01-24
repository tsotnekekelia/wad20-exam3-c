# WAD 2020 Exam 2: Project C

## Project setup
```
npm install
```

### Compiles for development
```
npm start
```
# Setup

You will need to [import](https://docs.github.com/en/free-pro-team@latest/github/importing-your-projects-to-github/importing-a-repository-with-github-importer) 
this repository to you GitHub account, to do that please follow these steps:
* Go to Github [import page](https://github.com/new/import)
  * **Note**: you have to be logged in to your GitHub account
* In the first field `"Your old repository’s clone URL"` enter URL of this repository `https://github.com/tsotnekekelia/wad20-exam3-c`
* In  the next field give it a name
* Make it **Private**
* And begin to import, it should take few seconds
* Add me as a collaborator to your new repository, [click here](https://docs.github.com/en/free-pro-team@latest/github/setting-up-and-managing-your-github-user-account/inviting-collaborators-to-a-personal-repository)
 to learn how
  * My `email` and `username` on github is: `cotne.kekelia@yahoo.com` and `tsotnekekelia`
  
# Tasks
  
Modify [/routes/users.js](./routes/users.js).

1. Add a new `POST` route `localhost:3000/users/:id`, where `id` is a route parameter _**[4 points]**_
    1. Endpoint will also receive JSON object in the body of the request, something like this:
    
    ```
        {
            "property": "email",
            "value": "new@address.com"   
        }
    ```

2. Endpoint should read local [/data/users.js](./data/users.js) file 
and if user with provided `id` is found, their respective `property` needs to be updated with provided `value`, after updating property, user object needs to be returned as 
an endpoint response, otherwise return error `404` _**[10 points]**_
3. In case user is found, after updating users' property, persist changes by writing updated users array in to the [/data/users.js](./data/users.js) file _**[6 points]**_
    1. **Note**: make sure that you do not lose records of the other users
4. Only certain properties can be changed for the user, 
so validate that sent `property` is one of these: 
`firstname, lastname, email, avatar, occupation`.
in case validation fails return response with status code `400` _**[5 points]**_
