# Bamboo

The local url is http://bamboo.internal/

It is made possible through the [NgInx](nginx.md) proxy configuration and the [hosts file](../envs/hosts.links)

The container ***internal*** link is http://bamboo:8085

## Agent (Locally running)

https://confluence.atlassian.com/bamboo/bamboo-remote-agent-installation-guide-289276832.html

Download agent server

http://bamboo.internal/agentServer/agentInstaller/atlassian-bamboo-agent-installer-9.1.1.jar

Run agent server

```shell
java -jar atlassian-bamboo-agent-installer-9.1.1.jar http://bamboo.internal/agentServer/
```

## Post-Configuration

After all the applications have been configured.

You need to create application (**bi-directional**) links with [Jira](jira.md) and [BitBucket](bitbucket.md).

Note:
- the Jira should exist if the [same step](jira.md#Post-Configuration) has been done at the Jira level.
- the BitBucket should exist if the [same step](bitbucket.md#Post-Configuration) has been done at the BitBucket level.

http://bamboo.internal/plugins/servlet/applinks/listApplicationLinks

___
[Back](../README.md) 