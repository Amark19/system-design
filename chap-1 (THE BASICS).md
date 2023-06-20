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

# services
## monolith
Entire application is built as single unity no separated units are decomposed here unlike microservices.Whole business unit,logic is in same application.

## microservices
application basically decomposed/separate into collection small services.They can communicate with each other via API's.These are loosely coupled services.Separate services for separate unit of buisnesses.

# Networking
## Tcp/ip model
It is an improved version of OSI model
- Application layer :- end-to-end communication e.g. http/https protocols are best e.g. for application layer.
- Transport layer(tcp layer) : breaks data to chunks,trasfers it character by character & retransmits the data if data do not received.Initiate connection -> communicate with other applicaiton->close connection
- network layer/internet layer(ip) :- data sent in chunks from transport layer it basically assigns ip to it i.e showing a way to which direction to move & where to go (pirate of ship 😆)
- data link layer :- data framing and error prevention
- physical layer :- generates data and requesting connection 

## DNS
Domain name system?why do we need it ?we know data exchange is always between ip's ryt?each website has its unique ip address but remembering ip of each website isn't it so hard task ? That's where domain name comes where mapping ip to domain name is to be done 256.123.980 -> example.com .
When we type any domain in browser ,browser contacts to it dns provider gets ip then request files that are stored in resp. ip server .
But isn't it so redundant work ?everytime making request to domain name provider & asking about ip?then in that case browser cache these ip so that it do not have to perform this task again.

## http request 
application level protocol helps us to request files,data from server that follows client-server model.While sending this request it has something as request head which has all information such as whom to request,ip that is requesting.Also has request body which holds the actual data that is requested or recieved

![image](https://user-images.githubusercontent.com/71604396/230789033-d3e8f143-3493-403c-af0f-84d7b5a67473.png)

## REST API
It is api service to exchange data between two machines.Like it has few methods such as
- get :- to get/fetch all data from web service
- post :- send data to web service

## graphQL
api service introduced by facebook in 2015.Instead of making api calls for pull or push data to server here we make one single query & then select what all resources you want from response.

## websockets
- Type of protocol which is helpful to handle realtime data.ohhh what is realtime data ?It can be any continuous stream of data such as we get from chat application.
- In chat application,at every second users send message to other users.So how can we handle that ? using api request ? that means at every second making api request & then requesting it from db to show msg to other users,isn't is so costlier?
- websockets helps us to send or retrieve data within a single request no need to send multiple request at each update or message.

# Database
## SQL
structure query language which helps us to make database query.Mysql is a database that uses sql as language to make query to stored,pull,insert data

## ACID
- Atomicity :- all or everything i.e either transaction take place or not take place,can't be partial transaction
- consistency :- data should be consistent that mean if user is withdrawing money then it should be reflected to all the bank servers
- isolation :- concurrent or parallel transactions/queries should not cause conflicts
- durability :- data once updated or added it should never be lost by database

## NoSQl
non relation database that means data will not be stored in fixed tables either it can be stored as graph nodes,documents e.g firebase firestore,mongodb

## Cap theorem
- consistency :- every node in network should see same data
- availability :- every request should get response..d
- parition reference :- system should work continuously even if there are some failures as well
fun fact :- cap thm itself says that we can only achieve 2 of these among 3
