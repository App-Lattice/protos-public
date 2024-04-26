# Cert Manager 

## DNS
https://cert-manager.io/docs/configuration/acme/dns01/

In certain applications, you may need the user to provide the DNS01 provider information in a request so that cert manager can be configured properly. For example for Digital Ocean:

```bash
grpcurl -d @ my-service.myapp.io:443 MyService.Api.somethingThatManagesDns <<EOM
{
  "dns" : {"accessToken" : "do-access-token}
}
EOM

```
or, for AWS
```bash
grpcurl -d @ my-service.myapp.io:443 MyService.Api.somethingThatManagesDns <<EOM
{
  "dns" : {
    "region":"us-east-1",
    "hosted_zone_id":"abc123",
    "role"="arn:aws:iam:yyyyyyyyyyyyyyyyy:role/dns-manager"
  }
}
EOM

```