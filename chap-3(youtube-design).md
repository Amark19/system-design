# Youtube
## functional requirements
- users can upload videos
- users can watch videos

## Non functional requirements
- reliability
  - user should never faced issue while uploading videos
  - uploaded video should never get corrupt or deleted by yotube
- scalability
  Assumptions,
  - one videos parallelly can have 1000's of users
  - 1 Billion active users / day
  - a user watching 5 videos on avg/day
  - total 5 billion users watching a video
  - upload ratio 1:100 (for every 100 users who r watching video 1 is uploading video) (read:write)
  - that means 50 million video is been uploaded
- Availability
  - everytime user refreshes videos they should see some results that is 200 status
- latency
  - ofc we have to minimize it
  - user should see quick response for each actions
  - clicking on video should play that video immediately
## Let's design this system,
## uploading video

  1. when user request something then ofcourse that request will be going to server & that too not a single server for which will require multiple servers which can be handle by load balancer
  
  ![image](https://user-images.githubusercontent.com/71604396/233182405-8303f9ab-888b-4e8e-8985-8d9b2b16fa32.png)
  
  2. Now user is uploading video then applicatio need to store it somewhere like any object storage such as aws s3
  
  ![image](https://user-images.githubusercontent.com/71604396/233183834-1401c327-2026-4ce2-9770-fdca891f1bc1.png)
  
  3. Once video is uploaded,but what about all meta-data linked to the video(title,description,uid)? we can store it in any DB.Let us assume any noSql db(MongoDb) in which we can have two collections
    - user collection
    - video collection(video title,video description etc)
    - adantage of using nosql is we don't have to perform join operation between videos and video information instead we can achieve this by reference
    
  ![image](https://user-images.githubusercontent.com/71604396/233185830-71c8c8bb-513d-41a4-9339-c3149da6934c.png)
  
  4. These uploaded video can be in bigger size so youtube here performs encoding algorithm so that youtube videos size can be reduced and these task done asynchronously as it is not done in seconds can take up to minutes or hours maybe.
    - So, here to achieve this,videos can be added to queues so that it can be encoded further one by one
    - again we can have object storage in which can store these encoded formatted videos
    
  ![image](https://user-images.githubusercontent.com/71604396/234965172-a96a3abe-b0ba-4da0-9405-46c9f4edfdaf.png)

## Watching video
 1. use of cdn
   - we know that users are not reading whole raw video instead they will be fetching encoded format of video later be decoded
   - And to avoid multiple calls to object storage we can have cdn
   - whole of these static files(video,images etc) can be served,distributed over network using cdn

  ![image](https://user-images.githubusercontent.com/71604396/234970661-108e7ddd-8758-4b92-aaa7-9bbded71dd51.png)
  
2. use of cache
    - storing most viewed videos,latest uploaded videos in front database that is in cache memoery for faster access of such videos

  ![image](https://user-images.githubusercontent.com/71604396/234971923-98e8836c-7665-401c-952e-9a9f49b23b5c.png)


