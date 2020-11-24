# Jira Sandbox Environment

## Pre-conf
You need to add this hosts in your "hosts"-file:

```bash
# Docker Jira Sandbox
127.0.0.1  jira.internal
127.0.0.1  pgadmin.internal
127.0.0.1  nodered.internal
```
If you are't able to edit the "hosts"-file, use the ports..  

App     | Url
--------|----------------------  
jira    | http://localhost:8080  
pgadmin | http://localhost:5050
nodered | http://localhost:1880

## Startup...
````bash
docker-compose up -d
````
- Go to: http://pgadmin.internal
- Connect to Postgres database
- Create a database for Jira
- Goto: http://jira.internal
- Start setup Jira with the database you had created.


Use NodeRed (http://nodered.internal) for mockups of your work / testing.  
For example:  
- Add "palette" for SMTP, so Jira can send mail  
- Add "palette" for Dashboard, and show the status from JVM.  
  (To easy view JVM: add jolokia-plugin for Jira.)

## Links
Apps    | Url
--------|-----------------------------
Jolokia | https://marketplace.atlassian.com/apps/1213211/jolokia-monitoring-agent
node-red-contrib-mailin-smtp (SMTP for NodeRed)| https://flows.nodered.org/node/node-red-contrib-mailin-smtp
node-red-dashboard (Dashboard for NodeRed) | https://flows.nodered.org/node/node-red-dashboard
@digitaloak/node-red-contrib-digitaloak-postgresql (Postgres for NodeRed)| https://flows.nodered.org/node/@digitaloak/node-red-contrib-digitaloak-postgresql



## License  
[MIT](https://choosealicense.com/licenses/mit/)
