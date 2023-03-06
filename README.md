# igdb-schema-and-enum


## Basic Schema's & Enum
Video Games! Schema
|field|type|description|
|:----|:----|:----|
|age_ratings|Array of Age Rating IDs|The PEGI rating|
|aggregated_rating|Double|Rating based on external critic scores|
|aggregated_rating_count|Integer|Number of external critic scores|
|alternative_names|Array of Alternative Name IDs|Alternative names for this game|
|artworks|Array of Artwork IDs|Artworks of this game|
|bundles|Array of Game IDs|The bundles this game is a part of|
|category|Category Enum|The category of this game|
|checksum|uuid|Hash of the object|
|collection|Reference ID for Collection|The series the game belongs to|
|cover|Reference ID for Cover|The cover of this game|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|dlcs|Array of Game IDs|DLCs for this game|
|expanded_games|Array of Game IDs|Expanded games of this game|
|expansions|Array of Game IDs|Expansions of this game|
|external_games|Array of External Game IDs|External IDs this game has on other services|
|first_release_date|Unix Time Stamp|The first release date for this game|
|follows|Integer|Number of people following a game|
|forks|Array of Game IDs|Forks of this game|
|franchise|Reference ID for Franchise|The main franchise|
|franchises|Array of Franchise IDs|Other franchises the game belongs to|
|game_engines|Array of Game Engine IDs|The game engine used in this game|
|game_localizations|Array of Game Localization IDs|Supported game localizations for this game. A region can have at most one game localization for a given game|
|game_modes|Array of Game Mode IDs|Modes of gameplay|
|genres|Array of Genre IDs|Genres of the game|
|hypes|Integer|Number of follows a game gets before release|
|involved_companies|Array of Involved Company IDs|Companies who developed this game|
|keywords|Array of Keyword IDs|Associated keywords|
|language_supports|Array of Language Support IDs|Supported Languages for this game|
|multiplayer_modes|Array of Multiplayer Mode IDs|Multiplayer modes for this game|
|name|String| |
|parent_game|Reference ID for Game|If a DLC, expansion or part of a bundle, this is the main game or bundle|
|platforms|Array of Platform IDs|Platforms this game was released on|
|player_perspectives|Array of Player Perspective IDs|The main perspective of the player|
|ports|Array of Game IDs|Ports of this game|
|rating|Double|Average IGDB user rating|
|rating_count|Integer|Total number of IGDB user ratings|
|release_dates|Array of Release Date IDs|Release dates of this game|
|remakes|Array of Game IDs|Remakes of this game|
|remasters|Array of Game IDs|Remasters of this game|
|screenshots|Array of Screenshot IDs|Screenshots of this game|
|similar_games|Array of Game IDs|Similar games|
|slug|String|A url-safe, unique, lower-case version of the name|
|standalone_expansions|Array of Game IDs|Standalone expansions of this game|
|status|Status Enum|The status of the games release|
|storyline|String|A short description of a games story|
|summary|String|A description of the game|
|tags|Array of Tag Numbers|Related entities in the IGDB API|
|themes|Array of Theme IDs|Themes of the game|
|total_rating|Double|Average rating based on both IGDB user and external critic scores|
|total_rating_count|Integer|Total number of user and external critic scores|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|
|version_parent|Reference ID for Game|If a version, this is the main game|
|version_title|String|Title of this version (i.e Gold edition)|
|videos|Array of Game Video IDs|Videos of this game|
|websites|Array of Website IDs|Websites associated with this game|



### Screenshots Schema


|field|type|description|
|:----|:----|:----|
|alpha_channel|boolean| |
|animated|boolean| |
|checksum|uuid|Hash of the object|
|game|Reference ID for Game|The game this video is associated with|
|height|Integer|The height of the image in pixels|
|image_id|String|The ID of the image used to construct an IGDB image link|
|url|String|The website address (URL) of the item|
|width|Integer|The width of the image in pixels|



