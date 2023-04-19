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
### High level design
  1. when user request something then ofcourse that request will be going to server & that too not a single server for which will require multiple servers which can be handle by load balancer
  ![image](https://user-images.githubusercontent.com/71604396/233182405-8303f9ab-888b-4e8e-8985-8d9b2b16fa32.png)
  2. Now user is uploading video then applicatio need to store it somewhere like any object storage such as aws s3
  ![image](https://user-images.githubusercontent.com/71604396/233183834-1401c327-2026-4ce2-9770-fdca891f1bc1.png)
  3. Once video is uploaded,but what about all meta-data linked to the video(title,description,uid)? we can store it in any DB.Let us assume any noSql db in which we can have two collections
    - user collection
    - video collection
  ![image](https://user-images.githubusercontent.com/71604396/233185830-71c8c8bb-513d-41a4-9339-c3149da6934c.png)
