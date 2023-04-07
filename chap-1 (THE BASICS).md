# Scaling

## vertical scaling
client makes request to server & server respond it back but lets suppose load on server is increasing exponentially or linearly then our application will face down time or work slowly.Then to overcome this problem we add
extra cpu's ,increase ram in our server to serve request faster.

## Horizontal scaling
By considering above scenario what if our server is down due to some issues? Then that means our application is also down ryt ? Don't you think we r so much reliable to only one server ?Yess we are
then in that case we distribute our servers in multiple locations or I can say we create replicas of our application in multiple locations so that if one server is down then user's request can be fulfill by other servers.

![image](https://user-images.githubusercontent.com/71604396/230620668-4e96c4a8-4913-4b08-ad16-3dabeb8da176.png)

## load balancer
