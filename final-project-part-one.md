| [Home](https://hanklin999.github.io/tswd-portfolio/) | [Data Visualization Examples](dataviz-examples) | [Critique by Design](critique-by-design) | [Final Project I](final-project-part-one) | [Final Project II](final-project-part-two) | [Final Project III](final-project-part-three) |

# Final Project I: Initial Proposal

## The Habitual Shopper

> **Online grocery shopping may offer endless choices, but are you really discovering anything new?**

A changing basket does not always mean discovery. Shoppers may simply be combining familiar products in different ways.

**Primary audience:** Product managers and analysts working on grocery recommendations, repeat purchases, and product discovery.

**Reader takeaway:** Understand what is routine and what is real exploration, so routine purchases can be simplified and discovery can become more intentional.

---

## Outline

### Project Overview

Grocery shopping seems repetitive, so I expected consecutive orders to contain many of the same products. However, the Instacart data showed less overlap than I expected. This led me to ask whether shoppers were discovering new products or simply rotating among familiar ones. My story compares consecutive baskets with longer purchase histories to separate these two behaviors.

### Story Structure

#### Act 1 — Consecutive Baskets Share Relatively Few Products

Among 484 shoppers with complete histories for orders 5–10, consecutive baskets have an average product overlap of only **19.4%**. This creates the opening puzzle: if grocery shopping is habitual, why do the baskets look so different?

#### Act 2 — Baskets Look More Familiar at Broader Category Levels

The same orders look more similar when products are grouped into broader categories:

- **Products:** 19.4% overlap
- **Aisles:** 29.6% overlap
- **Departments:** 46.1% overlap

This does not prove that preferences are stable. Broader categories naturally create more opportunities for overlap. It does show that product-level change is only one part of the story.

#### Act 3 — A Different Basket Can Contain Nothing New

Basket overlap compares **two consecutive orders**. New-to-history purchasing asks whether an item has appeared anywhere in the shopper's **previously recorded history**. These measures can describe very different behavior.

Shopper 42 provides a clear example. Order 9 contains six products and Order 10 contains seven. Only **Organic Blueberries** appears in both orders, producing an overlap of **8.3%**. Yet all seven products in Order 10 had appeared earlier in the shopper's history. The basket changed almost completely, but it contained nothing new to the recorded history.

I then use median thresholds for overlap and new-to-history purchasing to organize the sample into four descriptive patterns:

- **Routine:** Similar baskets with mostly familiar products
- **Rotational:** Different baskets with mostly familiar products
- **New-to-user:** Different baskets with more new-to-history products
- **Mixed:** Similar baskets that also include new-to-history products

The most interesting group is **Rotational Shoppers**. In the exploratory sample, **50 of 484 shoppers (10.3%)** have both low basket overlap and low new-to-history purchasing. These labels help explain the data; they are not permanent or validated customer types.

#### Act 4 — Some Shopping Patterns Continue

I compare behavior in orders 5–10 with a later period covering orders 11–15. Among 323 shoppers with enough history for both periods:

- **80.3%** of initially Routine shoppers (n = 127) remain Routine.
- **53.7%** of initially Rotational shoppers (n = 41) remain Rotational.

Some patterns continue, but they are not equally stable. The product implication is simple: teams should measure routine replenishment and product discovery separately instead of treating every basket change as evidence of exploration.

---

## Initial Sketches

These sketches show the planned flow of the final story. They are based on my exploratory analysis and will be redesigned for the final project.

### Consecutive Baskets Share Relatively Few Products

![Distribution of Product-Level Basket Similarity](images/habitual-shopper/sketch_01_similarity.png)

This histogram introduces the puzzle by showing the distribution of basket overlap across 484 shoppers.

### Baskets Look More Familiar at Broader Category Levels

![Product, Aisle, and Department Similarity](images/habitual-shopper/sketch_02_categories.png)

This comparison shows how overlap increases from products to aisles and departments, while noting that broader categories naturally create more overlap.

### A Changing Basket Does Not Always Mean New Products

![Basket Similarity vs. Product Novelty](images/habitual-shopper/sketch_03_discovery.png)

This is the main chart in the story. It highlights the 50 Rotational Shoppers whose baskets change even though their purchases are mostly familiar.

#### One Different Basket, No New-to-History Products

![Real Shopping Basket Example: Shopper 42](images/habitual-shopper/sketch_03_basket_example.png)

The side-by-side orders make the main idea concrete: only one item overlaps, but every item in the second order has been purchased before.

### Some Shopping Patterns Continue Across Later Orders

![Shopping Pattern Persistence](images/habitual-shopper/sketch_04_persistence.png)

Two 100% stacked bars compare how often Routine and Rotational shoppers retain their labels in the later period.

---

## The Data

### Data at a Glance

- **Source:** [Instacart Market Basket Analysis](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis), released for a 2017 Kaggle competition
- **Content:** Anonymized order histories, products, order sequence, aisles, and departments
- **Files used:** `orders.csv`, `order_products__prior.csv`, `products.csv`, `aisles.csv`, and `departments.csv`
- **Initial sample:** First 1,000 eligible shoppers by user ID
- **Main analysis:** 484 shoppers with complete histories for orders 5–10
- **Later comparison:** 323 shoppers with enough history for orders 11–15
- **Code:** [The Habitual Shopper — GitHub Repository](https://github.com/Hanklin999/the-habitual-shopper)

I have downloaded the data and completed the initial analysis in Python. The sample is useful for building the story, but it is not a random sample and should not be treated as representative of all Instacart shoppers.

### Analytical Approach

**Basket overlap** is measured with the Jaccard Index:

**Products in Both Baskets / Unique Products Across Both Baskets**

I calculate it separately for product, aisle, and department sets. **New-to-history purchasing** is the share of products marked `reordered = 0`, meaning that the item has not appeared earlier in the shopper's recorded history. I use each shopper's averages during orders 5–10 to create the four descriptive patterns and compare them with orders 11–15.

### What This Analysis Cannot Tell Us

- “New” means new to the recorded Instacart history, not necessarily new to the shopper's life.
- Purchase records do not show browsing, searches, recommendation exposure, or customer motivation.
- The first 1,000 eligible users are not a random sample of all Instacart shoppers.
- Novelty tends to decline as more purchase history becomes available.
- The four patterns are descriptive labels, not permanent customer types.

The findings are descriptive rather than causal. An experiment would be needed to determine whether a recommendation strategy changes customer behavior.

---

## Method and Medium

I plan to create an interactive, scroll-driven story on **GitHub Pages**, rather than a standalone dashboard.

- **Python, Pandas, and NumPy:** Data preparation and analysis
- **Matplotlib:** Current exploratory sketches
- **Tableau or Plotly:** Final annotated and interactive charts
- **Planned interactions:** Compare category levels, explore shopping patterns, and inspect the Shopper 42 example

Each section will present one question, one main visual, and one takeaway before moving to the next part of the story.

---

## What Should Readers Do?

> **Automate the routine. Make discovery intentional.**

Shoppers can save or automate products they purchase regularly. When they want to explore, they can look beyond their usual products, recommendations, or shopping platform. This may help them spend less time on repeat shopping and manage their choices and budget more intentionally.

For product teams, the same idea suggests treating replenishment and discovery as different customer needs—and evaluating them with different measures.

---

## References

1. Instacart. (2017). *Instacart Market Basket Analysis*. Kaggle. https://www.kaggle.com/competitions/instacart-market-basket-analysis/data
2. Berinato, S. (2016). *Good Charts: The HBR Guide to Making Smarter, More Persuasive Data Visualizations*. Harvard Business Review Press.
3. Original exploratory analysis and visualization sketches developed for the CMU Telling Stories with Data course using the Instacart dataset.

---

## AI Acknowledgements

I used ChatGPT to help brainstorm the story structure, debug parts of the Python analysis, and revise the organization and wording of this proposal. I checked the results against the Instacart data and made the final decisions about the topic, analysis, visualizations, and interpretation. All numerical results and shopping examples shown here come from the dataset rather than generated data.
