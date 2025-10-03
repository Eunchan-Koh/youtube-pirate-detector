# youtube-pirate-detector
# Problem Statement
My mother is running a youtube channel, and she is suffering because of ai pirates who steal her videos, thumbnails and even titles to upload those videos on their channel. This already happened at least three times so far, so I have decided to work on this problem.  

# How does it work?
I have checked that ai pirates mostly take the videos but still maintain the title's meaning. They are not exactly the same as the original video, but the title does not change that much and meaning always stays constant. Also, I have checked that pirated videos always were the most popular videos in my mother's channel. Hence, I decided to use these points to detect ai pirates. Simply get all videos from my mother's channel and search titles of all those videos using youtube api to see if there is other videos than my mother's videos! If the titles are almost the same, than those will be suspicious videos for me.

# What process?
1. The system will get around 20~50 videos from my mother's channel. The order of the videos will be in number of views.
2. Search one video title on youtube and get up to 5 videos from the search using the youtube data v3 api
   - If the owner of the video is my mother, ignore that video. If not, collect them into a temporary list.
3. Compare each searched videos' title with the original video's title from my mother's channel using Embedding model & cosine similarity
   - If the similarity is over 90%, it could be having almost the same title. show the title and url of the video on the console. Also display the title and url of the original video so it is easier to compare manually as well.
4. Repeat step 2~3 for the all rest of the videos from my mother's channel.

# Hard points/ Limits?
Youtube data v3 api has a usage limit per day, and this cannot be increased without permission from google side. I thought I will be able to grant more quotas for this if I have a method to pay, but it was not how it works for the youtube api. So...initially, I wanted to scan and search for all videos in my mother's channel, but that made me run out of the daily quota so easily. That made me consume another day to complete making this system since I could not test any further.

# point of improvement?
A lot of improvements can be made. For example...  
I can try to get some api that reads the subtitle or creates a script(subtitles) once a video link is given so make ai check if the scripts have the similar information for the first 1 minute. By doing so, I don't even have to manually check the suspicious videos by myself.  
Also, I can try to add the database since the most popular video in my mother's channel won't change every single day. Making a system that updates the database only when changes have been detected will allow me to save the youtube api daily quota and embedding model token usage.  

# Does it work?
well, when I previously searched the original video's title, I could find the ai pirate's video right away. However, No videos have been pirated after making this system, so could not check it yet. I will see if it works in the future, running this system once every week.