### Collection Schema
Collection, AKA Series

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|games|Array of Game IDs|The games that are associated with this collection|
|name|String|Umbrella term for a collection of games|
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|



### Cover Schema
The cover art of games

|field|type|description|
|:----|:----|:----|
|alpha_channel|boolean| |
|animated|boolean| |
|checksum|uuid|Hash of the object|
|game|Reference ID for Game|The game this cover is associated with. If it is empty then this cover belongs to a game_localization, which can be found under game_localization field|
|game_localization|Reference ID for Game Localization|The game localization this cover might be associated with|
|height|Integer|The height of the image in pixels|
|image_id|String|The ID of the image used to construct an IGDB image link|
|url|String|The website address (URL) of the item|
|width|Integer|The width of the image in pixels|


### External Game Schema
Game IDs on other services

|field|type|description|
|:----|:----|:----|
|category|Category Enum|The id of the other service|
|checksum|uuid|Hash of the object|
|countries|Array of Integers|The ISO country code of the external game product.|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|game|Reference ID for Game|The IGDB ID of the game|
|media|Media Enum|The media of the external game.|
|name|String|The name of the game according to the other service|
|platform|Reference ID for Platform|The platform of the external game product.|
|uid|String|The other services ID for this game|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|


#### Franchise Schema
A list of video game franchises such as Star Wars.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|games|Array of Game IDs|The games that are associated with this franchise|
|name|String|The name of the franchise|
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|


### Game Engine Schema

Video game engines such as unreal engine.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|companies|Array of Company IDs|Companies who used this game engine|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|description|String|Description of the game engine|
|logo|Reference ID for Game Engine Logo|Logo of the game engine|
|name|String|Name of the game engine|
|platforms|Array of Platform IDs|Platforms this game engine was deployed on|
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|

### Game Localization Schema

Game localization for a game

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|cover|Reference ID for Cover|The cover of this game localization|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|game|Reference ID for Game|The Game the localization belongs to|
|name|String| |
|region|Reference ID for Region|The Region of the localization|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|

### Game Mode Schema
Single player, Multiplayer etc

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|name|String|The name of the game mode|
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|

```
Example:
{
        "id": 1,
        "created_at": 1298937600,
        "name": "Single player",
        "slug": "single-player",
        "updated_at": 1323216000,
        "url": "https://www.igdb.com/game_modes/single-player",
        "checksum": "a43b1688-f968-3541-0897-9735ffde1745"
}
```

### Involved Company Schema

company involved in same
|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|company|Reference ID for Company| |
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|developer|boolean| |
|game|Reference ID for Game| |
|porting|boolean| |
|publisher|boolean| |
|supporting|boolean| |
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|


### Keyword Schema
Keywords are words or phrases that get tagged to a game such as “world war 2” or “steampunk”.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|name|String| |
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|


### Language Schema
Languages that are used in the Language Support endpoint.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|locale|String|The combination of Language code and Country code|
|name|String|The English name of the Language|
|native_name|String|The Native Name of the Language|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|


### Language Support Schema

Games can be played with different languages for voice acting, subtitles, or the interface language.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|game|Reference ID for Game| |
|language|Reference ID for Language| |
|language_support_type|Reference ID for Language Support Type| |
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|

### Language Support Type Schema

Language Support Types contains the identifiers for the support types that Language Support uses.

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|name|String| |
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|

### Multiplayer Mode Schema

Data about the supported multiplayer types
|field|type|description|
|:----|:----|:----|
|campaigncoop|boolean|True if the game supports campaign coop|
|checksum|uuid|Hash of the object|
|dropin|boolean|True if the game supports drop in/out multiplayer|
|game|Reference ID for Game|The game this multiplayer mode is associated with|
|lancoop|boolean|True if the game supports LAN coop|
|offlinecoop|boolean|True if the game supports offline coop|
|offlinecoopmax|Integer|Maximum number of offline players in offline coop|
|offlinemax|Integer|Maximum number of players in offline multiplayer|
|onlinecoop|boolean|True if the game supports online coop|
|onlinecoopmax|Integer|Maximum number of online players in online coop|
|onlinemax|Integer|Maximum number of players in online multiplayer|
|platform|Reference ID for Platform|The platform this multiplayer mode refers to|
|splitscreen|boolean|True if the game supports split screen, offline multiplayer|
|splitscreenonline|boolean|True if the game supports split screen, online multiplayer|

