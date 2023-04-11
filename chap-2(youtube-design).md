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
