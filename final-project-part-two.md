| [Home](https://hanklin999.github.io/tswd-portfolio/) | [Data Visualization Examples](dataviz-examples) | [Critique by Design](critique-by-design) | [Final Project I](final-project-part-one) | [Final Project II](final-project-part-two) | [Final Project III](final-project-part-three) |

# Final Project II: Development and Iteration

## The Habitual Shopper

> **Online grocery shopping may offer endless choices, but are you really discovering anything new?**

**Project links:** [Part I: Initial Proposal](final-project-part-one) | [Analysis repository](https://github.com/Hanklin999/the-habitual-shopper) | [Shorthand Story: The Habitual Shopper](https://carnegiemellon.shorthandstories.com/the-habitual-shopper-an-instacart-data-story/index.html)

---

## How the Story Developed

In Part I, I wanted to explore whether online grocery shoppers tend to repeat their purchases or try new products. As I worked with the Instacart dataset, I realized that simply comparing two consecutive orders does not tell the whole story.

> **A product missing from the previous order is not necessarily new.**
The shopper might have purchased it several orders earlier. This became the main idea behind my story: a changing shopping basket does not always mean a shopper is discovering new products.

For Part II, I created a draft story using Shorthand. I organized the analysis into a few sections, starting with shopping patterns across product categories, followed by the difference between repeat purchases and new products. I also included a real example from Shopper 977 to make the findings easier to understand.

The analysis focuses on 484 shoppers with complete records for Orders 5–10. I used Python and Datawrapper to create the visualizations and Shorthand to present them as a visual story.

---

# Wireframes and Storyboards

I used Shorthand to build a working draft of my story. The goal was to guide readers from general shopping patterns to a real shopper's experience, and then explore what the findings might mean for grocery apps.

[View the Shorthand Story](https://carnegiemellon.shorthandstories.com/the-habitual-shopper-an-instacart-data-story/index.html)


## Act 1: Different Products, Familiar Categories?

The story starts by comparing repeat purchases at three levels: products, aisles, and departments.

The median repeat rates are 27.7% for products, 47.4% for aisles, and 71.7% for departments. I used three distribution charts to show how shopping baskets can look different at the product level but more similar at the category level.

Visual: Three charts comparing repeat rates across 484 shoppers.
<iframe title="How Often Do Shoppers Repeat the Same Products?" aria-label="Small multiple line chart" id="datawrapper-chart-ON3Eq" src="https://datawrapper.dwcdn.net/ON3Eq/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="722" data-external="1"></iframe><script type="text/javascript">(function(){function e(){window.addEventListener(`message`,function(e){if(e.data[`datawrapper-height`]!==void 0){var t=document.querySelectorAll(`iframe`);for(var n in e.data[`datawrapper-height`])for(var r=0,i;i=t[r];r++)if(i.contentWindow===e.source){var a=e.data[`datawrapper-height`][n]+`px`;i.style.height=a}}})}e()})();</script>


## Act 2: Not in the Last Basket Doesn't Mean New

This section introduces the main finding. On average, 30.5% of products were also in the previous order, 30.6% had been purchased earlier but not in the previous order, and 38.9% were new to the shopper's recorded history.

I used a 100% stacked bar chart to show these three groups together. The 30.6% is especially important because it shows that shoppers often return to familiar products.

Visual: A 100% stacked bar chart showing basket composition.
![Basket composition](https://raw.githubusercontent.com/Hanklin999/the-habitual-shopper/main/outputs/figures/03_basket_composition.png)


## Act 3: When Familiar Products Return

To make the findings more concrete, I followed Shopper 977 across Orders 8, 9, and 10.

The shopper purchased 6, 13, and 7 products in these orders. Several products from Order 8 disappeared in Order 9 but returned in Order 10, including bananas, avocados, and almond milk.

I used shopping basket illustrations to help readers follow these changes.

Visual: Three shopping baskets showing the products purchased in each order.
![Shopper 977 shopping baskets](https://raw.githubusercontent.com/Hanklin999/the-habitual-shopper/main/outputs/figures/購物者977：輪替購物行為示例.png)


## Act 4: What Should Grocery Apps Remember?

The final section connects the findings to grocery app design. I introduce three possible features: Quick Reorder, Returning Favorites, and Category Discovery.

The idea is that grocery apps could use more than the previous order to help shoppers find products they may want to buy again.

Visual: Three feature ideas based on the shopping patterns.

---

# User Research

## Target Audience and Recruitment

The primary audience is product managers and analysts who work with online shopping, recommendations, or repeat purchasing. The story should also remain understandable to regular online grocery shoppers.

For feedback, I plan to speak with three types of readers:

1. A frequent online shopper.
2. Someone with a business or analytics background.
3. Someone without a technical background.


## Research Goals and Interview Script

| Goal | Questions to Ask |
|---|---|
| First impression | What do you think this story is about? |
| Understand the main finding | What do you think the 30.6% returning-products group means? |
| Shopper example | Does Shopper 977's example (Orders 8–10) help you understand the story? |
| Product implications | Which of the three grocery app features would you find most useful? |

The interview should begin without explaining the intended conclusion. After the participant reads the draft, I will ask the questions above and request a short summary of the story in their own words.

## Interview Findings

**Status:** User interviews have not yet been documented. This section should be completed with actual feedback before submission; findings should not be invented.

| Question or task | Interview 1 | Interview 2 | Interview 3 |
|---|---|---|---|
| Expected story after the opening | To be completed | To be completed | To be completed |
| Understanding of the key findings | To be completed | To be completed | To be completed |
| Reaction to Shopper 977 | To be completed | To be completed | To be completed |
| Most confusing chart or term | To be completed | To be completed | To be completed |
| Main takeaway or action | To be completed | To be completed | To be completed |

---

# Identified Changes for Part III

The following revisions come from the current analysis and self-review. Interview-based changes should be added after the research sessions.


| Area | Planned Changes |
|---|---|
| Data visualizations | Improve chart labels and make the key percentages easier to compare. |
| Shopper example | Make the changes between Orders 8, 9, and 10 easier to follow. |
| Storytelling | Shorten some sections and improve the transitions between charts. |
| Product implications | Add simple visuals to explain the three grocery app features. |
| Overall design | Improve spacing, font consistency, and mobile readability. |


## Part III Priorities

1. Complete three user interviews and summarize the feedback.
2. Improve the charts and Shopper 977 illustrations.
3. Make the story easier to read on both desktop and mobile.
4. Revise the Shorthand story based on reader feedback.
5. Finalize the layout, references, and visual design.

---

## References

1. Instacart. (2017). *Instacart Market Basket Analysis*. Kaggle. https://www.kaggle.com/competitions/instacart-market-basket-analysis/data
2. Berinato, S. (2016). *Good Charts: The HBR Guide to Making Smarter, More Persuasive Data Visualizations*. Harvard Business Review Press.
3. Analysis code and generated outputs: https://github.com/Hanklin999/the-habitual-shopper

## AI Acknowledgements

I used ChatGPT to help reorganize the Part II draft, revise wording, and debug the Python analysis. I verified the reported values against the generated analysis outputs. User-research findings will be based only on actual interviews and will not be generated by AI.
