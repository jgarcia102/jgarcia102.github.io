---
title: "Data Visualization: Analyzing Effectiveness of MLB Pitcher's Changeups"
date: 2018-07-14
tags: [data visualization, MLB, Tableau]
header:
  image: "/images/Strikeout.jpg"
excerpt: "Data Visualization, MLB, Tableau"
---
#### *John Garcia*
#### *July 14, 2018*

When I was younger, I was fascinated by Major League Baseball. I would watch two
or three games a week and watch highlights on Baseball Tonight as often as I could.
My favorite games to watch showcased hitters or pitchers playing at their best. I
enjoyed watching high scoring games or dominating pitching performances.

One of my favorite pitchers to watch in the mid-2000s was Johan Santana of the Twins.
Santana threw a mid-90s fastball, a slider, and a changeup with excellent command,
and would make batters loo silly with some of the swings they took, especially on
changeups. I always wondered though, what made changeups effective? Fastballs are
easy, look at velocity, movement, and control. Curveball and slider effectiveness
can be determined by movement and control. For changeups, there are the obvious
factors: control, movement, and choosing the right count to throw it in. But what
about the difference in velocity between the pitcher's fastball and changeup? If
the batter is supposed to be fooled by the changeup's velocity, does movement even
matter? I looked at data from changeups by Major League pitchers and find out what
makes changeups effective.

I used the PITCHf/x data from fangraphs.com to do my analysis. The PITCHf/x data
provides data on horizontal and vertical movement of changeups. It also collected
fastball data from each pitcher, since I want to look at the difference in velocity
between a pitcher's fastball and changeup. To determine a pitcher's effectiveness,
I will be looking at three measure of performance: batting average against, strikeout
rate, and the pitch type linear weight(often called "pitch value") for the pitchers
changeup. Pitch value for a pitcher's change up will look at all of the changeups
a pitcher threw in a season and look at how well a batter performed against them
based on the run expectancy of the count the changeup was thrown in. For more
information on pitch value, fangraphs has an [in-depth explanation](https://www.fangraphs.com/library/pitching/linear-weights/).

Before I made any visualizations in Tableau, I had to pre-process and filter the
data. Many pitchers threw more than one type of fastball and some pitchers didn't
throw a changeup. When I looked at a pitchers fastball, I only looked at the fastball
the pitcher threw most frequently. For reference, there are three types of fastballs
primarily thrown: 4-seam fastball, 2-seam fastball and a cutter. I calculated the
change in velocity between a pitcher's most frequently thrown fastball and their
changeup. For movement, PITCHf/x provides horizontal movement and vertical movement
for changeups. I used the Pythagorean Theorem to calculate total movement.

When I made my visualizations, I wanted to see if there was an optimal difference
in velocity between a pitchers fastball and changeup, and I wanted to see how
important movement was. My first graph has velocity change on the x-axis and
movement on the y-axis. Each point is colored by the pitch value. A high pitch
value indicates an effective changeup, and is colored red. A low pitch value is
colored blue. I applied one more filter to the data. I filtered out pitchers that
had a changeup that was faster than their fastball since those were most likely
classification errors by PITCHf/x. You can search for your favorite pitcher in
the search window, but he will not show up if he does not throw a changeup.

{% include Tableau_Pitch_Value.html %}

The graph provided an few insights. I was not sure how much movement would contribute
to a changeups effectiveness. I would have thought that if anything when I filtered
for pitchers with an effective changeup, the boundaries for the distribution would
have been higher. It turns out that the average changeup movement for effective
changeups is the same as for ineffective changeups, but the range in distribution
increases.

The graph provides the same insight for velocity change. The average velocity change
between effective and ineffective changeups is about the same but the range in
distribution is higher. Perhaps these two metrics together indicate that having a
unique changeup provides an edge. This is additionally supported by seeing many of
the darkest red points away from the mass of points in the middle.

I also looked at changeup effectiveness measured by batting average against and
strikeouts per 9 innings. These metrics are more difficult to use. They can be
ineffective if a pitcher does not throw very many fastballs or changeups. On these
graphs I have provided the ability to filter for the percentage of fastballs and
changeups thrown.

{% include Tableau_BAA.html %}

{% include Tableau_Strikeout_Rate.html %}

The batting average graph provides a minor indication that there is importance to
having a larger change in velocity. When I set the fastball and changeup percentage
filters to 15 and the combined fastball and changeup percentage filter to 40,
there is almost a 1 MPH increase in the boundaries for the distribution in velocity
change.

I believe that the biggest insight came from the changeup pitch value graph that
throwing changeups that are different from league average provide an advantage.
