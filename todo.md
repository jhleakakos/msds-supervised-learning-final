## To-Do list

I am using JetBrains' DataSpell IDE for this project. It is essentially a nice JetBrains IDE experience wrapped around Jupyter notebooks. Normally JetBrains IDEs have built-in support for to-dos, but I cannot get it working for DataSpell. So I will use a separate markdown codeblock here to track outstanding items.

### Column Notes

Next is to narrow the feature space down to what we will use for modeling. Note that the only categorical variable that will need encoding is `goal`. I am treating the 1-10 ratings as discrete numeric variables instead of as ordinal categorical variables since the current numeric encoding captures the order that we want for them.

Here are the features that we will keep:
- gender (boolean): indicates if participant is male or female
- int_corr (continuous & in range [-1, 1]): correlation between ratings of interests between date participants; this summarizes down participants' interest ratings for a group of 17 activities
- age_o (continuous & in range [18,55]): partner's age
- age (continuous & in range [18,55]): participant's age
- goal (categorical): participant's primary goal in participating in event
    1. Seemed like a fun night out
    2. To meet new people
    3. To get a date
    4. Looking for a serious relationship
    5. To say I did it
    6. Other
- exphappy (discrete & in range [1,10]): how happy participant expects to be with people they meet at event

From here onwards, we encounter repetitions of the six attributes above. I will provide headers that explain what the repetitions are asking about instead of adding that as a description for each feature.

Here are the abbreviations:

- attr#_#: attractive
- sinc#_#: sincere
- intel#_#: intelligent
- fun#_#: fun
- amb#_#: ambitious
- shar#_#: shared interests

The data dictionary says that waves 6-9 rate some groups of these features on a 1-10 scale while the remaining waves distribute 100 points across all five or six features. Some feature groupings that the dictionary indicates should be [1,10] are already rescaled to [0,100] such that the total of all of the features in the grouping for each row sum to 100, so the standardization turned [1,10] ratings into relative ratings on a [1,100] percentage scale. For groupings that require further standardization, we will do the same by summing the total for the grouping for a row and standardize it if the amount does not sum to 100. The one case we may be missing out on here is if someone gives 10s for all of the attributes on a 1-10 scale, but those would get rescaled to 10s anyways.

This means that the data type for each of these columns will end up being continuous & in range [0,100].

Now, back to the columns.

These six features are related to what the participant looks for in the opposite sex:
- attr1_1
- sinc1_1
- intel1_1
- fun1_1
- amb1_1
- shar1_1

The next six features are what the participant thinks most of their fellow men/women look for in the opposite sex:
- attr4_1
- sinc4_1
- intel4_1
- fun4_1
- amb4_1
- shar4_1

The next six features are what the participant thinks the opposite sex looks for in a date:
- attr2_1
- sinc2_1
- intel2_1
- fun2_1
- amb2_1
- shar2_1

The next five features are how the participant rates themselves (discrete & in range [1,10]):
- attr3_1
- sinc3_1
- intel3_1
- fun3_1
- amb3_1

The next five features are how the participant thinks others would rate them (discrete & in range [1,10]):
- attr5_1
- sinc5_1
- intel5_1
- fun5_1
- amb5_1

Moving on to information collected at the dates:
- dec (boolean): does the participant want to meet their date partner again

Next is how the participant rates their date on the six attributes from above (discrete & in range [1,10]):
- attr
- sinc
- intel
- fun
- amb
- shar

And two final features related to the specific date:
- like (discrete & in range [1,10]): how much the participant likes their date overall
- prob (discrete & in range [1,10]): how probable do you think it is that your partner will want to see you again
 
### Model Identification Cell

- Explain the different models to explore and how we expect performance differences as well as the differences in what the models can tell us
