# Sanitation Network Circle Newsfeed
### Documentation
With the Sanitation Network Circle Newsfeed, news can be exchanged within the network and published bundled on websites. The feed can be accessed via the SuSanA website and can be displayed with any feed reader and adapted to the layout of the website.
  
---   
**Copyright notice: 
We ask for the following copyright link within the display of the Network Circle Newsfeed.  
Source: Sanitation Network Circle Feed, provided by SuSanA - https://www.susana.org**
  
---    
In this documentation, you will learn  
+ understand the basic structure of the RSS  
+ add useful elements to the feed using the configuration file  
+ how to design your feed according to our guidelines and examples  
+ create your own feed for  
  
  
# Integration of the feed

You can find the current feed at the following URL and thus embed it in an existing web application.  
https://api.susana.org/newscircle/rss/sanitation_circle.rss

The extended description and documentation of available channels and categories can be found in the current configuration file  
https://api.susana.org/newscircle/config.json

Until the API is released in early May 2023, please use the example files provided in this documentation for development purposes
- example_output.rss
- example_config.json

## Header of the feed
In the header of a channel you will find the title, a short description and the time of the last update of the channel.
  
## Item tags inside the feed
The following information is available within an item of a channel
  
### title ### 
Title of the feed entry as it should be displayed on the external web pages. Maximum length of 256 characters 

### link ### 
URL of the web page to which the read more button should point.

### description ### 
Description of the entry. We recommend a maximum length of 350 characters to avoid automatic shortening of the description text on the external websites where the feed is embedded.  
**Important note: HTML & script elements will be removed.**

### pubDate ###
Time of publication of the feed entry. Note: The output of the channel is already sorted in descending order by this date field. 

### source ###
Abbreviation of the organization providing the entry. **Important note:** The abbreviation used here describes the organisation through which the entry was made available. The links and descriptions of the organisations can be found in the extended configuration parameters of config.json.

### author ###
Name of the author who wrote the article. We ask that this be taken into account in the output.

### category ###
Category of the entry. You can use it to filter the output of the feed on your website by these categories. **Note:** All available categories can be found in config.json. You can also generate a separate explicit RSS feed for each category using a URL. Use the following syntax in the call https://api.susana.org/newscircle/rss/category/{category}.rss.  
You can also find all URLs within the configuration file.

### guid ###
Unique URL with ID, with the help of which they avoid duplication in the output and caching of feeds.

### enclosure ###
Optionale Verknüpfung einer Bild- / Video-Datei über eine URL innerhalb des jeweiligen Eintrages. Weitere Hinweise finden Sie auf: https://cyber.harvard.edu/rss/rss.html#ltenclosuregtSubelementOfLtitemgt 



## Extended configuration parameters

The configuration file provides important information about the Sanitation Network Circle Neewsfeed in JSON format.

### Read out available categories

### Available Categories



## Channels & Categories 

You can also retrieve the categories and channels named in the current config.json as a separate feed.