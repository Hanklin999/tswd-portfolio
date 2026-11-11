| [Home](https://hanklin999.github.io/tswd-portfolio/) | [Data Visualization Examples](dataviz-examples) | [Critique by Design](critique-by-design) | [Final Project I](final-project-part-one) | [Final Project II](final-project-part-two) | [Final Project III](final-project-part-three) |

# Critique by Design

> **Status: Complete.** The final redesign was revised after peer testing and is included below.

## Family spending across income quintiles

This project redesigns a chart about how UK households in different income groups divide their weekly spending.

## Step one: the visualization

I selected MakeoverMonday's [2025/W39 Family Spending in the UK](https://makeovermonday.vercel.app/dataset/2025w39-family-spending-in-the-uk), which uses data from the UK Office for National Statistics. The original chart compares spending categories across five income quintiles.

I chose it because the topic is relevant to household budgets and inequality, but the stacked bars make comparisons difficult. Each income group's percentages use a different spending total, so stacking them creates a combined bar length with no useful meaning. “All households” also repeats information already represented by the five quintiles.

## Step two: the critique

Using Stephen Few's *Data Visualization Effectiveness Profile*, I found that the chart has a clear topic, a reliable source, and a simple visual style. Its main weaknesses are perceptibility and truthfulness.

Most values do not share a common baseline, so readers cannot compare them quickly. For example, housing accounts for 27.0% of spending in the lowest-income group and 13.1% in the highest-income group, but the stacked layout hides this difference. The chart is intended for a general audience, yet readers must move between the bars and legend to understand the main pattern.

## Step three: Sketch a solution

I replaced the stacked bars with a dot plot so every value uses the same percentage scale. Contrasting colors emphasize the lowest- and highest-income groups, while gray dots show the three middle groups. I removed “All households,” shortened several category names, and used annotations to highlight the main comparisons. This version was designed to make the differences between income groups easier to see.

### Static prototype

This was the version used in the in-class discussion.

![A multi-series dot plot comparing the share of weekly household expenditure across five income quintiles. The Bottom fifth and Top fifth are emphasized, and housing is directly annotated.](images/critique-by-design/Ay4B5-lower-income-households-devote-more-of-their-spending-to-housing-and-food-.png)

## Step four: Test the solution

### In-class peer discussion

During class, I shared the first Datawrapper version with three classmates and asked about its clarity, readability, and overall presentation. Our discussion produced four main comments:

1. **Income labels:** The quintile labels were not immediately clear. My classmates suggested familiar terms such as “the rich” and “the poor” to make the comparison easier to understand.
2. **Too many categories:** The chart included too many spending categories, which made the main message difficult to identify. They recommended keeping only the categories that best support the story.
3. **Gridlines and layout:** The gridlines made the chart feel visually unbalanced and distracted from the data.
4. **Reading flow:** The first highlighted point appeared near the upper-right of the chart, so the reading order did not feel natural.

### Synthesis

The feedback showed that the chart needed a clearer entry point and less visual competition. I decided to simplify the income labels without using informal terms such as “rich” and “poor,” reduce the number of categories, and place the strongest findings at the top. I also used annotations to guide readers through the two main comparisons. The gridline comment was useful, but the final chart still contains horizontal guides; reducing them further remains a possible refinement rather than a completed change.

## Step five: build the solution

The final redesign keeps the dot plot because it gives every value the same percentage scale and makes the five income groups easier to compare. Based on the in-class peer discussion, I completed the following changes:

- Replaced the short quintile labels with clearer descriptions, from “Lowest income (bottom 20%)” to “Highest income (top 20%).”
- Reduced the chart to eight spending categories so the main pattern is easier to see.
- Moved housing and food to the top and added annotations for housing and restaurants to create a clearer reading path.
- Revised the title and supporting note so readers understand that the values are shares of each income group's weekly expenditure, not absolute spending amounts.

The final chart shows that lower-income households spend a larger share on housing and food, while higher-income households spend larger shares on categories such as recreation and restaurants. The redesign does not claim that lower-income households spend more money in absolute terms. A future version could reduce the remaining horizontal gridlines and test the chart with more participants.

### Final interactive redesign

[Open the final Datawrapper chart in a new page](https://datawrapper.dwcdn.net/Ay4B5/5/).

<iframe title="Lower-income households spend a larger share on housing and food" aria-label="Dot Plot" id="datawrapper-chart-Ay4B5" src="https://datawrapper.dwcdn.net/Ay4B5/5/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="307" data-external="1"></iframe><script type="text/javascript">(function(){function e(){window.addEventListener(`message`,function(e){if(e.data[`datawrapper-height`]!==void 0){var t=document.querySelectorAll(`iframe`);for(var n in e.data[`datawrapper-height`])for(var r=0,i;i=t[r];r++)if(i.contentWindow===e.source){var a=e.data[`datawrapper-height`][n]+`px`;i.style.height=a}}})}e()})();</script>

## References

- MakeoverMonday. [2025/W39 Family Spending in the UK](https://makeovermonday.vercel.app/dataset/2025w39-family-spending-in-the-uk).
- Office for National Statistics. [Family spending workbook 1: detailed expenditure and trends](https://www.ons.gov.uk/peoplepopulationandcommunity/personalandhouseholdfinances/expenditure/datasets/familyspendingworkbook1detailedexpenditureandtrends), FYE 2024, Table 3.2E5.
- Few, Stephen. [Data Visualization Effectiveness Profile](https://www.perceptualedge.com/articles/visual_business_intelligence/data_visualization_effectiveness_profile.pdf), 2017.
- Datawrapper. [Final interactive redesign](https://datawrapper.dwcdn.net/Ay4B5/5/).

## AI acknowledgements

I used ChatGPT/Codex to help locate and verify the relevant ONS source workbook, extract the high-level FYE 2024 values into a Datawrapper-ready CSV, discuss alternative chart forms, check the interpretation of the data, and revise portions of the written critique for clarity and grammar. I made the final decisions about the critique, narrative focus, visual design, annotations, and Datawrapper implementation.
