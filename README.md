# 50 Years of the Billboard HOT 100
---

- [Motivation](#motivation)
- [Data Sources](#data-sources)
- [Data Questions](#data-questions)
- [Technologies](#technologies)
- [The Process](#the-process)
- [Dashboard](#dashboard)

---
## Motivation 
I have loved music for as long as I can remember. Even before I could play or sing, I used to write poems and songs. I started playing music in my late teens and have continued down the road songwriting and telling stories. Music was what initially bought me to Nashville about two years ago. When I had the opportunity to dig into any topic, music was a natural first choice.

The Billboard HOT 100 is one of the most popular and longest running music charts used today currently being in it’s 64th year. It is a wealth of knowledge regarding the most popular tracks over the past six to seven decades.  Billboard alone can speak volumes about the popular artists and music styles of the day. However, it does not have the capacity to analyze the music itself for broader changes in composition. 

Enter Spotify. Spotify is a digital music, podcast, and video service that gives you access to millions of songs and other content from creators all over the world. With digitalization and adavnced alogorythms, we are able to look at and understand music in a whole new way. The algorithm used leverages Convolutional Neural Networks that use clustering to identify similarities in time signature, key, mode, tempo and loudness based on its audio waveform. This is done per-track, so it is easy to compare across genres and time analyzing the differnces in features such as timing, key, tempo, energy, etc.

These two data sources provided an exciting opportunity to combine the history and statistics found in the annual Billoard HOT 100, with Spotify’s ‘Audio Features’ to understand at a deeper level the musical elements of each track and across time. 

---
## Data Sources
- [Billboard](https://www.billboard.com/charts/hot-100/)
- [Spotify](https://developer.spotify.com/)
  -	Spotify for Developers
  -	Audio Features
  -	Track Info
  -	Artist Info
  -	Genre’s
  -	Playlists
 
---
## Data Questions:
1.	Can we use Spotify’s ‘Audio Features’ to identify trends in  the most popular music reported by the Billboard HOT 100 over the last 50 years?
2.	What are the most significant audio features determining charting tracks?
3.	Are there differences in the presence of these core audio elements when looking at averages of the top 100, top 10 or the chart-topping artists?
4.	What does the popularity of genres tell us about the progression popular music styles over the decades?

---
## Technologies
- [Python](https://www.python.org/)
- [Jupyter Notebooks](https://jupyter.org/)
- [Pandas](https://pandas.pydata.org/)
- [Requests](https://pypi.org/project/requests/)
- [Ittertools](https://docs.python.org/3/library/itertools.html)
- [NumPy](https://numpy.org/)
- [Spotipy](https://spotipy.readthedocs.io/en/master/)
- [Power BI](https://powerbi.microsoft.com/en-us/)
- [Custom Visuals- ImgViewerVisual.0.1.0](https://blog.pragmaticworks.com/power-bi-custom-visuals-image-viewer)

---
## The Process

### Getting the Data

The initial process started with doing a web scrape of the HOT 100 Billboard hits. Once I had the list was ready to move to Spotify to start pulling the artist/ track info through that system.

Working With Spotify: To have access to the information the audio features, track and artist info that I was seeking, I first needed to register as a developer with Spotify and set up an app to get the proper credentials to  access the information in the Spotify Console for Developers. This whole process what a bit clunky and it appears that Spotify makes pretty regular updates to this process as a little of the literature was a little out of date to successfully get Python to recognize the credentials.

After authorization was secured, the next step was to start looing through the console to find which information that I would like to utilize. The system of looking through the options for exploring artists, playlists, albums etc. was straightforward as Spotify supplied a URL which only needed a unique Spotify identifier code (artist, track, playlists) These links were only set up to handle a single identifier at a time. I was able to set up a series of code that would allow the identification numbers to be looped through the list.

Now came the tricky part… I had to figure out how to get Spotify to recognize that artist/ track names to connect with the proper id’s to be able to run that data through the console. After some digging I was able to find a search option that let you put in a name instead of the id number. If I could generate the id’ I could merge that together with the list and I would be set to go. This was when I started to uncover two additional roadblocks, the naming conventions between the two sites  varied and that would return inaccurate results. The second problem was that each song had multiple tracks (variations of that track listed) and I would have to write code that could identify the correct track. I was able to do this witch success using a ‘popularity’ score on the top track, however, I couldn’t get through the web scrapped list.
I had to take a step back, and I had to rethink and look at this through a different lens.

### Getting the Data (again)

After a little bit of searching, it turned out that Spotify actually has playlists of the Billboard Top 100 for almost every year since it began. Hallelujah we were back in business! This was a great learning opportunity for me to remember to put in the time upfront and look at all options. When you get stuck, do it again. I was able to take already created Spotify playlists and pull in the tracks I wanted through the console. In hindsight, I am glad that I had this debacle. It helped me to remember to slow down and to look at ALL options. This cut a lot of code and editing out of the process in the end.

After getting the complied lists, I needed to start pulling in the data. From here I pulled in Spotipy. Spotipy  is a lightweight Python library for the Spotify Web API. With Spotipy you get full access to all of the music data provided by the Spotify platform with out having to dig through multiple layers of dictionaries.

### Clean, Prepare and Analyze

---
## Dashboard
[50 years of the Billboard HOT 100](https://app.powerbi.com/view?r=eyJrIjoiNjg0Yjk3ZTItOTQyYy00YTNkLWFmZTQtZWE0ZTQxNmE3N2FjIiwidCI6IjEwMWRhNTg3LTE4NDMtNGY1Mi04YjhhLTE3YjA2OWM2NmQzMyIsImMiOjJ9&pageName=ReportSection)

![myImage](https://media.giphy.com/media/XRB1uf2F9bGOA/giphy.gif)
