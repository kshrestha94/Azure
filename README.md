# Friday 30/06/2023 MD

## Access Sparta application folder using scp method

step 1
`cd sparta\ web\ app/`
```
this command will direct you to the specific folder in which the application file is located inside.
```
step 2
`scp -r -i ~/.ssh/<enter private key> app/ adminuser@<ip address>:~/`
```
The 'scp' command is used to recursively copy the app folder from your local machine to a remote server using a specific private key for authentication. Once executed, the app folder and its contents will be copied recursively to the adminuser's home directory (~/) on the remote server.
```

