# Atlassian Test Environment

You will need to request trial keys via: https://my.atlassian.com/license/evaluation

**The trial license are valid for 30 days (E.g. 30/Jan/2023 -> 28/Feb/2023)**

## Start 

Add host lines to the /etc/host of your machine before starting

You can run the following command (for linux based os)

```
sudo echo "

# For Docker Atlassian
127.0.0.1 jira.internal
127.0.0.1 confluence.internal
127.0.0.1 bitbucket.internal
127.0.0.1 bamboo.internal

" >> /etc/hosts
```

Create the folder
 - postgresql
 - jira
 - bitbucket
 - confluence
 - bamboo

The shell script **create_folder_structure.sh** will do it.

Finally, run the docker compose command:

```bash
docker compose up --build -d
```

## Postgresql (port:5432)

***!! 2023-01-31 Postgres 15 is not supported, using postgres 14.6 !!***

## JIRA (port:8080)

## BitBucket (port:7990)

## Confluence (port:8090)

## Bamboo (port:8085)

https://confluence.atlassian.com/bamboo/bamboo-remote-agent-installation-guide-289276832.html

Run agent server

```shell
java -jar atlassian-bamboo-agent-installer-9.1.1.jar http://localhost:8085/agentServer/
```

## Application Link

Links the differents application through the jira

http://jira.internal/plugins/servlet/applinks/listApplicationLinks
http://jira.internal/secure/admin/jira/ViewBambooApplicationLinks.jspa

http://bitbucket.internal/plugins/servlet/applinks/listApplicationLinks
http://confluence.internal/plugins/servlet/applinks/listApplicationLinks
http://bamboo.internal/plugins/servlet/applinks/listApplicationLinks