## Architecture for std application

1. client/server request
  - developer creates then push the code to server from local repo
  - ci/cd helps developer to test projects in prod & validates the pushed codee
  - server can be connected to external storage or database via network i.e distributed storage
  - user makes request & get the response via js,html,css files or it can be only api based server where user makes request and they get json data in response
  
  ![image](https://user-images.githubusercontent.com/71604396/235223387-3edb09ff-7675-409f-b768-2197a6734905.png)

2. Vertical scaling
  - increasing configuration of ram & cpu to improved load time,decrease latency 

  ![image](https://user-images.githubusercontent.com/71604396/235224046-cead741d-4fd8-42f9-9dee-4ad1ff8c7bca.png)

3. Horizontal scaling
  - Vertical scaling can cause single point of failure instead we can use horizontal scaling
  - In this,instead increase conf we increase number of servers that are distributed servers maintaned by load balancer

  ![image](https://user-images.githubusercontent.com/71604396/235225002-c9f365c3-e1f0-447d-a8c2-c3257aeb8de5.png)

4. External APi & services
  - A server may have to communicate with other services such as api service or cdn servers

  ![image](https://user-images.githubusercontent.com/71604396/235225570-e7f38aec-2487-4223-a3e0-ac7f8a9e4687.png)

5. logging services
  - Logs are very important for developer perspective(stores all activity to server i.e load time,latency,bandwidth,failures)
  - These logs are not stored in server instead it is stored in different services that can be retrieved

  ![image](https://user-images.githubusercontent.com/71604396/235226515-75ee3c7b-71f5-48dd-a78d-ef0269922502.png)

6. metrics & alerts
  - Metrics provides insights about how well server responding?is it using resources properly?utilizing cpu very well etc
  - If something wrong happening to server then do we have to traceback or will user tells us?No in such time Alerts pushes notification if there is some critical error occuring
  - such as if metrics has reached some threshold then alert will recognize it and send notification to developers.
  ![image](https://user-images.githubusercontent.com/71604396/235227651-bba00611-aef5-4b00-b1af-c5594a931f28.png)
