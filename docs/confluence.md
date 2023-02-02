# Confluence

The local url is http://confluence.internal/

It is made possible through the [NgInx](nginx.md) proxy configuration and the [hosts file](../envs/hosts.links)

The container ***internal*** link is http://confluence:8090

## Post-Configuration

After all the applications have been configured.

You need to create application (**bi-directional**) links with [Jira](jira.md).

Note:
- the Jira should exist if the [same step](jira.md#Post-Configuration) has been done at the Jira level.

Got to http://confluence.internal/plugins/servlet/applinks/listApplicationLinks  and create the links.