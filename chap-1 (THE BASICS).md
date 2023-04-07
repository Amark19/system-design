# Scaling

## vertical scaling
client makes request to server & server respond it back but lets suppose load on server is increasing exponentially or linearly then our application will face down time or work slowly.Then to overcome this problem we add
extra cpu's ,increase ram in our server to serve request faster.

## Horizontal scaling
By considering above scenario what if our server is down due to some issues? Then that means our application is also down ryt ? Don't you think we r so much reliable to only one server ?Yess we are
then in that case we distribute our servers in multiple locations or I can say we create replicas of our application in multiple locations so that if one server is down then user's request can be fulfill by other servers.
Eliminates single point of failure.

![image](https://user-images.githubusercontent.com/71604396/230620668-4e96c4a8-4913-4b08-ad16-3dabeb8da176.png)

## load balancer
We understood that horizontal scaling is better than vertical but what if most of the request sent to only one server then in that case sever will be overloaded ryt ? So,in that case load balancer plays vital role where it make sures that request get evenly spread within all the server for which it uses round robin algorithm

![image](https://user-images.githubusercontent.com/71604396/230664368-2285aded-09be-4eb6-ba53-fff8e514cf12.png)

## cdn (content delievery network)
cdn helps us to serve static files such as images,videos & html/css/js files.SO all these files is stored into one server which basically serves or copies these files to another servers.CDN helps to cache the content that are closer to end users.Let us suppose you have one website which has assets such as images etc. which takes some time to request from servers & load it.Then to overcome this issue cdn helps us to cache these files in cdn server can be accessed quicker.

## caching
caching is basically storing data in cache memory that is requested quite frequently to reduce load time.

# Networking
