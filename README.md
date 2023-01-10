# Investigating Conversational Search Behavior For Domain Exploration

This repository contains the datasets of the research paper "Investigating Conversational Search Behavior For Domain Exploration", accepted to ECIR 2023. We provide an annotated dialogue corpus of text-based information-seeking conversations, including the five domain datasets that were explored. A total of 26 participants took part in the study, which was conducted in English. The experimental setup consisted of multiple chat sessions between two participants, where one participant acted as information seeker and the other as information provider. After the chat sessions, the participants filled out feedback surveys, which are also provided in this repository.

## Description of Domain Datasets
* [Geography dataset](https://en.wikipedia.org/wiki/List_of_nature_parks_in_Germany) (License: CC BY-SA 3.0) 
* [History dataset](https://pantheon.world/data/datasets) (License: CC BY-SA 4.0) 
* [Media dataset](https://en.wikipedia.org/wiki/List_of_time_travel_works_of_fiction) (License: CC BY-SA 3.0) 
* [Nutrition dataset](https://en.wikipedia.org/wiki/Table_of_food_nutrients) (License: CC BY-SA 3.0) 
* [Sports dataset](https://en.wikipedia.org/wiki/List_of_world_association_football_records) (License: CC BY-SA 3.0)

| Domain    | # Rows | # Columns | Short Description                                                                            |
|-----------|---------|------------|----------------------------------------------------------------------------------------------|
| Geography | 98      | 5          | A dataset with geographic information about nature parks in Germany.                  |
| History   | 11341   | 17         | This data source has biographic data and popularity metrics about historical figures. |
| Media     | 500     | 5          | A compilation of sci-fi literature, films, and TV series on the topic of time travel. |
| Nutrition | 285     | 9          | This data source contains data about the nutritional value of common food products.   |
| Sports    | 77      | 6          | A dataset with information about a variety of international football records.         |

## Descriptive Statistics of Dialogue Corpus
| Aspect                                      | Geography         | History           | Media             | Nutrition         | Sports            | Overall           |
|---------------------------------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|
| No. of messages                 | 169   | 98    | 156   | 153   | 93    | 669   |
| No. of sessions                 | 6     | 5     | 5     | 5     | 5     | 26    |
| Min-max messages per session    | 11-41 | 8-29  | 20-62 | 21-45 | 16-22 | 8-62  |
| Avg. messages per session       | 28.17 | 19.60 | 31.20  | 30.60  | 18.60 | 25.73 |
| Std. of messages per session   | 10.85 | 6.83  | 15.63 | 8.87  | 2.80  | 11.33 |
| Avg. characters per message     | 47.28 | 48.45 | 45.04 | 48.99 | 40.91 | 46.43 |
| Std. of characters per message | 49.46 | 79.52 | 39.79 | 43.29 | 26.15 | 49.44 |

## Annotation Procedure
The dialogue transcripts were manually annotated. This task of dialogue act annotation identifies the function or goal of a given utterance. Two researchers independently labeled each message with a speech act and corresponding dialogue act. To come up with a suitable group of dialogue acts, we started with an initial set derived from the widely known taxonomy of Bach and Harnish (1979). Through regular discussions, we clarified ambiguous labels and resolved disagreements between the annotators. Thereby, the set of used dialogue acts evolved through adding or removing certain to better fit the dialogue corpus.

We present an overview of all identified dialogue acts in the table blow.

| Dialogue act  | Frequency     | Definition                                                        | Example                                                     |
|-------------|---------------|-------------------------------------------------------------------|-------------------------------------------------------------|
| Request     | 214 (31.99%) | Express a general information need.                 | What is your dataset about?                   |
| Describe    | 129 (19.28%) | Provide a description of an information item.       | Steve Jobs was born 1955 in San Francisco.    |
| Acknowledge | 54 (8.07%)   | Express that an utterance was understood.           | Ok got it.                                    |
| List        | 47 (7.03%)   | List multiple information items from the dataset.   | They are name, state, year, area and summary. |
| Rank        | 45 (6.73%)   | Rank information items by a given metric.           | The earliest record is from 1906.             |
| Greet       | 39 (5.83%)   | Open the conversation with an initial greeting.     | Hi!                                           |
| Count       | 31 (4.63%)   | Count the number of a specified set of data items.  | There are 12 different categories.            |
| Thank       | 28 (4.19%)   | Express gratitude with regard to a response.        | Interesting, thank you!                       |
| Verify      | 25 (3.74%)   | Verify if the dataset contains a specific data item. | Yes, Socrates is in the dataset.             |
| Offer       | 20 (2.99%)   | Offer options for information exploration.          | Maybe you can ask me about her occupation.    |
| Accept      | 16 (2.39%)   | Agree with a suggested exploration direction.       | That would be great.                          |
| Clarify     | 14 (2.09%)   | Ask a clarification question for a given utterance. | You want to know the name of each column?     |
| Promise     | 4 (0.60%)    | Promise to perform a requested action.              | Sure. One second.                             |
| Reject      | 3 (0.44%)    | Disagree with a suggested exploration direction.    | No, thank you.                                |


## Process model
We employed process mining techniques, since they have been successfully applied to discover sequential patterns from dialogue logs. For the process discovery, we chose an inductive miner algorithm from the Python-based process mining library called PM4Py (https://pm4py.fit.fraunhofer.de/).

