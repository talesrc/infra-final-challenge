# Infrastructure Rotation Challenge

## How to run it?
To run it you just need to execute the command ```./localstack``` inside the repository root folder. It will create the cluster, install the nginx ingress and apply the application manifests.
teste

## How to test it?
If no error logs has appeared during the execution of the localstack script, it probably has worked. So to test it you need to enter the following command inside your terminal: ```curl http://localhost```.
The output must be equal to the below.
```terminal
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My HTML</title>
  </head>
  <body>
    <h1>This is my html. It is served with go</h1>
  </body>
</html>%
```
