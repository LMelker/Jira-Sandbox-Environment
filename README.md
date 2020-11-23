# Jira Sandbox Environment

## Pre-conf 
You need to add this hosts in your "hosts"-file:

```bash
# Docker Jira Sandbox
127.0.0.1  jira.internal
127.0.0.1  pgadmin.internal
127.0.0.1  nodered.internal
```

## Startup...
````bash
docker-compose up -d
````
- Go to: http://pgadmin.internal
- Connect to Postgres database
- Create a database for Jira
- Goto: http://jira.internal
 - It can be needed to Restart Jira
 - Start setup Jira with the database you had created.


Use NodeRed (http://nodered.internal) for mockups of your work / testing.  
For example:  
- Add "pallette" for SMTP, so Jira can send mail  
- Add "pallette" for Dashboard, and show the status from JVM.  
  (To easy view JVM: add jolokia-plugin for Jira.) 


## License  
[MIT](https://choosealicense.com/licenses/mit/)
