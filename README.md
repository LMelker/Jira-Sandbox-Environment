# Jira Sandbox Environment

## Pre-conf
You need to add this hosts in your "hosts"-file:

```bash
# Docker Jira Sandbox
127.0.0.1  jira.internal4
127.0.0.1  pgadmin.internal
127.0.0.1  nodered.internal
127.0.0.1  grafaba.internal
127.0.0.1  prometheus.internal

```
If you are't able to edit the "hosts"-file, use the ports..  

App        | Url
-----------|----------------------  
jira       | http://localhost:8080
pgadmin    | http://localhost:5050
nodered    | http://localhost:1880
grafaba    | http://localhost:3000
prometheus | http://localhost:9090

## Startup
````bash
docker-compose up -d
````
- Go to: http://pgadmin.internal
- Connect to Postgres database
- Create a database for Jira and confluence
- Goto: http://jira.internal
- Start setup Jira with the database you had created.

## Update
````bash
docker-compose pull
````


## [Easy test of REST API...](nodered.md)
Use NodeRed (http://nodered.internal) for mockups of your work / testing.  
For example:  
- Add "palette" for SMTP, so Jira can send mail  
- Add "palette" for Dashboard, and show the status from JVM.  
  (To easy view JVM: add jolokia-plugin for Jira.)

## [Monitoring Jira...](prometheus_grafana.md)
Use Prometheus to pick up data every 15sec from Jira.
Use Grafana to view the data that Prometheus picks up.

### Setup Grafana
- Go to: http://grafana.internal
- Login with: admin/admin
- Update the password.
- Pointout Prometheus as a Data Source
  - left side menu: Configuration / Data Sources
  - Add Prometheus
    - URL: http://prometheus:9090
    - Access: Server
  - Press: Save & test
### Setup Prometheus
- In Jira: add the addon: "Prometheus Exporter For Jira"
  - Go to the settings of Prometheus:
    - /secure/PromForJiraSecureTokenConfigAction!default.jspa
  - Generate a Token!
- Edit the: prometheus.yml
  - add the token from Jira
  - restart Prometheus container
  

## [Links...](links.md)


## License  
[MIT](https://choosealicense.com/licenses/mit/)
