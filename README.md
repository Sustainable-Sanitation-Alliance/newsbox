# Sanitation Network Circle Newsfeed
### Documentation
With the Sanitation Network Circle Newsfeed, news can be exchanged within the network and published bundled on websites. The feed can be accessed via the SuSanA website and can be displayed with any feed reader and adapted to the layout of the website.
  
**Copyright notice: 
We ask for the following notice within the display of the Network Circle Newsfeed.  
Source: Sanitation Network Circle Feed, provided by SuSanA - https://www.susana.org**
  
  
In this documentation, you will learn
2. understand the basic structure of the RSS
3. add useful elements to the feed using the configuration file
4. how to design your feed according to our guidelines and examples
5. create your own feed for
  

# Integration of the feed

You can find the current feed at the following URL and thus embed it in an existing web application.  
https://api.susana.org/newscircle/rss/sanitation_circle.rss

The extended description and documentation of available channels and categories can be found in the current configuration file  
https://api.susana.org/newscircle/config.json

Until the API is released in early May 2023, please use the example files provided in this documentation for development purposes
- example_output.rss
- example_config.json
  
  
## Feed items
The following information is available within an item of a channel
  
### title ### 
Text

### link ### 
Text

### description ### 
Text  
**Important note: HTML & script elements will be removed.

### pubDate ###
Text

### source ###
Abbreviation of the source (organisation) of the entry.
**Important note: The abbreviation used here describes the organisation through which the entry was made available. The links and descriptions of the organisations can be found in the extended configuration parameters of config.json**.


### author ###
Text


### category ###
Text

### guid ###
Text

### enclosure ###
Text



## Extended configuration parameters

The configuration file provides important information about the Sanitation Network Circle Neewsfeed in JSON format.

### Read out available categories

### Available Categories



## Channels & Categories 

You can also retrieve the categories and channels named in the current config.json as a separate feed.