### Platform Schema
The hardware used to run the game or game delivery network

|field|type|description|
|:----|:----|:----|
|abbreviation|String|An abbreviation of the platform name|
|alternative_name|String|An alternative name for the platform|
|category|Category Enum|A physical or virtual category of the platform|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|generation|Integer|The generation of the platform|
|name|String|The name of the platform|
|platform_family|Reference ID for Platform Family|The family of platforms this one belongs to|
|platform_logo|Reference ID for Platform Logo|The logo of the first Version of this platform|
|slug|String|A url-safe, unique, lower-case version of the name|
|summary|String|The summary of the first Version of this platform|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|
|versions|Array of Platform Version IDs|Associated versions of this platform|
|websites|Array of Platform Website IDs|The main website|

### Player Perspective Schema
Player perspectives describe the view/perspective of the player in a video game.
|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|name|String| |
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|

### Release Date Schema
A handy endpoint that extends game release dates. Used to dig deeper into release dates, platforms and versions.

|field|type|description|
|:----|:----|:----|
|category|Category Enum|The format category of the release date|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|date|Unix Time Stamp|The date of the release|
|game|Reference ID for Game| |
|human|String|A human readable representation of the date|
|m|Integer|The month as an integer starting at 1 (January)|
|platform|Reference ID for Platform|The platform of the release|
|region|Region Enum|The region of the release|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|y|Integer|The year in full (2018)|


# Tag Numbers Schema
Tag numbers are automatically generated numbers which provide a compact and fast way to do complex filtering on the IGDB API. The number calculation can be easily achieved with any programming language.

The basis of the calculation is a 32bit integer, where the first 4 bits contain the object type ID, and the remaining 28 bits represent the ID of the object we are generating the tag number for.

Using this method a flat index of custom object ‘hashes’ can be maintained in which index the search and filtering is faster than using conventional methods.

Currently the following object types use tags:
|Type ID|Name|
|:----|:----|
|0|Theme|
|1|Genre|
|2|Keyword|
|3|Game|
|4|Player Perspective|

Let’s see two examples for tag number calculation.
We try to find all the games which relate to the Shooter genre. The tag number generation in Javascript would look something like the example on the right.

Javascript example query:
- Address:  https://api.igdb.com/v4/games/
- Body: where tags = (268435461);

Python example query:

- Address: https://api.igdb.com/v4/games/
- Body: where tags = (536871060);

### Game Video Schema
A video associated with a game

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|game|Reference ID for Game|The game this video is associated with|
|name|String|The name of the video|
|video_id|String|The external ID of the video (usually youtube)|


### Website Schema

A website url, usually associated with a game

|field|type|description|
|:----|:----|:----|
|category|Category Enum|The service this website links to|
|checksum|uuid|Hash of the object|
|game|Reference ID for Game|The game this website is associated with|
|trusted|boolean| |
|url|String|The website address (URL) of the item|

### Theme Struct 

Video game themes

|field|type|description|
|:----|:----|:----|
|checksum|uuid|Hash of the object|
|created_at|Unix Time Stamp|Date this was initially added to the IGDB database|
|name|String| |
|slug|String|A url-safe, unique, lower-case version of the name|
|updated_at|Unix Time Stamp|The last date this entry was updated in the IGDB database|
|url|String|The website address (URL) of the item|




#### Age Rating Enums
 category
|name|	value|
|---| ---|
|ESRB|	1|
|PEGI|	2|
|CERO|	3|
|USK|	4|
|GRAC|	5|
|CLASS_IND|	6|
|ACB|	7|

