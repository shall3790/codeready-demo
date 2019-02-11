## Install Debugger - VSDBG

`curl -sSL https://aka.ms/getvsdbgsh | bash /dev/stdin -v latest -l /opt/app-root/vsdbg -r linux-x64`

## Run standalone pod

```
oc run -i -t dotnet-pod --image=docker-registry.default.svc:5000/openshift/dotnet:2.1 --restart=Never -- bash
oc rsync . dotnet-pod:/opt/app-root/src
dotnet publish -c Debug -o ../app 
```