# Mini Data-Analysis: Deliverable 1
Stella Wiegert

Total points available: 74

# Part 0: Getting Set Up

Let’s get ready to work on this assignment!

**0.1: Install Packages**

- Install the [`diversedata`](https://diverse-data-hub.github.io/)
  package by typing the following into your **R console**:

<!-- -->

    install.packages("pak")
    library(pak)
    pak::pak("diverse-data-hub/diversedata")

**0.2: Load Packages**

Typically, R Packages are loaded in at the very beginning of the
analysis. If you later want to use other packages, please come back and
add them here:

``` r
library(tidyverse)
library(diversedata)
library(moderndive)
#--- Add any other packages below this line ---#
```

# Task 1: Choose a Data Set and Research Question

You may use one of the datasets from class or one of the datasets from
`diversedatahub`.

- **boulder-housing**: This data set contains housing information for
  the Boulder, Colorado area. *\[Add a second sentence here describing
  what the data covers — e.g., the variables included or what question
  it was collected to answer.\]*

- **squirrel-census**: Thes\[[great NYC squirrel
  census](https://www.thesquirrelcensus.com/),`squirrel-data.csv` –
  squirrel sightings recorded around Manhattan and Brooklyn parks.

- **rolling stone**: A [new visual
  essay](https://pudding.cool/2024/03/greatest-music/) from The Pudding
  compares Rolling Stone’s “500 Greatest Albums of All Time” lists from
  2003, 2012, and 2020. A methodology note says the project began with a
  spreadsheet by Chris Eckert and eventually led the authors to develop
  a dataset of their own. Theirs lists every album in the rankings — its
  name, genre, release year, 2003/2012/2020 rank, the artist’s name,
  birth year, gender, and more — plus each year’s voters. \[h/t Jason
  Kottke\]

- **coffee census**: In 2023, [British
  YouTuber](https://www.youtube.com/channel/UCMb0O2CdPBNi-QqPk5T3gsQ)
  (and former [World Barista
  Champion](https://www.jameshoffmann.co.uk/work#/coffee-competitions/))
  James Hoffman virtually hosted the [Great American Coffee Taste
  Test](https://www.youtube.com/watch?v=1fN_z4-EcOU), during which
  thousands of people simultaneously blind-tasted the same four coffees.
  Hoffman has published a [video summarizing the
  results](https://www.youtube.com/watch?v=bMOOQfeloH0), as well as [a
  spreadsheet of anonymized survey
  responses](https://bit.ly/gacttCSV+)from 4,000+ participants. It
  includes tasters’ demographics, general coffee drinking habits and
  preferences, assessments of the four coffees, and more. \[h/t Dan
  Brady\] (via
  [data-is-plural](https://www.data-is-plural.com/archive/2023-11-15-edition/))

- **wildfire**: This data set contains information on wildfires in
  Canada, compiled from official government sources under the Open
  Government Licence – Alberta. The data was gathered to monitor,
  assess, and respond to wildfire risks across different regions.
  Wildfires have far-reaching environmental, social, and economic
  consequences. From an equity and inclusion perspective, analyzing
  wildfire data can reveal geographic and resource-based disparities in
  detection and containment efforts, and highlight how certain
  populations face greater risks due to climate change and limited
  infrastructure. There are 26551 rows and 35 columns.

- **genderassessment**: Collected in 2023, the data allows for
  comparative evaluation across countries, sectors, and ownership types
  (e.g., Public, Private, Government). Each record represents a company
  and its corresponding evaluation across 28 detailed gender related
  indicators, offering a comprehensive snapshot of corporate gender
  equity worldwide. There are 2000 rows and 29 variables

- **hcmst**: This data set is adapted from the original data set [How
  Couples Meet and Stay Together 2017,
  2022](https://data.stanford.edu/hcmst2017). This study, led by
  researchers from Stanford University, surveyed 1,722 U.S. adults in
  2022 to explore how relationships form and change with time and
  focused on dating habits and the impact of the COVID-19 pandemic on
  relationships. This adapted data set focuses on variables that may
  affect the quality of the relationship, considering demographic
  characteristics of the subjects, couple dynamics, as well as
  COVID-19-related variables. The COVID-19 pandemic had a [significant
  impact](https://pmc.ncbi.nlm.nih.gov/articles/PMC10009005/) on
  romantic relationships in the United States. This data set enables
  exploration of how external factors, like the health of the subjects
  and changes in income, as well as personal behaviors, like conflict
  and intimate dynamics, relate to an individual’s perception of the
  quality of the relationship. There are 1328 rows and 21 columns.

- **womensmarchmadness**: This adapted data set contains historical
  records of every NCAA Division I Women’s Basketball Tournament
  appearance since the tournament began in 1982 up until 2018, capturing
  tournament results across more than four decades of collegiate women’s
  basketball. All data is sourced from the NCAA and contains the data
  behind the story [The Rise and Fall Of Women’s NCAA Tournament
  Dynasties](https://fivethirtyeight.com/features/louisiana-tech-was-the-uconn-of-the-80s/).
  The rise in popularity of the NCAA Women’s March Madness, fueled by
  athletes like Caitlin Clark and Paige Bueckers, reflects a broader
  cultural shift in the recognition of women’s sports. Beyond
  entertainment and athletic achievement, women’s participation in sport
  has social and professional benefits. There are 2092 rows and 20
  columns.

*Note: We encourage you to use one of the options above, but if you have
a data set that you’d really like to use, please check with a member of
the teaching team to see whether the data set is of appropriate
complexity. If approved, please add a brief description of the data
here.*

### 1.1: Choose 2 data sets **(2 points)**

Out of the 5 data sets listed above, choose **2** that appeal to you
based on their description. Write your choices below:

<!-------------------------- Start your work below ---------------------------->

1: rollingstone

2: genderassessment

<!----------------------------------------------------------------------------->

### 1.2: Explore the Data **(12 points)**

One way to narrowing down your selection is to *explore* the data sets.
Use your knowledge of `dplyr` to summarize three variables in each of
the data sets (for example, listing what levels of a categorical
variable exist, or calculating the mean of a continuous variable of
interest). Write a sentence that describes your findings for each
variable explored. You may use multiple R code chunks if preferred.

<!-------------------------- Start your work below ---------------------------->

#### Data Set 1

``` r
### Explore 3 variables of data set 1 ###
music <- read_csv("dat/RollingStone500.csv")
```

    New names:
    Rows: 691 Columns: 26
    ── Column specification
    ──────────────────────────────────────────────────────── Delimiter: "," chr
    (19): Sort Name, Clean Name, Album, Album Genre, Album Type, Wks on Bill... dbl
    (7): 2003 Rank Old, 2003 Rank, 2012 Rank, 2020 Rank, 2020-2003 Differen...
    ℹ Use `spec()` to retrieve the full column specification for this data. ℹ
    Specify the column types or set `show_col_types = FALSE` to quiet this message.
    • `` -> `...25`
    • `` -> `...26`

``` r
glimpse(music)
```

    Rows: 691
    Columns: 26
    $ `Sort Name`                             <chr> "Sinatra, Frank", "Diddley, Bo…
    $ `Clean Name`                            <chr> "Frank Sinatra", "Bo Diddley",…
    $ Album                                   <chr> "In the Wee Small Hours", "Bo …
    $ `2003 Rank Old`                         <dbl> 101, 212, 56, 302, 50, NA, NA,…
    $ `2003 Rank`                             <dbl> 100, 214, 55, 306, 50, NA, NA,…
    $ `2012 Rank`                             <dbl> 101, 216, 56, 308, 50, NA, 451…
    $ `2020 Rank`                             <dbl> 282, 455, 332, NA, 227, 32, 33…
    $ `2020-2003 Differential`                <dbl> -182, -241, -277, -195, -177, …
    $ `Release Year`                          <dbl> 1955, 1955, 1956, 1956, 1957, …
    $ `Album Genre`                           <chr> "Big Band/Jazz", "Rock n' Roll…
    $ `Album Type`                            <chr> "Studio", "Studio", "Studio", …
    $ `Wks on Billboard`                      <chr> "14", "-", "100", "?", "5", "8…
    $ `Peak Billboard Position`               <dbl> 2, 201, 1, 2, 13, 1, 2, 201, 3…
    $ `Spotify Popularity`                    <chr> "48", "50", "58", "62", "64", …
    $ `Spotify URI`                           <chr> "spotify:album:3GmwKB1tgPZgXeR…
    $ `Chartmetric Link`                      <chr> "https://app.chartmetric.com/a…
    $ `Artist Member Count`                   <chr> "1", "1", "1", "1", "1", "1", …
    $ `Artist Gender`                         <chr> "Male", "Male", "Male", "Male"…
    $ `Artist Birth Year Sum`                 <chr> "1915", "1928", "1935", "1915"…
    $ `Debut Album Release Year`              <chr> "1946", "1955", "1956", "1946"…
    $ `Avg. Age at Top 500 Album`             <chr> "40", "27", "21", "41", "25", …
    $ `Years Between Debut and Top 500 Album` <chr> "9", "0", "0", "10", "0", "13"…
    $ `Album ID`                              <chr> "3GmwKB1tgPZgXeRJZSm9WX", "1cb…
    $ `Album ID Quoted`                       <chr> "\"3GmwKB1tgPZgXeRJZSm9WX\",",…
    $ ...25                                   <chr> NA, NA, NA, NA, NA, NA, NA, NA…
    $ ...26                                   <chr> NA, NA, NA, NA, NA, NA, NA, NA…

``` r
music |>
  mutate(weeks = as.numeric(`Wks on Billboard`)) |>
  arrange(desc(weeks))
```

    Warning: There was 1 warning in `mutate()`.
    ℹ In argument: `weeks = as.numeric(`Wks on Billboard`)`.
    Caused by warning:
    ! NAs introduced by coercion

    # A tibble: 691 × 27
       `Sort Name`     `Clean Name`   Album  `2003 Rank Old` `2003 Rank` `2012 Rank`
       <chr>           <chr>          <chr>            <dbl>       <dbl>       <dbl>
     1 Pink Floyd      Pink Floyd     The D…              43          43          43
     2 Adele           Adele          21                  NA          NA          NA
     3 Lamar, Kendrick Kendrick Lamar good …              NA          NA          NA
     4 Drake           Drake          Take …              NA          NA          NA
     5 Swift, Taylor   Taylor Swift   1989                NA          NA          NA
     6 Rihanna         Rihanna        Anti                NA          NA          NA
     7 Ocean, Frank    Frank Ocean    Blonde              NA          NA          NA
     8 Lamar, Kendrick Kendrick Lamar DAMN                NA          NA          NA
     9 SZA             SZA            Ctrl                NA          NA          NA
    10 King, Carole    Carole King    Tapes…              36          36          36
    # ℹ 681 more rows
    # ℹ 21 more variables: `2020 Rank` <dbl>, `2020-2003 Differential` <dbl>,
    #   `Release Year` <dbl>, `Album Genre` <chr>, `Album Type` <chr>,
    #   `Wks on Billboard` <chr>, `Peak Billboard Position` <dbl>,
    #   `Spotify Popularity` <chr>, `Spotify URI` <chr>, `Chartmetric Link` <chr>,
    #   `Artist Member Count` <chr>, `Artist Gender` <chr>,
    #   `Artist Birth Year Sum` <chr>, `Debut Album Release Year` <chr>, …

``` r
  #filter(weeks > 600)
```

``` r
music |>
  mutate(weeks = as.numeric(`Wks on Billboard`)) |>
  group_by(`Album Genre`) |>
  summarize(mean_wks = mean(weeks, na.rm = TRUE)) |>
  arrange(desc(mean_wks))
```

    Warning: There was 1 warning in `mutate()`.
    ℹ In argument: `weeks = as.numeric(`Wks on Billboard`)`.
    Caused by warning:
    ! NAs introduced by coercion

    # A tibble: 17 × 2
       `Album Genre`                       mean_wks
       <chr>                                  <dbl>
     1 Hard Rock/Metal                         89  
     2 Singer-Songwriter/Heartland Rock        86.8
     3 Hip-Hop/Rap                             85.6
     4 Soul/Gospel/R&B                         79.2
     5 Indie/Alternative Rock                  74.3
     6 <NA>                                    62.1
     7 Country/Folk/Country Rock/Folk Rock     58.4
     8 Latin                                   54.6
     9 Funk/Disco                              49.2
    10 Rock n' Roll/Rhythm & Blues             47.8
    11 Blues/Blues Rock                        46.7
    12 Electronic                              45.9
    13 Punk/Post-Punk/New Wave/Power Pop       42.8
    14 Blues/Blues ROck                        42  
    15 Big Band/Jazz                           36.8
    16 Reggae                                  17.1
    17 Afrobeat                               NaN  

``` r
music |>
  mutate(weeks = as.numeric(`Wks on Billboard`)) |>
  #filter(`Artist Gender` %in% c("Male", "Female")) |>
  group_by(`Artist Gender`) |>
  summarize(total_weeks = sum(weeks, na.rm = TRUE))
```

    Warning: There was 1 warning in `mutate()`.
    ℹ In argument: `weeks = as.numeric(`Wks on Billboard`)`.
    Caused by warning:
    ! NAs introduced by coercion

    # A tibble: 4 × 2
      `Artist Gender` total_weeks
      <chr>                 <dbl>
    1 Female                 7142
    2 Male                  26974
    3 Male/Female            2647
    4 N/A                       0

Write your findings here.

The first variable I investigated was which albums spent the longest
time on the Billboard top 100. By arranging the greatest albums of all
time according to that metric, we can see that Pink Floyd’s Dark Side of
the Moon, Adele’s 21, and Kendrick Lamar’s good kid, m.A.A.d city spent
the longest time on that chart. Additionally, I also investigated which
album genre on had the most time on the Billboard charts, with the top
being Hard Rock/Metal and the bottom being Reggae (although there is an
anomoly with the Afrobeat genre that will require further
investigation). The last variable I investigated was how the gender of
the artist affected the time the album spent on the Billboard chart,
with males artists signficicantly outnumbering the female and mixed
group albums.

#### Data Set 2

``` r
### Explore 3 variables of data set 2 ###
glimpse(genderassessment)
```

    Rows: 2,000
    Columns: 29
    $ company                           <chr> "3M", "Asos", "A.P. Moller - Maersk"…
    $ country                           <chr> "United States", "United Kingdom", "…
    $ region                            <chr> "North America", "Europe & Central A…
    $ industry                          <chr> "Chemicals", "Apparel & Footwear", "…
    $ ownership                         <chr> "Public", "Public", "Public", "Publi…
    $ year                              <dbl> 2023, 2023, 2024, 2023, 2023, 2023, …
    $ score                             <dbl> 11.3, 16.9, 10.9, 12.8, 15.4, 10.0, …
    $ percent_score                     <dbl> 22, 32, 21, 25, 30, 19, 24, 25, 0, 1…
    $ strategic_action                  <dbl> 1, 1, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, …
    $ gender_targets                    <dbl> 0, 0, 1, 1, 0, 1, 1, 0, 0, 1, 0, 0, …
    $ gender_due_diligence              <dbl> 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 0, …
    $ grievance_mechanisms              <dbl> 0.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2…
    $ stakeholder_engagement            <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
    $ corrective_action                 <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
    $ gender_leadership                 <dbl> 0, 3, 0, 0, 2, 1, 1, 2, 0, 0, 0, 1, …
    $ development_recruitment           <dbl> 0, 1, 1, 1, 1, 0, 0, 1, 0, 1, 2, 0, …
    $ employee_data_by_sex              <dbl> 0, 0, 0, 0, 0, 0, 0, 2, 0, 0, 1, 3, …
    $ supply_chain_gender_leadership    <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
    $ enabling_environment_union_rights <dbl> 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
    $ gender_procurement                <dbl> 1, 0, 0, 0, 1, 0, 0, 2, 0, 0, 0, 0, …
    $ gender_pay_gap                    <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 2, 0, …
    $ carer_leave_paid                  <dbl> 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 2, 0, …
    $ childcare_support                 <dbl> 0, 1, 0, 0, 2, 0, 0, 1, 0, 1, 2, 2, …
    $ flex_work                         <dbl> 2, 1, 0, 0, 1, 1, 2, 2, 0, 0, 0, 1, …
    $ living_wage_supply_chain          <dbl> 0, 2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
    $ health_safety                     <dbl> 1.0, 0.5, 1.0, 1.0, 1.0, 1.0, 0.5, 0…
    $ health_safety_supply_chain        <dbl> 2, 2, 2, 2, 2, 2, 1, 0, 0, 1, 2, 2, …
    $ violence_prevention               <dbl> 1.0, 0.5, 1.0, 1.0, 1.0, 1.0, 1.0, 1…
    $ violence_remediation              <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …

``` r
#country that had highest average score
#company that had highest score
#What score category had the most zeroes
```

``` r
genderassessment |> #country that had highest average score
  group_by(country) |>
  summarize(mean_score = mean(score)) |>
  arrange(desc(mean_score))
```

    # A tibble: 87 × 2
       country     mean_score
       <chr>            <dbl>
     1 Cyprus            17.3
     2 Portugal          15.9
     3 Czechia           14.3
     4 Hungary           13.2
     5 Spain             13.1
     6 Greece            12.6
     7 Australia         12.4
     8 Italy             12.1
     9 New Zealand       11.9
    10 Finland           11.7
    # ℹ 77 more rows

``` r
#company that had highest score
genderassessment |>
  group_by(company) |>
  summarize(mean_score = mean(score)) |>
  arrange(desc(mean_score))
```

    # A tibble: 2,000 × 2
       company    mean_score
       <chr>           <dbl>
     1 Eni              26.9
     2 HPE              26.7
     3 Caixabank        25.2
     4 Kering           24  
     5 SONY             23.9
     6 Inditex          23.7
     7 Firmenich        23.4
     8 Hershey          23.4
     9 Merck & Co       23.3
    10 Falabella        23.2
    # ℹ 1,990 more rows

``` r
genderassessment |>
  filter(company == "Eni")
```

    # A tibble: 1 × 29
      company country region            industry ownership  year score percent_score
      <chr>   <chr>   <chr>             <chr>    <chr>     <dbl> <dbl>         <dbl>
    1 Eni     Italy   Europe & Central… Oil & G… Public     2023  26.9            51
    # ℹ 21 more variables: strategic_action <dbl>, gender_targets <dbl>,
    #   gender_due_diligence <dbl>, grievance_mechanisms <dbl>,
    #   stakeholder_engagement <dbl>, corrective_action <dbl>,
    #   gender_leadership <dbl>, development_recruitment <dbl>,
    #   employee_data_by_sex <dbl>, supply_chain_gender_leadership <dbl>,
    #   enabling_environment_union_rights <dbl>, gender_procurement <dbl>,
    #   gender_pay_gap <dbl>, carer_leave_paid <dbl>, childcare_support <dbl>, …

``` r
#What score category had the most zeroes
genderassessment |>
  pivot_longer(
    cols = !c(company, country, region, industry, ownership, year, score, percent_score),
    names_to = "category",
    values_to = "value"
  ) |>
  group_by(category) |>
  summarize(total_score = sum(value, na.rm = TRUE)) |>
  arrange(total_score)
```

    # A tibble: 21 × 2
       category                          total_score
       <chr>                                   <dbl>
     1 supply_chain_gender_leadership             3 
     2 enabling_environment_union_rights         29 
     3 stakeholder_engagement                    42 
     4 violence_remediation                      46 
     5 living_wage_supply_chain                  84 
     6 corrective_action                        126.
     7 gender_pay_gap                           136 
     8 gender_due_diligence                     161 
     9 gender_procurement                       406 
    10 carer_leave_paid                         464.
    # ℹ 11 more rows

Write your findings here.

The first variable I investigated was which country had the overall
highest score across all the gender-equality metrics with all the
companies that are based in it. The top three were Cyprus, Portugal, and
Czechia, while the bottom three that had any data/companies to score
were Congo, Dem. Rep., Angola, and Vietnam. The next variable I
investigated was which company had the highest overall gender-equality
score, which was Eni, which is an oil and gas company based in Italy,
while the lowest scoring company was tied across six companies, with a
total range in the score of all the companies scored of 26.9-8.2=18.7
points. Lastly, I also investigated which category of scoring had the
best overall score across all the companies, which was
grievance_mechanisms, and which category was the lowest scoring category
overall, which was supply_chain_gender_leadership. Notably,
gender_pay_gap was not the lowest-scoring category, indicating that
getting more women into leadership roles could become more of a primary
advocacy concern in addition to equal gender pay.

<!----------------------------------------------------------------------------->

### 1.3: Choose 1 Data Set **(2 points)**

It’s time to choose only one data set. State the data set that you’ve
chosen, and why you’ve chosen it.

<!-------------------------- Start your work below ---------------------------->

I have chosen the genderassessment dataset because I want to explore
further the relationship between different score categories and see if
companies that score lower in certain categories (leadership categories)
have an associated lower score in other categories (pay-related
categories). Additionally, although on the surface it seems like there
is a lot more cleaning to do in the rolling stone dataset, I think
there’s a lot more exploratory potential and inference potential in the
genderassessment dataset that I’m curious about. These are the reasons
that I have chosen this dataset.

<!----------------------------------------------------------------------------->

### 1.4: Research Question **(4 points)**

Let’s choose a primary and a secondary research question to explore.

Write your research questions **as questions**, and be specific. You can
change it later if needed.

> For example, if I had chosen a `titanic` data set for my project, I
> might ask, “(Primary) Is there a relationship between survival and the
> class of the passengers? (Secondary) Does this relationship differ by
> gender?”

<!-------------------------- Start your work below ---------------------------->

Is there a relationship between scores in leadership-measuring
categories and pay-related categories? Does this differ by type of
company and across regions?

<!----------------------------------------------------------------------------->

### 1.5: Commit **(2 points)**

Commit your work and push it to GitHub. Include an informative commit
message, and include “(1.5)” in the message.

# Task 2: Further Exploring Your Chosen Data Set

### 2.1: Missing Data **(6 points)**

Missing data is inevitable, and can complicate analyses. Let’s see what
variables (if any) have missing data in your chosen data set.

Your task is to create a table that calculates the proportion of missing
values per variable. Be sure to output the table.

<!-------------------------- Start your work below ---------------------------->

``` r
### Explore missingness here ###
genderassessment |>
  pivot_longer(
    names_to = "category",
    values_to = "value", 
    cols = company:violence_remediation,
    values_transform = as.character
  ) |>
  group_by(category) |>
  summarize(missingness = sum(is.na(value)),
            pct_missingness = mean(is.na(value)) * 100) |>
  arrange(desc(missingness))
```

    # A tibble: 29 × 3
       category                          missingness pct_missingness
       <chr>                                   <int>           <dbl>
     1 industry                                    5            0.25
     2 ownership                                   4            0.2 
     3 carer_leave_paid                            0            0   
     4 childcare_support                           0            0   
     5 company                                     0            0   
     6 corrective_action                           0            0   
     7 country                                     0            0   
     8 development_recruitment                     0            0   
     9 employee_data_by_sex                        0            0   
    10 enabling_environment_union_rights           0            0   
    # ℹ 19 more rows

<!----------------------------------------------------------------------------->

### 2.2: Missing Data (Again) **(6 points)**

Based on your research question, will this missingness pose an issue?
For the purposes of this class (and this class only!), we will consider
missingness a problem **if there is more than 20% of a single variable
(that is of interest) is missing**.

> For example, let’s assume I wanted to explore the following research
> questions: “Is there a relationship between survival and the class of
> the passengers? Does this relationship vary by gender?”. If the
> variable indicating whether or not a person survived was missing for
> 20% or more of the passengers, then this would be a problem. However,
> if a variable indicating the colour of shirt a passenger was wearing
> was missing, this probably wouldn’t be an issue as that variable is
> quite irrelevant to my analysis!

Based on this definition, is missingness an issue for your analysis? If
so, describe how you will address this (pivoting your research question,
for example). If you will continue with a new research question, write
it here! **Do not go back to Task 1 and redo the analysis.** ).

If missingness is not an issue, describe why.

<!-------------------------- Start your work below ---------------------------->

Missingness is not an issue in this data because the only missing values
for my data are in the industry and ownership categories that describe
the companies that were scored. Even then, there is \<1% missingness in
both of these variables, meaning that even though the industry is
relevant to our research question, it will not significantly affect our
analysis.

<!----------------------------------------------------------------------------->

### 2.3: Tidy your Data **(10 points)**

Produce a tidy data set that could be used to answer your research
questions. **Please ensure you have at least one quantitative (numeric)
and one categorical variable in your data set. It’s okay you need to
include a less relevant variable in your tidied data to ensure this.**

To tidy your data, you should:

- Create new variables (if needed)

- Transform the data into a tidy form (if needed)

- Remove irrelevant columns (if needed)

- Comment your code throughout

Show the first 6 rows of the tidied data.

<!-------------------------- Start your work below ---------------------------->

``` r
genderassessment |>
  select(company, region, industry, ownership, score, gender_leadership,
         supply_chain_gender_leadership,
         gender_pay_gap, carer_leave_paid, living_wage_supply_chain) -> gender_analysis #selecting the columns form the dataset that we want to 
#compare and the information about the companies
  
gender_analysis |>
  head(6) #displaying the first 6 rows of data - no further tidying needed because each row is one 
```

    # A tibble: 6 × 10
      company              region         industry ownership score gender_leadership
      <chr>                <chr>          <chr>    <chr>     <dbl>             <dbl>
    1 3M                   North America  Chemica… Public     11.3                 0
    2 Asos                 Europe & Cent… Apparel… Public     16.9                 3
    3 A.P. Moller - Maersk Europe & Cent… Freight… Public     10.9                 0
    4 ABB                  Europe & Cent… Capital… Public     12.8                 0
    5 AbbVie               North America  Pharmac… Public     15.4                 2
    6 Abercrombie & Fitch  North America  Apparel… Public     10                   1
    # ℹ 4 more variables: supply_chain_gender_leadership <dbl>,
    #   gender_pay_gap <dbl>, carer_leave_paid <dbl>,
    #   living_wage_supply_chain <dbl>

``` r
#observation (company) with each column containing one variable and each cell containing a value for that variable and observation - this could then be used to answer my research questions from above
```

<!----------------------------------------------------------------------------->

### 2.4: Create a Table (10 points)

Use any functions from the `tidyverse` to create one table that outputs
the mean, minimum, and maximum of all numeric columns in your data,
dropping the missing values if they exist.

Show the outputted table.

<!-------------------------- Start your work below ---------------------------->

``` r
gender_analysis |>
  pivot_longer(
    cols = score:living_wage_supply_chain,
    names_to = "variable",
    values_to = "value"
  ) |> #tidying needed here to be able to summarize the numerical variables like this, but not needed 
  #above because then would not be able to answer my by region/company question from above
  group_by(variable) |>
  summarize(
    mean = mean(value, na.rm = TRUE),
    max = max(value, na.rm = TRUE),
    min = min(value, na.rm = TRUE)
  )
```

    # A tibble: 6 × 4
      variable                          mean   max   min
      <chr>                            <dbl> <dbl> <dbl>
    1 carer_leave_paid               0.232     4       0
    2 gender_leadership              0.448     4       0
    3 gender_pay_gap                 0.068     3       0
    4 living_wage_supply_chain       0.0420    2       0
    5 score                          7.99     26.9     0
    6 supply_chain_gender_leadership 0.00150   1       0

<!----------------------------------------------------------------------------->

### 2.5: Commit **(2 points)**

Commit your work and push it to GitHub. , and include “(2.7)” in the
message.

# Task 3: Tidy Your Submission Overall

Check over your document and GitHub repository for the following:

### 3.1: Coherence **(2 points)**

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

### 3.2: Error-free code **(2 points)**

For full marks, all code in the document should run without error and be
completely reproducible.

### 3.3 README **(6 points)**

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- List the files/folders contained in the repository
- In a sentence or two, briefly explains how to engage with the
  repository. You can assume the person reading knows the material from
  STAT 545A. Basically, if a visitor to your repository wants to explore
  your project, what should they know? How can they reproduce your
  report?

### 3.4 Generative AI Disclosure **(3 points)**

In this course, Generative AI can be used in the following ways:

- to clarify concepts discussed in class

- as an “advanced search engine” (i.e., searching error codes)

- debugging code that students wrote and attempted to debug on their own

Generative AI **CANNOT** be used to generate text or code (including
comments) from scratch.

Any use of Generative AI must be disclosed.

**To disclose your use, please copy and paste the following template
into the README of your GitHub Repository and fill out the relevant
details** \[in square brackets\]. BE SPECIFIC. Saying you used it to
debug your code is not enough. Explicitly describe where you got stuck

Here is an example of a specific, explicit debug:

> “I had the error `attempt to apply non-function` after running my
> code. I used Claude to help me identify that this error was due to me
> attempting to multiply two numbers together without the use of a `*`,
> i.e. `(2)(3)` instead of `2*3`.”

``` markdown

## Generative AI Statement

Generative AI (through [LIST MODELS USED, i.e. ChatGPT, CoPilot)] was used to
help me complete  this assignment in the following ways.

1. [Describe here]

2. [Describe here]

...

I affirm that Generative AI was not used to generate text, code, or comments for
my assessments.
```

If you did not use Generative AI, please include the following in your
README:

``` markdown

## Generative AI Statement

Generative AI was not used in any way throughout this assignment.
```

Assessments suspected of having AI-generated text and/or code, or
assignments where the Generative AI use was not disclosed, will be
flagged and temporarily assigned a grade of zero. Students will be
required to meet with the instructor to receive a grade.

### 3.5 Output **(4 points)**

All output on GitHub is readable, recent and relevant:

- All `.qmd` files have been rendered to their output `.md` files.
- All rendered `.md` files are viewable without errors on Github.
  Examples of errors: Missing plots, “Sorry about that, but we can’t
  show files that are this big right now” messages, error messages from
  broken R code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (`.qmd`) files have been updated.
- There should be no relic output files. For example, if you were
  rendering a `.qmd` to `.html`, but then changed the output to be only
  a markdown file, then the `.html` file is a relic and should be
  deleted.

# Step 4: Submission

\*\* Submit repo link \*\*

To submit this milestone, submit the github link to the repo.

This assignment was authored by the team of instructors at University of
British Colombia’s STA 545 class.
