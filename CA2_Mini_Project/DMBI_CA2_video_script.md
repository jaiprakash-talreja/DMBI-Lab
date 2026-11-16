# BlackSpot Miner: CA2 video script

Written from the speaker notes. Record the slides from `CA2 DMBI Group 09.pptx`, about 12 to 15 minutes in total. Change the speaker split if your team prefers.

## Slide 1: Slide 1

**Speaker: Jaiprakash**

Good morning. We are Group 9. Our project is BlackSpot Miner. We took five years of real police collision records and asked a practical question: if a road authority has a limited safety budget, where should it spend it? KSI on these slides means killed or seriously injured.

## Slide 2: Slide 2

**Speaker: Jaiprakash**

Road crashes kill about 1.19 million people a year, and India recorded about 1.72 lakh deaths in 2023. An authority can only treat a limited number of sites. Ranking last year's worst sites is the common answer, but bad years are partly bad luck. So we split the problem into three questions: where, why and what next. Our reference paper mined road accidents in Dehradun. It used clustering and association rules but no prediction and no test on later data, and that is the gap we build on.

## Slide 3: Slide 3

**Speaker: Jaiprakash**

This is the same process from our CA1 case study, now implemented. One prepared data set feeds three branches: hotspots, rules and prediction. All three feed one decision. Everything is tested on 2025, a year never used in mining or training. Over to Adarsh for the data.

## Slide 4: Slide 4

**Speaker: Adarsh**

Our data is the UK Department for Transport STATS19 record: 513,801 collisions, 937,265 vehicles and 652,821 casualties. Before modelling we checked every field year by year, and that found a trap. Police forces have been moving to injury-based reporting, which classifies more injuries as serious. On the left, that share jumped from 49.6 to 86.5 percent. On the right, the raw severe share rises faster than the adjusted one. So raw severity is not comparable across years. We used DfT's adjusted figures for location work and injury-based records only for rules and severity models.

## Slide 5: Slide 5

**Speaker: Adarsh**

Four decisions shaped the data. We joined the vehicle and casualty tables to learn who was involved. We removed leakage: anything known only after the outcome, such as the number of casualties. We dropped fields that are empty in recent years. And we split by time, because a random split lets a model see the future, which a real authority never can. This leaves 309,041 injury-based records for rules and severity, and 513,745 records for location ranking.

## Slide 6: Slide 6

**Speaker: Adarsh**

This heatmap is the chance that a collision is KSI, by who was involved and the speed limit. Read along the pedestrian row: 33 percent at 30 mph, 46 at 40 and 51 at 60. The multi-vehicle row rises far less. Severity peaks on 60 mph roads, not motorways, and the most dangerous hours by rate are in the early morning, even though the most KSI collisions happen on weekday afternoons.

## Slide 7: Slide 7

**Speaker: Adarsh**

We used DBSCAN because a black spot is a small dense patch and most severe crashes are isolated. K-Means would force every crash into a cluster. We tested 16 settings and required the largest cluster to stay under one kilometre, which gave eps 100 metres and min samples 6. Hotspots rediscovered on past years collected 4.79 times as many 2025 KSI collisions per square kilometre as random past locations. But 93.89 percent of KSI collisions are outside any hotspot, so hotspot work alone cannot solve the problem. Over to Vidushi.

## Slide 8: Slide 8

**Speaker: Vidushi**

Apriori ran on 221,193 collisions from 2021 to 2024. Lift tells us how many times more likely KSI is under a condition than overall. We filtered 1,657 rules down to 109, then tested them on 2025. 107 kept a lift of at least 1.2. Blue is the mined period and orange is unseen 2025, and they barely differ. The strongest rule is a motorcycle leaving the road, where KSI is 66.7 percent likely in the mined period and 59.1 in 2025.

## Slide 9: Slide 9

**Speaker: Vidushi**

Kumar and Toshniwal claimed that clustering first reveals rules the whole data set hides. They had 11,574 accidents from Dehradun. We repeated it with their k of 6 on 221,193 collisions from Britain. K-Modes suits categorical data because a mean of lighting types has no meaning. The segments range from 16.7 to 38.6 percent KSI. We found 60 rules that appear only inside segments, and we added a test the paper did not run: 55 of them held on 2025. So the claim survives on a much larger data set in a different country.

## Slide 10: Slide 10

**Speaker: Vidushi**

We trained four syllabus classifiers, tuned them on 2024 and tested once on 2025. Random Forest was best with PR-AUC 0.440, against 0.27 by chance. Accuracy looks low at 56.9% because the threshold favours recall. Predicting Slight for everything scores 73.0% and catches nobody. Severity depends on things the police form does not record, such as impact speed and seat belt use. A much higher score on data like this would make us check for leaked columns. We use this model to explain risk, not to predict single crashes. Over to Piyush.

## Slide 11: Slide 11

**Speaker: Piyush**

Budgets are spent on places, so we moved to 500 metre grid cells. Three past years of features predict the next year, and we tested on 2025. Poisson boosting reached ROC-AUC 0.764 against 0.680 for ranking by past KSI count. At 5,000 sites it covers 2.13 more percentage points of KSI, and the bootstrap interval excludes zero. The gain is small at the very top, so we do not oversell it. Then the trap: the 100 worst cells of 2024 fell 39.8 percent the next year, and the data records no treatment. That is what regression to the mean predicts, and it is why worst-site lists can look better than they are.

## Slide 12: Slide 12

**Speaker: Piyush**

This is the decision. We refit on the latest data and scored 2023 to 2025 to give a list for 2026. Each site gets a suggested review type from its own collision mix. 98 percent of the top 100 sites lie within 750 metres of a DBSCAN hotspot, so two independent methods agree on where the problem is. The review type is a prompt for an engineer, not a model prediction, and we claim no crash reduction. The interactive map and the full list of 1,000 sites are in our GitHub repository.

## Slide 13: Slide 13

**Speaker: Piyush**

To close: we can stand behind these results because each was tested on a year the methods never saw. We are equally clear about the limits. There is no traffic volume data, so busy places rank high partly because they are busy, and we show association, not cause. Our code, notebook, report and interactive map are on GitHub. Thank you, and we are open for your questions.
