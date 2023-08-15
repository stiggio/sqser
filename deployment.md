# Sqser
---

<img src="https://i.ibb.co/3RgfdPD/sqser.png" width="250" height="250">

# How is SQSer deployed in Stigg?


## IAM role
Sqser has its onw apikeys with role that allows all sqs operations as it needs to both read write, list etc

## Heroku
Sqsers master is automatically deployed to heroku. It uses in the env the api key of the correct iam role.
note, that aws zone is set need to be set as env var as well.

## Slack api (webhooks+commands)
We have an app with commands that are calling the sqser and also webhooks to send messages back

## Scheduler
We use event bridge to dispatch a daily list command to sqser so we can get the queues status in the mornings.

