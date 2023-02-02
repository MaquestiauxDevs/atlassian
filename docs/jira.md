# Jira

The local url is http://jira.internal/

It is made possible through the [NgInx](nginx.md) proxy configuration and the [hosts file](../envs/hosts.links)

The container ***internal*** link is http://jira:8080

## Post-Configuration

After all the applications have been configured.

You need to create application (**bi-directional**) links with [BitBucket](bitbucket.md), [Confluence](confluence.md) and [Bamboo](bamboo.md).

Got to http://jira.internal/plugins/servlet/applinks/listApplicationLinks for [Confluence](confluence.md) and [BitBucket](bitbucket.md)

Got to http://jira.internal/secure/admin/jira/ViewBambooApplicationLinks.jspa for [Bamboo](bamboo.md)