# Bitbucket

The local url is http://bitbucket.internal/

It is made possible through the [NgInx](nginx.md) proxy configuration and the [hosts file](../envs/hosts.links)

The container ***internal*** link is http://bitbucket:7990

## Post-Configuration

After all the applications have been configured.

You need to create application (**bi-directional**) links with [Jira](jira.md) and [Bamboo](bamboo.md).

Note:
- the Jira should exist if the [same step](jira.md#Post-Configuration) has been done at the Jira level.
- the Bamboo should exist if the [same step](bamboo.md#Post-Configuration) has been done at the Bamboo level.

Got to http://bitbucket.internal/plugins/servlet/applinks/listApplicationLinks and create the links.