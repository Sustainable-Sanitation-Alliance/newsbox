# Network Circle Newsbox (NCN)
### Documentation
With the Sanitation Network Circle NE, news can be exchanged within the network and published bundled on websites. The feed can be accessed via the SuSanA website and can be displayed with any feed reader and adapted to the layout of the website.
  
---   
**Copyright notice: 
We ask for the following copyright link within the display of the Network Circle Newsfeed.  
Source: Sanitation Network Circle Feed, provided by SuSanA - https://www.susana.org**
  
---    
In this documentation, will show you to  
+ understand the basic structure of the RSS and add useful elements to the feed using the configuration file  
+ design your feed according to our guidelines and examples  
+ participate and create your own feed   
  
                       
					                   
									     
										   
# 1. Integration of the feed

You can find the current feed at the following URL and thus embed it in an existing web application.  
https://api.susana.org/newscircle/rss/sanitation_circle.rss

The extended description and documentation of available channels and categories can be found in the current configuration file  
https://api.susana.org/newscircle/config.json

Until the API is released in early May 2023, please use the example files provided in this documentation for development purposes
- example_output.rss
- example_config.json

## 1.1. Header of the feed
In the header of a channel you will find the title, a short description and the time of the last update of the channel.
  
## 1.2. Item tags inside the feed
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
Optional linking of an image / video file via a URL within the respective entry. You can find further notes at: https://cyber.harvard.edu/rss/rss.html#ltenclosuregtSubelementOfLtitemgt 



## 1.3. Extended configuration parameters

The configuration file provides important information about the Sanitation Network Circle Neewsfeed in JSON format.

### Sources - additional partner information
Within this object all participating partner organizations can be found. These abbreviations (orgAbbrev) are outputs in the source tag of the items in the newsfeed and can thus also be filtered. 

Here you can find the name and a description [orgDescription] of the partner organization, the link to the website [orgUrl] and a URL to the logo [orgLogo] of the organization, which you can use on your website. 
  
In addition, the number of current posts [orgActualPosts] can be found within the NCN feed from this source and also the timestamp [orgLastBuildDate] of the last update.  
      
In addition, it is possible to retrieve an explicit source via URL. api.susana.org/newscircle/rss/{source}.rss.  


### Categories

**categoryName**  
Name of the yategory  
  
**categoryDescription**  
Description of the category   

**categoryFeedUrl**  
The URL for to get the RSS feed only with items of this category 
  
**categoryActualPosts**  
Number of actual items inside this category feed  
  
**categoryLastBuildDate**  
Timestamp of the latest post inside the category feed

### Channels

Note: The object identifier contains the alias name of the channel.  

**channelName**  
Name of the channel  
  
**channelDescription**  
Description of the channel  
  
**channelFeedUrl**  
The URL for to get the RSS feed only with items of this channel  

**channelActualPosts**  
Number of actual items inside this channel feed   

**channelLastBuildDate**  
Timestamp of the latest post inside the channel feed
  
  
    
## 1.4. Targeted API calls to categories and channels

You can also retrieve the categories and channels named in the current config.json as a separate feed.

To do this, use the category as the file name for the RSS feed within the URL according to the following scheme.  
https://api.susana.org/newscircle/rss/category/[categoryName].rss

And for the channels the scheme:  
https://api.susana.org/newscircle/rss/channels/[example_channel_alias].rss  
  
    
	  
	  
---  

# 2. Designing the newsfeed output

The following fields should be displayed within the feed on the web page.
Source (Abbreviation of the partner organization) 
Publishing date 
Author of the article / post
Title
Description

We recommend a presentation according to the following scheme:

[ pubDate ] by [ author ]  
[ title ]  
[ source ]: [ description ]  
  
The description should be shortened to 350 characters. Either the title is to be linked or the read more button at the end of the post. The link to the website providing the entry is mandatory! If you want the category to be displayed as well, we recommend the following scheme.  
  
[ pubDate ] by [ author ]  
[ Title ]  
[ SOURCE ] • [ category ]: [ Description ]  

This could look like the following example article in the news feed:  
  
  
*Mon, 10 Apr 2023 by Mia Wong*  
**The Extremes of Good and Evil**  
SUSANA • Events: But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. 
  
  
  
---  

# 3. Provide your feed
You can participate in the RSS feed of the network by providing a corresponding RSS feed within your own website under a fixed URL, which will then be integrated through the interface of the NCN.  
  
To do this, contact the SuSanA secretariat in advance by mail (info@susana.org) to check whether your organization meets the requirements and criteria to be included in the network newsfeed.   
  
After completion and provision of your RSS, it will be added to the configuration file and played out globally on all participating websites. For this we need your logo, which we provide and store in predefined formats on our web service.



## 3.1. Header of your RSS feed
The header of your channel element must contain at least two parameters. The other parameters are based on the general specifications for the structure of an RSS feed and are not mandatory for the import into the NCN. Required are:

**[pubDate]**  
Date when the feed was published  

**[lastBuildDate]**  
Date of the last update of your feed  
  
    
	  
## 3.2. Item tags inside your RSS feed
The following information is available within an item of a channel
  
**title** 
Title of the feed entry as it should be displayed on the external web pages. Maximum length of 256 characters 

**link** 
URL of the web page to which the read more button should point.

**description** 
Description of the entry. We recommend a maximum length of 350 characters to avoid automatic shortening of the description text on the external websites where the feed is embedded.  
**Important note: HTML & script elements will be removed.**

**pubDate** 
Time of publication of the feed entry. Note: The output of the channel is already sorted in descending order by this date field.  
  
**source** 
This field is ignored and output based on our configuration file in the NCN. You can use this field to provide source information for other feed collections.  
  
**author** 
Name of the author who wrote the article. We ask that this be taken into account in the output.  
  
**category** 
Enter here in which of the available categories your entry should be published. Please refer to the current config.json for the available categories.  
  
### guid ###
Unique URL by which your entry can be identified, this should not change during the life of the entry or be applied to other entries.  
  
### enclosure ###  
Optional linking of an image / video file via a URL within the respective entry. You can find further notes at: https://cyber.harvard.edu/rss/rss.html#ltenclosuregtSubelementOfLtitemgt 
