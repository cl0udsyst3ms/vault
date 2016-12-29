# vault
vault config files
add secret
vault write secret/terraform/db1pass vault=passwordDB
curl -H "X-Vault-Token: token-id" -H "Content-Type: application/json" -X POST -d '{"value":"postgresSQLpass"}' http://7.7.7.73:8200/v1/secret/terraform/postgres
