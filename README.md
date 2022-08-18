#50 years of the Billboard HOT 100
Kelly Harthan

**Still need to revise and add links. Wanted to get this version pushed up now. Will be polished/ finished in the next hour or two.

###Motivation [Go to Motivation](#Motivation)
###Data Sources
Data Questions
Technologies
The Process
The Dashboard


##Motivation [Go to Motivation](#Motivation)
I have loved music for as long as I can remember. Even before I could play or sing, I used to write poems and songs. I started playing music in my late teens and have continued down the road songwriting and telling stories. Music was what initially bought me to Nashville.

The Billboard HOT 100 is one of the most popular and longest running music charts used today being on it’s 64th year. It is such a wealth of knowledge regarding the most popular tracks over the past six to seven decades.  Billboard alone can tell you a lot about the popular artists and music styles of the day. However, there was a golden opportunity in combining that history with Spotify’s ‘Audio Features’ to do a more thorough analysis of the musical elements of each of the tracks, With this combination we could get a more thorough understanding  the changes the actual music structure over time.

Data Sources
[Billboard] (https://www.billboard.com/charts/hot-100/)
-	Spotify
o	Spotify for Developers
o	Audio Features
o	Track Info
o	Artist Info
o	Genre’s
o	Playlists

Data Questions:
1.	Can we use Spotify’s ‘Audio Features’ to identify trends in popular music over the last 50 years?
2.	What are the most significant musical elements determining charting tracks?
3.	Are there differences in the presence of these core audio elements when looking at the top 100, top 10 and the chart-topping artists?
4.	What do genres tell us about the post popular music styles?

Technologies
Python
o	Jupyter Notebooks
o	Pandas
o	Requests
o	Ittertools
o	numpy
o	Spotipy
Power BI
o	Custom Visuals

The Process

-	Getting the Data
The initial process started with doing a web scrape of the HOT 100 Billboard hits. Once I had the list was ready to move to Spotify to start pulling the artist/ track info through that system.

Working With Spotify: To have access to the information the audio features, track and artist info that I was seeking, I first needed to register as a developer with Spotify and set up an app to get the proper credentials to  access the information in the Spotify Console for Developers. This whole process what a bit clunky and it appears that Spotify makes pretty regular updates to this process as a little of the literature was a little out of date to successfully get Python to recognize the credentials.

After authorization was secured, the next step was to start looing through the console to find which information that I would like to utilize. The system of looking through the options for exploring artists, playlists, albums etc. was straightforward as Spotify supplied a URL which only needed a unique Spotify identifier code (artist, track, playlists) These links were only set up to handle a single identifier at a time. I was able to set up a series of code that would allow the identification numbers to be looped through the list.

Now came the tricky part… I had to figure out how to get Spotify to recognize that artist/ track names to connect with the proper id’s to be able to run that data through the console. After some digging I was able to find a search option that let you put in a name instead of the id number. If I could generate the id’ I could merge that together with the list and I would be set to go. This was when I started to uncover two additional roadblocks, the naming conventions between the two sites  varied and that would return inaccurate results. The second problem was that each song had multiple tracks (variations of that track listed) and I would have to write code that could identify the correct track. I was able to do this witch success using a ‘popularity’ score on the top track, however, I couldn’t get through the web scrapped list.
I had to take a step back, and I had to rethink and look at this through a different lens.

-	Getting the Data (again)

After a little bit of searching, it turned out that Spotify actually has playlists of the Billboard Top 100 for almost every year since it began. Hallelujah we were back in business! This was a great learning opportunity for me to remember to put in the time upfront and look at all options. When you get stuck, do it again. I was able to take already created Spotify playlists and pull in the tracks I wanted through the console. In hindsight, I am glad that I had this debacle. It helped me to remember to slow down and to look at ALL options. This cut a lot of code and editing out of the process in the end.

After getting the complied lists, I needed to start pulling in the data. From here I pulled in Spotipy. Spotipy  is a lightweight Python library for the Spotify Web API. With Spotipy you get full access to all of the music data provided by the Spotify platform with out having to dig through multiple layers of dictionaries.

-	Clean, Prepare and Analyze

Link to the Dashboard
[50 years of the Billboard HOT 100[ (https://app.powerbi.com/view?r=eyJrIjoiNjg0Yjk3ZTItOTQyYy00YTNkLWFmZTQtZWE0ZTQxNmE3N2FjIiwidCI6IjEwMWRhNTg3LTE4NDMtNGY1Mi04YjhhLTE3YjA2OWM2NmQzMyIsImMiOjJ9)

![myImage](https://media.giphy.com/media/XRB1uf2F9bGOA/giphy.gif)
