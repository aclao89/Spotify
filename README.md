## Visualizing Spotify Data with Python and Tableau

![spotify](https://github.com/aclao89/Spotify/blob/main/spotify_header.jpg)

We live in the era of big data. We can collect lots of data which allows to infer meaningful results and make informed business decisions. However, this comes with some trade-offs. As the amount of data increases, it gets trickier to analyze and explore the data.

There comes in the power of visualizations which are great tools in exploratory data analysis when used efficiently and appropriately. Visualizations also help to deliver a message to your audience or inform them about your findings. There is no one-fits-all kind of visualization method so certain tasks require different kinds of visualizations.

Spotify is a Swedish audio streaming and media services provider founded on 23 April 2006 by Daniel Ek and Martin Lorentzon. It is the world's largest music streaming service provider, with over 381 million monthly active users, including 172 million paying subscribers, as of September 2021.

I have been a Spotify subscriber for over 10 years; I became curious of my music preferences and listening habits. Althought I did not need to do this analysis to determine that I love to listen to comedy/horror podcasts such as [Last Podcast on the Left](https://www.lastpodcastontheleft.com/) or upcoming hip-hop/R&B Canadian duo [Manila Grey](https://www.manilagrey.com/), I felt it would be a fun project to learn about Spotify API and their developer platform.

Tools used: Jupyter Notebook with data manipulation libraries and Tableau Public for data visualizations.

### Step 1: Request your Data

Request your copy of Spotify data using this [link](https://www.spotify.com/us/account/privacy/). Scroll down to request your data and confirm the request via your email (registered with Spotify). It may take a while to receive your data (took about a week for me); check your email for the download link.

![request_data](https://github.com/aclao89/Spotify/blob/main/Imgs/step1.PNG)

### Step 2: Data Cleaning

Once you received the files from Spotify, we will create one dataframe that includes all streaming data whether each song is on our library and each song's Spotify 'URI' - which is unique identifier.

![create_stream](https://github.com/aclao89/Spotify/blob/main/Imgs/read_files.PNG)

Here, I created an "Unique ID" by combining the artistName + trackName

![merge](https://github.com/aclao89/Spotify/blob/main/Imgs/merge_dfs.PNG)

Received an error when I tried to read in the 'YourLibrary1.json' file. I had to go in to manually delete the "albums" dictionary so it would be able to merge correctly with the "df_combined" dataframe.

![read_lib](https://github.com/aclao89/Spotify/blob/main/Imgs/read_lib.PNG)

Next, I created a 'track_uri' column which is the 'uri' column but stripped "spotify:track:".

![uri](https://github.com/aclao89/Spotify/blob/main/Imgs/split_uri.PNG)

Lastly, I merged the library and streaming dataframes

![merged_last](https://github.com/aclao89/Spotify/blob/main/Imgs/merge_lib_stream.PNG)
