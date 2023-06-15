# LHL-Midterm
Original Authors: Andrew Elliott &amp; Jacob Cyr

## Project:
### Introduction:
Pokémon is a major media franchise, starting with the release of a pair of video games in 1996 before quickly skyrocketing into a persistent global powerhouse that today rivals other prominent franchises like Mario and Disney. It is notable not only for its creature collection and team building mechanics, but also for kickstarting a competitive battling scene that today sees thousands of players competing with one another in tournaments. Why this matters is that the Esports industry has really taken off over the past decade, with some estimates suggesting it pulls in over $1B USD in revenue annually from hundreds of millions of avid watchers.

### Central Aim:
As such, the ultimate aim of this project is to learn about different Pokemon and gain insights into which ones may be competitively viable (i.e. tournament winners) using statistical models and algorithms based on criteria such as stats, typings, "evolution stage", and so forth. 

### Limitations and Assumptions:
There are two central facts to consider:
1. These game work on a rotational cycle, meaning some Pokemon get removed and others get added in between games. This can impact availability across rotations.
2. We have limited time to work on this midterm, so we are trying to keep the scope of this project realistic given the timeframe.

As such, we are limiting our datasets to stats, names, and typings, while also ignoring special one-use mechanics and properties that can be adjusted between games such as "ability" traits, or item and move availability. We are only interested in details that are unlikely to change drastically between games, so the assumption will be that stats, evolution stage, and typings matter more than anything else even if we would need to consider other factors to determine this with near absolute certainty. We also found that there are instances where some Pokemon share the name but are otherwise distinct in stats, typings, etc., which are referred to as "forms"; we are ignoring all other instances of these as well.

## Problem to be Solved:
**Our central problem is this: Which stats seems to contribute the most to a Pokemon's likely success (e.g. total stats)? Using our findings, can we determine which typings and evolution stages have the highest prevalence of "good" Pokemon?**

## Process:
### Part A: API Call & CSV Formation
We performed an API call to PokeAPI, an open-source API that aims to consolidate Pokemon game data in a way that can help ensure accuracy across different platforms and websites. Using this API, we generated a CSV with the following information:
- Stats: hp, attack, defence, sp-attack, sp-defence, speed
- Types: type_1 and type_2 variables
- Names: What a Pokemon is named
- total_stat, which is the sum of all 6 stats
- Evolution: stage, which will either be 1, 2, or 3

This API call is organised within a central function that can generate a CSV depending on which "generation" (i.e. rotational game iteration) we want data on and return an error message if an invalid number is stored, even if we are not working with every dataset we could generate. 

### Part B: Cleaning and EDA
Because the data stored on the API's server is already pretty clean, there was no real need to do anything like change string case or fill Null/NaN values unless we wanted to, but we still did some of these things to demonstrate our ability to do them given that we will need to know once in the workforce.

However, the main work in this section was to scan the data and employ various techniques to understand it better. We listed details so that we could identify, for example, standard deviations, min and max values, interquartile ranges, and so forth; we also generated a few plots to help visualise some aspects of the data better.

After everything was said and done, two new CSV files were generated; one combining all 9 individual "genx_pokemon_stats" files into one, and another that filtered out the bottom 50% of Pokemon based on the totalstat value (anything below 450). 

### Part C: Quick SQL Demo
While we don't really need to do much with SQL given how clean our data is, we still felt it would be valuable to put some data in a SQL database. As such, we chose the newly made "fullgen_tophalf_pokemon.csv" file for this purpose.

### Part D:
model, correlations

### Part E:
visualize, Tableau, etc.
