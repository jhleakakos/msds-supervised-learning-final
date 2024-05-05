## To-Do list

I am using JetBrains' DataSpell IDE for this project. It is essentially a nice JetBrains IDE experience wrapped around Jupyter notebooks. Normally JetBrains IDEs have built-in support for to-dos, but I cannot get it working for DataSpell. So I will use a separate markdown codeblock here to track outstanding items.

### Notes from Published Paper

- Researchers looked at yes/no decisions separate from matches
- Four minute speed dates
- Participants were students in graduate and professional schools at Columbia University (selection bias maybe)
- Score card
    - Yes/No (main variable of interest)
        - Decision$_{ij}$ is the decision of subject *i* about person *j*
    - Six attributes to rate the other person on
        - Attractive
        - Sincere
        - Intelligent
        - Fun
        - Ambitious
        - Shared interests
- Women stayed seated and men rotated
- Study primarily looks at differential gender effects
    - Male$_i$ indicator variable
- Study only looks at attractiveness, intelligence, and ambition. The omitted characteristics had similar weights.
    - Rating$_ijc$ is subject *i's* rating on a ten-point scale about *j* on characteristic *c* $\in$ {Attractiveness, Intelligence, Ambition}
    - Observations that have missing values for one of these three characteristics are omitted from the regression
    - $\bar{Rating}_{-ijc}$ is the average rating for a characteristic from everyone who rated person *j* and the $-i$ means that *i* is excluded from this average
- There are a few log measures for SAT at undergrad institution, median income in zip code, and population density in zip code
- Self$_{ic}$ is subject *i's* rating for themselves on characteristic *c*
    - Others$_{ic}$ is how others who rated *i* rated them on *c*
- Each participant did a pre-event survey where the researchers gathered some of the non-event data about subjects
- Pre-event survey is used to determine ahead of time a few measures SameABC$_{ij}$ to say if the two people had the same ABC attribute
- Yeses%_i$ and other related measures relate to how many people *i* said yes to
- Table 2a shows descriptive statistics. Maybe include a section in the project that does some summary descriptive statistics to orient ourselves to the data. Also look at table 2b
- Page 685 starts to have some conditions and assumptions about men fearing rejection leading to lower desire for more intelligent or more ambitious women. Also asks why there is a difference in fear of rejection between genders. At least the paper is starting to question some of these things.
- Some survey results are subjective (ratings) and others are objective (SAT, zip code, etc)
    - Objective data is much more sparse if you try to include all three features
- In pre-event survey, participants rated their interest in seventeen activities and has SharedInterests features to compare between participants
 
### Project Cell

- Clarify focus on match vs decision
- Scope down and refine focus of analysis

### Loading and Initial Exploration Cell

- Determine the right scope for summary and initial EDA
- Plan for how to tackle the large feature space, making sure to incorporate details from the paper about the different groups of categorical variables

### Preprocessing Cell

- Look at categorical features and decide what types of mappings need to happen (numerical to string categories).
- Handle missing values
- Handle outliers
- Start figuring out when and how to substitute in factor levels for categorical variables (likely much later on after modeling since we'll want categorical variables as numbers for ML purposes)

### Model Identification Cell

- Explain the different models to explore and how we expect performance differences as well as the differences in what the models can tell us
