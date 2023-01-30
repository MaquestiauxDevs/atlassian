# Atlassian Test Environment

You will need to request trial keys via: https://my.atlassian.com/license/evaluation

**The trial license are valid for 30 days (E.g. 30/Jan/2023 -> 28/Feb/2023)**

## Postgresql (port:5432)

## JIRA (port:8080)

## BitBucket (port:7990)

## Confluence (port:8090)

## Bamboo (port:8085)

https://confluence.atlassian.com/bamboo/bamboo-remote-agent-installation-guide-289276832.html

Run agent server

```shell
java -jar atlassian-bamboo-agent-installer-9.1.1.jar http://localhost:8085/agentServer/
```

**Attention: Create the application link using the service name, not localhost nor container name AND after installing each server**

**TODO: Link Jira with Bitbucket/Bamboo**