#### Game Enums
category
|name|value|
|:----|:----|
|main_game|0|
|dlc_addon|1|
|expansion|2|
|bundle|3|
|standalone_expansion|4|
|mod|5|
|episode|6|
|season|7|
|remake|8|
|remaster|9|
|expanded_game|10|
|port|11|
|fork|12|
|pack|13|
|update|14|

status

|name|value|
|:----|:----|
|released|0|
|alpha|2|
|beta|3|
|early_access|4|
|offline|5|
|cancelled|6|
|rumored|7|
|delisted|8|


#### Platform Enums

category
|name|value|
|:----|:----|
|console|	1|
|arcade|	2|
|platform|	3|
|operating_system|	4|
|portable_console|	5|
|computer|	6|

#### Age Rating Content Description Enums
category
|name|value|
|:----|:----|
|ESRB_alcohol_reference|1|
|ESRB_animated_blood|2|
|ESRB_blood|3|
|ESRB_blood_and gore|4|
|ESRB_cartoon_violence|5|
|ESRB_comic_mischief|6|
|ESRB_crude_humor|7|
|ESRB_drug_reference|8|
|ESRB_fantasy_violence|9|
|ESRB_intense_violence|10|
|ESRB_language|11|
|ESRB_lyrics|12|
|ESRB_mature_humor|13|
|ESRB_nudity|14|
|ESRB_partial_nudity|15|
|ESRB_real_gambling|16|
|ESRB_sexual_content|17|
|ESRB_sexual_themes|18|
|ESRB_sexual_violence|19|
|ESRB_simulated_gambling|20|
|ESRB_strong_language|21|
|ESRB_strong_lyrics|22|
|ESRB_strong_sexual content|23|
|ESRB_suggestive_themes|24|
|ESRB_tobacco_reference|25|
|ESRB_use_of alcohol|26|
|ESRB_use_of drugs|27|
|ESRB_use_of tobacco|28|
|ESRB_violence|29|
|ESRB_violent_references|30|
|ESRB_animated_violence|31|
|ESRB_mild_language|32|
|ESRB_mild_violence|33|
|ESRB_use_of drugs and alcohol|34|
|ESRB_drug_and alcohol reference|35|
|ESRB_mild_suggestive themes|36|
|ESRB_mild_cartoon violence|37|
|ESRB_mild_blood|38|
|ESRB_realistic_blood and gore|39|
|ESRB_realistic_violence|40|
|ESRB_alcohol_and tobacco reference|41|
|ESRB_mature_sexual themes|42|
|ESRB_mild_animated violence|43|
|ESRB_mild_sexual themes|44|
|ESRB_use_of alcohol and tobacco|45|
|ESRB_animated_blood and gore|46|
|ESRB_mild_fantasy violence|47|
|ESRB_mild_lyrics|48|
|ESRB_realistic_blood|49|
|PEGI_violence|50|
|PEGI_sex|51|
|PEGI_drugs|52|
|PEGI_fear|53|
|PEGI_discrimination|54|
|PEGI_bad_language|55|
|PEGI_gambling|56|
|PEGI_online_gameplay|57|
|PEGI_in_game_purchases|58|
|CERO_love|59|
|CERO_sexual_content|60|
|CERO_violence|61|
|CERO_horror|62|
|CERO_drinking_smoking|63|
|CERO_gambling|64|
|CERO_crime|65|
|CERO_controlled_substances|66|
|CERO_languages_and others|67|
|GRAC_sexuality|68|
|GRAC_violence|69|
|GRAC_fear_horror_threatening|70|
|GRAC_language|71|
|GRAC_alcohol_tobacco_drug|72|
|GRAC_crime_anti_social|73|
|GRAC_gambling|74|
|CLASS_IND_violencia|75|
|CLASS_IND_violencia_extrema|76|
|CLASS_IND_conteudo_sexual|77|
|CLASS_IND_nudez|78|
|CLASS_IND_sexo|79|
|CLASS_IND_sexo_explicito|80|
|CLASS_IND_drogas|81|
|CLASS_IND_drogas_licitas|82|
|CLASS_IND_drogas_ilicitas|83|
|CLASS_IND_linguagem_impropria|84|
|CLASS_IND_atos_criminosos|85|

