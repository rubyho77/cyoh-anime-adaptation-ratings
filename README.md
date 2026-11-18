# Manga vs. Light-Novel Anime Adaptation Ratings


## Topic Check-in

For my Choose Your Own Hypothesis project, I plan to investigate whether anime adapted from manga and anime adapted from light novels differ in their AniList user ratings. I am interested in anime and wanted to use a dataset related to a topic I genuinely enjoy while also examining how online audiences evaluate different types of adaptations. I collected the data directly from the AniList public GraphQL API rather than using a pre-packaged dataset. My dataset focuses on finished, non-adult TV anime released from 2015 through 2025 whose source material is either manga or a light novel. The raw dataset contains 1,147 anime entries. Five entries without an AniList average score were removed, leaving 1,142 observations for analysis: 790 manga adaptations and 352 light-novel adaptations. I will use a permutation test to investigate whether the average AniList rating differs between the two groups and bootstrapping to quantify uncertainty in the mean and median rating differences.

**Project Repository:** [Insert GitHub repository link here]

### Project Scaffold Table

| Element | My Plan |
|---|---|
| **Topic / Question** | Among finished TV anime released from 2015–2025, do anime adapted from manga and anime adapted from light novels differ in their AniList user ratings? This matters because online ratings are widely used to evaluate and recommend entertainment media, but ratings may vary systematically across different types of source material and audience communities. |
| **Hypothesis** | I expect there may be a systematic difference in user ratings between manga adaptations and light-novel adaptations. I will use a two-sided comparison rather than assuming in advance that one source type must receive higher ratings. |
| **Outcome / Metric / Test Statistic** | The primary outcome is AniList `averageScore`, measured on a 0–100 scale. My permutation-test statistic will be the **difference in mean average score between manga adaptations and light-novel adaptations**: mean(Manga) − mean(Light Novel). |
| **Units of Analysis** | Each observation represents **one finished TV anime entry** in AniList that began between January 1, 2015 and December 31, 2025 and was adapted from either manga or a light novel. |
| **Data Source(s)** | Data come directly from the **AniList public GraphQL API**, using AniList's media database. The API allows filtering anime by format, status, source material, release date, and other characteristics. My query retrieved 1,147 qualifying entries. |
| **Why this data works** | AniList provides both the explanatory variable needed for the comparison (`source`: Manga or Light Novel) and the response variable (`averageScore`). It also includes release year, episodes, duration, genres, popularity, favorites, and country of origin, which can be used during EDA to understand whether the two groups differ in important ways. Because I retrieved and filtered the records directly from the API, I also have to document my own acquisition and cleaning process rather than relying on a pre-cleaned dataset. |
| **Uncertainty Metric** | I will use bootstrapping to estimate confidence intervals for **(1) the difference in mean ratings and (2) the difference in median ratings** between the two source groups. The median is my non-CLT metric because the usual CLT-based method for a sample mean does not directly provide the sampling distribution of the median. |
| **Null Hypothesis** | In the population represented by these AniList entries, manga adaptations and light-novel adaptations have **no systematic difference in average user rating**. Equivalently, the difference in their mean AniList scores is 0. |