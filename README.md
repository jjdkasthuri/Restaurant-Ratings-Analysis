# Restaurant Ratings Analysis

## Table of Content

- [Case Study](#case-study)
- [Dataset Description](#dataset-description)
- [ER Diagram](#er-diagram)
- [Data Cleaning](#data-cleaning)
- [Data Analysis](#data-analysis)
- [Dashboard](#dashboard)

## Case Study

## Dataset Description

Our data set consists of the following observations which include:

#### Consumers

- **Consumer_ID** - Unique identifier for each consumer
- **City** - City where the consumer lives
- **State** - State where the consumer lives
- **Country** - Country where the consumer lives
- **Latitude** - Latitude where the consumer lives
- **Longitude** - Longitude where the consumer lives
- **Smoker** - Whether the consumer smokes or not
- **Drink_Level** - Whether the consumer is an abstemious, casual, or social drinker
- **Transportation_Method** - Whether the consumer transports on foot, by public transport, or by car
- **Marital_Status** - The consumer's marital status (single or married)
- **Children** - Whether the consumer has dependent/independent children or kids
- **Age** - The consumer's age
- **Occupation** - The consumer's occupation (student, employed, or unemployed)
- **Budget** - The consumer's budget (low, medium, high)

#### Consumer_Preferences

- **Consumer_ID** - Unique identifier for each consumer
- **Preferred_Cuisine** - Types of food the consumer prefers

#### Ratings

- **Consumer_ID** - Unique identifier for each consumer
- **Restaurant_ID** - Unique identifier for each restaurant
- **Overall_Rating** - The overall rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)
- **Food_Rating** - The food's rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)
- **Service_Rating** - The service rating by the consumer for the restaurant (0=Unsatisfactory, 1=Satisfactory, 2=Highly Satisfactory)

#### Restaurants

- **Restaurant_ID** - Unique identifier for each restaurant
- **Name** - The restaurant's name
- **City** - The restaurant's city
- **State** - The restaurant's state
- **Country** - The restaurant's country
- **Zip_Code** - The restaurant's zip code
- **Latitude** - The restaurant's latitude
- **Longitude** - The restaurant's longitude
- **Alcohol_Service** - Whether the restaurant serves no alcohol, wine & beer, or a full bar
- **Smoking_Allowed** - Whether any smoking is allowed, including in the bar or in smoking sections
- **Price** - The restaurant's price (low, medium, high)
- **Franchise** - Whether the restaurant is a franchise
- **Area** - Whether the restaurant is in an open or closed area
- **Parking** - Whether the restaurant offers any sort of parking (none, yes, public, valet)

#### Restaurant_Cuisines

- **Restaurant_ID** - Unique identifier for each restaurant
- **Cuisine** - Types of food the restaurant serves

## ER Diagram

## Data Cleaning

### Steps to import data as a folder

1. Get data -> More -> All -> Folder -> Connect -> Path leading to the folder dataset -> Click ok
2. Click on transform data -> Duplicate the file -> Click on Binary to expand the dataset (Repeat the set for the no of datasets)

### Pre-Processing

- Remove blanks
- make the first row a header

#### Age Group

```
AgeGroup =
SWITCH(
    TRUE(),
    consumers[Age] <= 18, "Children and Adolescents",
    consumers[Age] <= 30, "Young Adults",
    consumers[Age] <= 45, "Adults",
    consumers[Age] <= 60, "Middle-aged Adults",
    "Seniors"
)
```

#### Service Rating Category

```
Service_Rating_Category = SWITCH(
    TRUE(),
    ratings[Service_Rating] = 0, "Unsatisfactory",
    ratings[Service_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```

#### Overall Rating Category

```
Overall_Rating_Category = SWITCH(
    TRUE(),
    ratings[Overall_Rating] = 0, "Unsatisfactory",
    ratings[Overall_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```

#### Food Rating Category

```
Food_Rating_Category = SWITCH(
    TRUE(),
    ratings[Food_Rating] = 0, "Unsatisfactory",
    ratings[Food_Rating] = 1, "Satisfactory",
    "Highly Satisfactory"
)
```

## Data Analysis

### Local Insights:

- What is the distribution of consumers by city and state?

  Most of the population is from San Luis Potosí, San Luis Potosí, while the second largest group is from Cuernavaca, Morelos.

- How does the age distribution of consumers vary by state?

  In all three states, young adults under 30 years of age form the majority of the population. In two states, San Luis Potosí and Morelos, the second largest demographic consists of seniors, aged over 60 years.

- What percentage of consumers are smokers or non-smokers in each city?

  The vast majority of consumers from all four cities are non-smokers, with Jiutepec having a 100% non-smoking population. In Cuernavaca city, smokers make up 25% of the population.

- How common is parking availability at restaurants in different cities?
  The majority of restaurants across all cities lack parking facilities, while some have parking available. In San Luis Potosí and Cuernavaca, two restaurants offer valet parking, while public parking is available in San Luis Potosí, Ciudad Victoria, and Cuernavaca.

### Dining Insights:

- How does the availability of parking correlate with restaurant price levels?

  Out of the 16 high-priced restaurants, 16 have parking available, with 3 offering valet parking, 1 providing public parking, and 5 lacking any parking options. Medium and low-priced restaurants do not offer valet parking; however, some provide public parking or have parking available, while others do not have parking available at all.

- What is the distribution of restaurants by state?

  San Luis Potosí has 84 restaurants, whereas Morelos and Tamaulipas each have 23 restaurants.

- How do restaurant franchises compare to non-franchises in terms of consumer ratings?

  The majority of the restaurants are non-franchises, and they are equally distributed across three rating categories: unsatisfactory, satisfactory, and highly satisfactory. A small portion of the restaurants are franchises, and they are also equally distributed across the same three rating categories.

- What are consumers' preferred cuisines based on their demographic profiles?

  Mexican cuisine is the most preferred, followed by American cuisine.

### Hospitality Insights:

- How does the type of alcohol service offered vary by restaurants in each city?

  In the four cities combined—Jiutepec, San Luis Potosí, Cuernavaca, and Ciudad Victoria—66.92% of restaurants don't offer alcohol, 6.93% offer a full bar, and 26.15% offer wine and beer.

- What transportation methods are most commonly used by consumers?

  61% of consumers use public transportation, 27% use cars, and 11% walk.

- How does the presence of alcohol service influence consumer ratings?

  Among non-drinkers, 303 rated their experience as highly satisfactory, 289 as satisfactory, and 170 as unsatisfactory. For wine and beer consumers, the ratings were 146 highly satisfactory, 105 satisfactory, and 68 unsatisfactory. At full bars, 37 rated highly satisfactory, 27 satisfactory, and 16 unsatisfactory.

- What percentage of restaurants allow smoking in each state?

  Roughly 73% of restaurants maintain smoke-free policies, while only 1.5% in San Luis Potosí and Morelo allow smoking in bar sections. About 7% of restaurants permit smoking overall, with approximately 18.46% offering designated smoking areas.

## Dashboard

# ss 
![image](https://github.com/jjdkasthuri/Restaurant-Ratings-Analysis/assets/154047882/0c246ceb-f6a7-43d9-a46c-6a50f9bfa6cf)

![image](https://github.com/jjdkasthuri/Restaurant-Ratings-Analysis/assets/154047882/7a5c85c8-a72b-4f97-a497-4fc894d6d23b)

![image](https://github.com/jjdkasthuri/Restaurant-Ratings-Analysis/assets/154047882/1e2c94eb-4638-4103-9816-f254943c8348)

![image](https://github.com/jjdkasthuri/Restaurant-Ratings-Analysis/assets/154047882/49fb0168-79eb-4a2a-ba05-2475e98cfc8f)

![image](https://github.com/jjdkasthuri/Restaurant-Ratings-Analysis/assets/154047882/3f13edba-2e2f-44da-828a-77a391063341)





