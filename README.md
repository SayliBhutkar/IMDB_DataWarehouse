# IMBD_DataIntegration_Talend
## IMDb Datasets
IMDb Dataset DetailsEach dataset is contained in a gzipped, tab-separated-values (TSV) formatted file in the UTF-8 character set. The first line in each file contains headers that describe what is in each column. A‘\N’is used to denote that a particular field is missing or null for that title/name. The available datasets are as follows:<br><br><br>
<b>title.akas.tsv.gz</b>-Contains the following information for titles:<br>
▪titleId(string) -a tconst, an alphanumeric unique identifier of the title<br>
▪ordering (integer) –a number to uniquely identify rows for a given titleId<br>
▪title (string) –the localized title<br>
▪region (string) -the region for this version of the title<br>
▪language (string) -the language of the title<br>
▪types (array) -Enumerated set of attributes for this alternative title. One or more of the following: "alternative", "dvd", "festival", "tv", "video", "working", "original", "imdbDisplay". New values may be added in the future without warning<br>
▪attributes (array) -Additional terms to describe this alternative title, not enumerated<br><br><br>
<b>title.basics.tsv.gz</b>-Contains the following information for titles:<br>
▪tconst(string) -alphanumeric unique identifier of the title<br>
▪titleType(string) –the type/format of the title (e.g. movie, short, tvseries, tvepisode, video, etc)<br>
▪primaryTitle(string) –the more popular title / the title used by the filmmakers on promotional materials at the point of release<br>
▪originalTitle(string) -original title, in the original language<br>
▪isAdult(boolean) -0: non-adult title; 1: adult title<br>
▪startYear(YYYY) –represents the release year of a title. In the case of TV Series, it is the series start year<br>
▪endYear(YYYY) –TV Series end year. ‘\N’ for all other title types<br>
▪runtimeMinutes–primary runtime of the title, in minutes<br>
▪genres (string array) –includes up to three genres associated with the title<br><br><br>
<b>title.crew.tsv.gz</b>–Contains the director and writer information for all the titles in IMDb. Fields include:<br>
▪tconst(string) -alphanumeric unique identifier of the title<br>
▪directors (array of nconsts) -director(s) of the given title<br>
▪writers (array of nconsts) –writer(s) of the given title<br><br><br>
<b>title.episode.tsv.gz</b>–Contains the tv episode information. Fields include:<br>
▪tconst(string) -alphanumeric identifier of episode<br>
▪parentTconst(string) -alphanumeric identifier of the parent TV Series<br>
▪seasonNumber(integer) –season number the episode belongs to<br>
▪episodeNumber(integer) –episode number of the tconstin the TV series<br><br><br>
<b>title.principals.tsv.gz</b>–Contains the principal cast/crew for titles<br>
 ▪tconst(string) -alphanumeric unique identifier of the title<br>
 ▪ordering (integer) –a number to uniquely identify rows for a given titleId<br>
 ▪nconst(string) -alphanumeric unique identifier of the name/person<br>
 ▪category (string) -the category of job that person was in<br>
 ▪job (string) -the specific job title if applicable, else '\N'<br>
 ▪characters (string) -the name of the character played if applicable, else '\N'<br><br><br>
<b>title.ratings.tsv.gz</b>–Contains the IMDb rating and votes information for titles<br>
▪tconst(string) -alphanumeric unique identifier of the title<br>
▪averageRating–weighted average of all the individual user ratings<br>
▪numVotes-number of votes the title has received<br><br><br>
<b>name.basics.tsv.gz</b>–Contains the following information for names:<br>
▪nconst(string) -alphanumeric unique identifier of the name/person<br>
▪primaryName(string)–name by which the person is most often credited<br>
▪birthYear–in YYYY format<br>
▪deathYear–in YYYY format if applicable, else '\N'<br>
▪primaryProfession(array of strings)–the top-3 professions of the person<br>
▪knownForTitles(array of tconsts) –titles the person is known for<br><br><br>
## IMDb Datasets –ISO Datasets<br>
•<b>Countries:</b>countries_iso-all.tsv<br>
•<b>Languages:</b>language-codes-iso.tsv<br><br><br>
## IMDb Datasets –Box Office Revenues<br>
•<b>World Wide Box Office All Time Top 1000 Movies:</b>World Wide Box Office All Time Top 1000.tsv<br>
•<b>Top Movie Franchises</b><br>
▪IMDb BoxOfficeMojo-Franchises (US & Canada).tsv–aggregate data for all franchises<br>
▪IMDb BoxOfficeMojo-Franchise_ Marvel Cinematic Universe.tsv–data for one franchise<br>
▪You need to extract & load data for top 20 franchises<br>
•<b>Top Movie Brands</b><br>
▪IMDb BoxOfficeMojo-Brands (US & Canada).tsv-aggregate data for all brands<br>
▪IMDb BoxOfficeMojo-Brand_ Marvel Comics.tsv–data for one brand<br>
▪Youneedto extract & load data for top 20 brands<br><br><br>
## Movie Lens Data<br>
This dataset (ml-25m) describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service. It contains 25,000,095 ratings and 1,093,360 tag applications across 62,423 movies. These data were created by 162,541 users between January 09, 1995 and November 21, 2019. This datasetwas generated on November 21, 2019.Description: MovieLens_README.txt<br>
•Movies Data File Structure (MovieLens_ movies.csv)<br>
•Ratings Data File Structure (MovieLens_ ratings.csv)<br>
•Tags Data File Structure (MovieLens_ tags.csv)<br>
•Links Data File Structure (MovieLens_ links.csv)<br>
•Tag Genome (MovieLens_ genome-scores.csv and MovieLens_ genome-tags.csv)<br><br><br>
## The Numbers<br>
•<b>Obtaining daily box office data on franchises & their movies by cut & past</b><br>
▪Franchises Domestic Box Office<br>
▪Box Office History for Marvel Cinematic Universe Movies<br>
▪The Avengers (2012)<br>
•<b>Files</b><br>
▪The Numbers -Domestic Box Office -Franchises.tsv<br>
▪The Numbers -Domestic Box Office -Franchises -Marvel Cinematic Universe.tsv<br>
▪The Numbers -Domestic Box Office Daily -The Avengers.tsv<br><br><br>
## IMDb Project Deliverables<br>
>•Ingest initial set of tsvor csv files into staging tables<br>
>•Design and load dimensional model for above data<br>
>•Perform data consistency & cleansing processes<br>
>•Add supplemental data to model<br>
>•Design and create BI visualizations answering business questions<br><br><br>
## Dimensional Model<br>
<img src="er.JPG" alt="Drawing" style="width: 100%;"/><br>
