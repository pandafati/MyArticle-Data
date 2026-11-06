# MyArticle-Data
## Project Phases

| Phase | Description | Folder |
|---|---|---|
| I | Data collection and preprocessing | `phase1_data_collection/` |
| II | Aspect extraction and labeling | `phase2_aspect_labeling/` |
| III | Generic and aspect-based summarization (3,000 human-written summaries) | `phase3_summarization/` |


# Phase I: Steel Industry News Dataset (SteelOrbis, 2022-2024)

A corpus of \*\*14,020 English-language steel industry news articles\*\* collected from SteelOrbis between \*\*January 2022 and September 2024\*\*, together with the preprocessing pipeline used to prepare it for natural language processing (NLP) and machine learning.

\## Overview

This repository supports \*\*Phase I (Data Collection and Preprocessing)\*\* of an NLP framework for analyzing steel market news. It documents how the data were collected, what the dataset contains, and how raw text was cleaned and transformed.



\## Data Source

\- \*\*Source:\*\* \[SteelOrbis](https://www.steelorbis.com), a global steel industry news platform established in 2002.

\- \*\*Reach:\*\* over 45,000 members and 90,000 users across 199 countries.

\- \*\*Coverage:\*\* news from suppliers, manufacturers, traders, and end-users.

\- \*\*Why SteelOrbis:\*\* global standing, consistent updates, comprehensive market coverage, English-language content, and lower filtering effort compared with alternative sources.

\- \*\*Compliance:\*\* articles were collected from publicly accessible pages in accordance with the site's terms of use.


\## Dataset Description


| Property | Details |


| Articles | 14,020 |

| Attributes per article | 27 (metadata and content) |

| Time span | January 2022 to September 2024 |

| Language | English |



\*\*Key fields used for analysis\*\*



| Field | Description |


| `\_id` | Unique identifier |

| `title` | Article headline |

| `date` | Publication timestamp |

| `location` | Geographic reference |

| `content` | Full article text |



\## Data Collection

\- A \*\*custom JavaScript web crawler\*\* systematically traversed SteelOrbis pages and extracted structured data, going beyond traditional scraping, which is limited to specific page elements.

\- Data were stored in a \*\*MongoDB\*\* NoSQL database, chosen for efficient handling of unstructured data, high-speed read/write operations, and effective indexing and querying.

\- This setup enables scalable and reproducible data acquisition.



\## Phase II: Preprocessing Pipeline

Implemented in Python using \*\*NLTK\*\* and the \*\*`re`\*\* library.

1\. \*\*Data cleaning:\*\* removal of duplicates, special characters, hyperlinks, hashtags, irrelevant symbols, and a custom stopword list.

2\. \*\*Normalization:\*\* lowercasing, removal of punctuation and extra whitespace, and filtering of non-English and special characters.

3\. \*\*Transformation:\*\* tokenization and stemming.



\*\*Stemmer choice:\*\* the \*\*Porter Stemmer\*\* was selected after comparison with Snowball, Lancaster, and FastText on a corpus sample. The alternatives either truncated domain terms excessively, losing their meaning, or left inflected forms largely unchanged.

The result is a clean, semantically meaningful corpus ready for machine learning workflows.

\## Tools and Technologies



JavaScript (crawler) · MongoDB · Python · NLTK · Regular expressions

\## Next Step

The following phase covers extracting and labeling key aspects of steel news.

# Phase III: Human-Written Summaries and Aspect-Based Summarization

A set of **3,000 steel industry news articles with human-written reference summaries**, used to fine-tune and evaluate generic and aspect-conditioned summarization models.



