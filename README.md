# vault
## add secret
```
vault write secret/terraform/db1pass vault=passwordDB

curl -H "X-Vault-Token: token-id" -H "Content-Type: application/json" -X POST -d '{"value":"postgresSQLpass"}' http://7.7.7.73:8200/v1/secret/terraform/postgres
```

## TLS vault setup
```
openssl genrsa -out terraform.key 2048

openssl req -x509 -new -nodes -key terraform.key -sha256 -days 1024 -out terraform-cert.pem
```
```
vault write auth/cert/certs/terraform display_name=terraform policies=prod certificate=@terraform-cert.pem ttl=3600
```

## Useful cmds
```
vault policy-write prod terraform-policy.hcl
vault policies <name>
```
