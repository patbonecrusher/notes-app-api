# Commands

https://serverless-stack.com/


``` shell
Cognito:
  Pool Id us-east-1_75YbjIjDN
  Pool ARN arn:aws:cognito-idp:us-east-1:296341624178:userpool/us-east-1_75YbjIjDN
  App client id: 574taeqhpe3c2oh6350hstkdo0

Identity pool id: us-east-1:61af9286-a459-4d5a-97e8-14461bdafb9b 
```

``` shell

serverless invoke local --function create --path mocks/create-event.json
serverless invoke local --function get --path mocks/get-event.json
serverless invoke local --function list --path mocks/list-event.json
serverless invoke local --function update --path mocks/update-event.json
serverless invoke local --function delete --path mocks/delete-event.json

# To confirm a user
aws cognito-idp admin-confirm-sign-up \
   --region us-east-1 \
   --user-pool-id YOUR_USER_POOL_ID \
   --username YOUR_USER_EMAIL
```

``` shell

apig-test \
--username='admin@example.com' \
--password='Passw0rd!' \
--user-pool-id='us-east-1_75YbjIjDN' \
--app-client-id='574taeqhpe3c2oh6350hstkdo0' \
--cognito-region='us-east-1' \
--identity-pool-id='us-east-1:61af9286-a459-4d5a-97e8-14461bdafb9b' \
--invoke-url='https://yq9q4rytd6.execute-api.us-east-1.amazonaws.com/prod' \
--api-gateway-region='us-east-1' \
--path-template='/notes' \
--method='POST' \
--body='{"content":"hello world","attachment":"hello.jpg"}'