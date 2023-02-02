# NgInx

NgInx is used to proxy the different apps

## Configuration

We create one entry per application.

## Jira HTTP

The proxy settings are forwarding the request to the **http://jira:8080** to **http://jira.internal**

***Note: the **jira.internal** is defined in the computer **[hosts file](../envs/hosts.links)***

```
http {
 server {
   server_name jira.internal;
   proxy_read_timeout 600s;
   location / {
     proxy_set_header X-Forwarded-Host $host;
     proxy_set_header X-Forwarded-Server $host;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     proxy_pass http://jira:8080;
     client_max_body_size 10M;
   }
 }
 ...
}
```

## Confluence HTTP

The proxy settings are forwarding the request to the **http://confluence:8090** to **http://confluence.internal**

***Note: the **conflence.internal** is defined in the computer **[hosts file](../envs/hosts.links)***

```
http {
 ...
 server {
   server_name confluence.internal;
   proxy_read_timeout 600s;
   location / {
     proxy_set_header X-Forwarded-Host $host;
     proxy_set_header X-Forwarded-Server $host;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     proxy_pass http://confluence:8090;
     client_max_body_size 10M;
   }
 }
 ...
}
```

## Bitbucket HTTP

The proxy settings are forwarding the request to the **http://bitbucket:8090** to **http://bitbucket.internal**

***Note: the **bitbucket.internal** is defined in the computer **[hosts file](../envs/hosts.links)***

```
http {
 ...
 server {
   server_name bitbucket.internal;
   proxy_read_timeout 600s;
   location / {
     proxy_set_header X-Forwarded-Host $host;
     proxy_set_header X-Forwarded-Server $host;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     proxy_pass http://bitbucket:7990;
     client_max_body_size 10M;
   }
 }
 ...
}
```

## Bitbucket SSH

For allowing **Bamboo** to link with a **Bitbucket** repository we need to forward also the Bitbucket **ssh port**

```
stream {
    upstream ssh {
        server bitbucket:7999;
    }
    server {
        listen 7999;
        proxy_pass ssh;
    }
}
```

## Bamboo HTTP

The proxy settings are forwarding the request to the **http://bamboo:8085** to **http://bamboo.internal**

***Note: the **bamboo.internal** is defined in the computer **[hosts file](../envs/hosts.links)***

```
http {
 ...
 server {
   server_name bamboo.internal;
   proxy_read_timeout 600s;
   location / {
     proxy_set_header X-Forwarded-Host $host;
     proxy_set_header X-Forwarded-Server $host;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     proxy_pass http://bamboo:8085;
     client_max_body_size 10M;
   }
 }
}
```

You can find [the complete configuration file](../envs/nginx.conf) in the repo

___
[Back](../README.md) 
