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

I built the working storyboard directly in Shorthand so readers could review the story in its intended format.

[Open the Shorthand story in a new page](https://carnegiemellon.shorthandstories.com/the-habitual-shopper-an-instacart-data-story/index.html)

<script
  src="https://carnegiemellon.shorthandstories.com/the-habitual-shopper-an-instacart-data-story/embed.js"
  data-id="https://carnegiemellon.shorthandstories.com/the-habitual-shopper-an-instacart-data-story">
</script>


## Act 1: Different Products, Familiar Categories?

The story starts by comparing repeat purchases at three levels: products, aisles, and departments.

The median repeat rates are 27.7% for products, 47.4% for aisles, and 71.7% for departments. I used three distribution charts to show how shopping baskets can look different at the product level but more similar at the category level.


<iframe title="How Often Do Shoppers Repeat the Same Products?" aria-label="Small multiple line chart" id="datawrapper-chart-ON3Eq" src="https://datawrapper.dwcdn.net/ON3Eq/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="722" data-external="1"></iframe><script type="text/javascript">(function(){function e(){window.addEventListener(`message`,function(e){if(e.data[`datawrapper-height`]!==void 0){var t=document.querySelectorAll(`iframe`);for(var n in e.data[`datawrapper-height`])for(var r=0,i;i=t[r];r++)if(i.contentWindow===e.source){var a=e.data[`datawrapper-height`][n]+`px`;i.style.height=a}}})}e()})();</script>


## Act 2: Not in the Last Basket Doesn't Mean New

This section introduces the main finding. On average, 30.5% of products were also in the previous order, 30.6% had been purchased earlier but not in the previous order, and 38.9% were new to the shopper's recorded history.

I used a 100% stacked bar chart to show these three groups together. The 30.6% is especially important because it shows that shoppers often return to familiar products.


![Basket composition](https://raw.githubusercontent.com/Hanklin999/the-habitual-shopper/main/outputs/figures/03_basket_composition.png)


## Act 3: When Familiar Products Return

To make the findings more concrete, I followed Shopper 977 across Orders 8, 9, and 10.

The shopper purchased 6, 13, and 7 products in these orders. Several products from Order 8 disappeared in Order 9 but returned in Order 10, including bananas, avocados, and almond milk.

I used shopping basket illustrations to help readers follow these changes.


![Shopper 977 shopping baskets](https://raw.githubusercontent.com/Hanklin999/the-habitual-shopper/main/outputs/figures/購物者977：輪替購物行為示例.png)


## Act 4: What Should Grocery Apps Remember?

The final section connects the findings to grocery app design. I introduce three possible features: Quick Reorder, Returning Favorites, and Category Discovery.

The idea is that grocery apps could use more than the previous order to help shoppers find products they may want to buy again.



---

# User Research

## Target Audience


The main audience is product managers and analysts who work with online shopping or recommendation systems. I also want the story to be understandable to regular online shoppers.

For the in-class critique, I showed the Shorthand draft to classmates and asked them to focus on the story, charts, shopper example, and visual design.


## Research Goals and Interview Script

I asked my group to consider four questions:

1. What do you think the main story is?
2. Which chart is the hardest to understand?
3. Does the Shopper 977 example make the finding clearer?
4. What should I change before the final version?

The interview should begin without explaining the intended conclusion. After the participant reads the draft, I will ask the questions above and request a short summary of the story in their own words.

## Interview Findings

### In-Class Critique Findings
I showed my Shorthand draft to my critique group. They thought the main story worked, especially the Shopper 977 example. Most of their feedback focused on making the visuals easier to read.

### Top Three Observations

1. The first set of charts was difficult to compare. A side-by-side or overlapping layout may work better than the current vertical layout.
2. The Shopper 977 example made the main idea easier to understand, but the basket illustration needs clearer labels.
3. The background colors and chart colors were sometimes distracting. A simpler palette would improve readability.

The group also asked whether the Kaggle data represented real purchases. I confirmed that it is the public Instacart Online Grocery Shopping Dataset released by Instacart in 2017.

### Plans Going Forward

I will redesign the first visualization, improve the Shopper 977 illustration, and use a simpler color palette. I will also add clearer source notes to the charts. I plan to keep the current story structure because the group found the main idea understandable.

---

# Identified Changes for Part III

The following changes are based on the in-class critique.

| Area | Planned Change |
|---|---|
| First visualization | Test a side-by-side or overlapping layout. |
| Shopper 977 example | Keep the example but improve the labels and basket comparison. |
| Color palette | Use fewer colors and give each color one consistent meaning. |
| Data source | Add a clear Instacart source note below each chart. |


## Part III Priorities

1. Redesign the first visualization.
2. Improve the Shopper 977 illustration.
3. Simplify the colors and backgrounds.
4. Add clearer source notes.
5. Revise the Shorthand story based on the critique.

---

## References

1. Instacart. (2017). *Instacart Market Basket Analysis*. Kaggle. https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis
2. Berinato, S. (2016). *Good Charts: The HBR Guide to Making Smarter, More Persuasive Data Visualizations*. Harvard Business Review Press.
3. Analysis code and generated outputs: https://github.com/Hanklin999/the-habitual-shopper

## AI Acknowledgements

I used ChatGPT to help edit the wording and debug parts of the Python analysis. I checked the reported values against my analysis outputs. The critique findings above are based on feedback from my in-class group.