#### Character Enums
gender
|name|value|
|:----|:----|
|Male|0|
|Female|1|
|Other|2|

species

|name|value|
|:----|:----|
|Human|1|
|Alien|2|
|Animal|3|
|Android|4|
|Unknown|5|

#### Company Enums
change_date_category

|name|value|
|:----|:----|
|YYYYMMMMDD|0|
|YYYYMMMM|1|
|YYYY|2|
|YYYYQ1|3|
|YYYYQ2|4|
|YYYYQ3|5|
|YYYYQ4|6|
|TBD|7|

start_date_category

|name|value|
|:----|:----|
|YYYYMMMMDD|0|
|YYYYMMMM|1|
|YYYY|2|
|YYYYQ1|3|
|YYYYQ2|4|
|YYYYQ3|5|
|YYYYQ4|6|
|TBD|7|

#### Company Website Enums
category

|name|value|
|:----|:----|
|official|1|
|wikia|2|
|wikipedia|3|
|facebook|4|
|twitter|5|
|twitch|6|
|instagram|8|
|youtube|9|
|iphone|10|
|ipad|11|
|android|12|
|steam|13|
|reddit|14|
|itch|15|
|epicgames|16|
|gog|17|
|discord|18|



#### External Game Enums
category

|name|value|
|:----|:----|
|steam|1|
|gog|5|
|youtube|10|
|microsoft|11|
|apple|13|
|twitch|14|
|android|15|
|amazon_asin|20|
|amazon_luna|22|
|amazon_adg|23|
|epic_game_store|26|
|oculus|28|
|utomik|29|
|itch_io|30|
|xbox_marketplace|31|
|kartridge|32|
|playstation_store_us|36|
|focus_entertainment|37|
|xbox_game_pass_ultimate_cloud|54|
|gamejolt|55|

media

|name|value|
|:----|:----|
|digital|1|
|physical|2|

#### Game Version Feature Enums
category
|name|value|
|:----|:----|
|boolean|0|
|description|1|

#### Game Version Feature Value Enums
included_feature

|name|value|
|:----|:----|
|NOT_INCLUDED|0|
|INCLUDED|1|
|PRE_ORDER_ONLY|2|

#### Platform Version Release Date Enums
category

|name|value|
|:----|:----|
|YYYYMMMMDD|0|
|YYYYMMMM|1|
|YYYY|2|
|YYYYQ1|3|
|YYYYQ2|4|
|YYYYQ3|5|
|YYYYQ4|6|
|TBD|7|

region

|name|value|
|:----|:----|
|europe|1|
|north_america|2|
|australia|3|
|new_zealand|4|
|japan|5|
|china|6|
|asia|7|
|worldwide|8|
|korea|9|
|brazil|10|

#### Platform Website Enums

category
|name|value|
|:----|:----|
|official|1|
|wikia|2|
|wikipedia|3|
|facebook|4|
|twitter|5|
|twitch|6|
|instagram|8|
|youtube|9|
|iphone|10|
|ipad|11|
|android|12|
|steam|13|
|reddit|14|
|discord|15|
|google_plus|16|
|tumblr|17|
|linkedin|18|
|pinterest|19|
|soundcloud|20|

#### Website Enums

category
|name|value|
|:----|:----|
|official|1|
|wikia|2|
|wikipedia|3|
|facebook|4|
|twitter|5|
|twitch|6|
|instagram|8|
|youtube|9|
|iphone|10|
|ipad|11|
|android|12|
|steam|13|
|reddit|14|
|itch|15|
|epicgames|16|
|gog|17|
|discord|18|

