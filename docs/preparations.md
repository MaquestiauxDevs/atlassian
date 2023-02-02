# Start 

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

Wait a few minutes, letting the different services to fullt start