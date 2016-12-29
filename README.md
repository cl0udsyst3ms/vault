# vault
vault config files
add secret
vault write secret/terraform/db1pass vault=passwordDB
curl -H "X-Vault-Token: e8e69b4c-42eb-5493-b3fa-63be973d733e" -H "Content-Type: application/json" -X POST -d '{"value":"postgresSQLpass"}' http://7.7.7.73:8200/v1/secret/terraform/postgres
