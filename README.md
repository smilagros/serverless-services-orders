# Serverless REST API


## Structure

This service has a separate directory for all the todo operations. For each operation exactly one file exists e.g. `services-orders/delete.js`. In each of these files there is exactly one function which is directly attached to `module.exports`.

The idea behind the `services-orders` directory is that in case you want to create a service containing multiple resources e.g. users, notes, comments you could do so in the same service. While this is certainly possible you might consider creating a separate service for each resource. It depends on the use-case and your preference.

## Use-cases

- API for a Web Application
#Create


1 mkdir ServicesOrdersAPI
2 cd ServicesOrdersAPI
3 serverless create --template aws-nodejs -name services-order-api
4 npm init -y
5 serverless deploy

## Deploy



## Usage

You can create, retrieve, update, or delete services-orders with the following commands:

### Create  


curl -X POST https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/create --data '{ "text": "Learn Serverless" }'


Example Result:

{"text":"Learn Serverless","id":"ee6490d0-aa11e6-9ede-afdfa051af86","createdAt":1479138570824,"checked":false,"updatedAt":1479138570824}%


### List all services-orders


curl https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/services-orders


Example output:

[{"text":"Deploy my first service","id":"ac90feaa11e6-9ede-afdfa051af86","checked":true,"updatedAt":1479139961304},{"text":"Learn Serverless","id":"206793aa11e6-9ede-afdfa051af86","createdAt":1479139943241,"checked":false,"updatedAt":1479139943241}]%


### Get one Todo


# Replace the <id> part with a real id from your services-orders table
curl https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/services-orders/<id>


Example Result:

{"text":"Learn Serverless","id":"ee6490d0-aa11e6-9ede-afdfa051af86","createdAt":1479138570824,"checked":false,"updatedAt":1479138570824}%


### Update  


# Replace the <id> part with a real id from your services-orders table
curl -X PUT https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/update/<id> --data '{ "text": "Learn Serverless", "checked": true }'

curl -X PUT https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/update/{1} --data "{ \"text\": \"Learn Serverlesss\", \"checked\": true }"



Example Result:

D:\AZUMHER\SAM\sam-services-orders>curl -X PUT https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/update/{1} --data "{ \"text\": \"Learn Serverlesss\", \"checked\": true }"
{"checked":true,"text":"Learn Serverlesss","id":"1","updatedAt":1549947202904}
D:\AZUMHER\SAM\sam-services-orders>curl -X PUT https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/update/{1} --data "{ \"text\": \"Susana Learn Serverlesss\", \"checked\": true }"
{"checked":true,"text":"Susana Learn Serverlesss","id":"1","updatedAt":1549947216254}
D:\AZUMHER\SAM\sam-services-orders>curl https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/list
[{"checked":true,"text":"Learn Serverlesss","id":"2","updatedAt":1549917384634},{"checked":true,"text":"Susana Learn Serverlesss","id":"1","updatedAt":1549947216254},{"checked":false,"createdAt":1549917135720,"text":"Learn Serverless","id":"1e907590-2e3c-11e9-a843-877376d39a2d","updatedAt":1549917135720}]
D:\AZUMHER\SAM\sam-services-orders>


### Delete


# Replace the <id> part with a real id from your services-orders table
curl -X DELETE https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/services-orders/<id>
curl -X DELETE https://4a3plrgux1.execute-api.us-east-1.amazonaws.com/dev/delete/<1>
# serverless-services-orders
# serverless-services-orders
