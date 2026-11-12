| [Home](https://hanklin999.github.io/tswd-portfolio/) | [Data Visualization Examples](dataviz-examples) | [Critique by Design](critique-by-design) | [Final Project I](final-project-part-one) | [Final Project II](final-project-part-two) | [Final Project III](final-project-part-three) |

# Final Project I: Initial Proposal

# The Habitual Shopper
### When a Different Basket Is Still Full of Familiar Products

**Target audience:** E-commerce product managers and product analysts

**Main idea:** A shopper can buy a very different basket without buying products that are new to them. To understand shopping habits, we need to look beyond two consecutive orders and consider the shopper's longer purchase history.

---

# Outline

## Project Overview

Grocery shopping seems like it should be repetitive. People regularly need the same basics, so I expected consecutive orders to contain many of the same products. When I started exploring the Instacart Market Basket Analysis dataset, however, the overlap was lower than I expected.

This led me to a more interesting question: when a basket changes, is the shopper actually trying new products, or are they rotating among products they have bought before? My project will compare basket similarity, product categories, and new-to-history purchases. The goal is to show why basket change and product discovery are related but not interchangeable ideas.

## Story Structure

### Act 1 — Consecutive Baskets Are Less Similar Than Expected

I will begin by asking how much two consecutive grocery orders overlap. For 484 shoppers with complete order histories from orders 5–10, the average product-level Jaccard similarity is only **19.4%**. A histogram will show the distribution and introduce the puzzle: if grocery shopping is habitual, why do the baskets look so different?

### Act 2 — Different Products, Familiar Categories

Next, I will compare the same orders at three levels:

- **Product similarity:** 19.4%
- **Aisle similarity:** 29.6%
- **Department similarity:** 46.1%

The baskets look more similar when products are grouped into broader categories. This does not prove that preferences are stable—larger categories naturally create more opportunities for overlap—but it shows that product-level similarity is only one part of the story.

### Act 3 — Basket Change Is Not the Same as Product Discovery

This is the main point of the project. Basket similarity compares **two consecutive orders**. Product novelty asks whether an item has appeared anywhere in the shopper's **previously recorded history**. A shopper can therefore have very different consecutive baskets while still purchasing familiar products.

Using median thresholds for similarity and novelty during orders 5–10, I divide the exploratory sample into four descriptive groups:

| Shopping Pattern | Basket Similarity | Product Novelty | Interpretation |
|---|---|---|---|
| Routine | High | Low | Similar baskets with familiar products |
| Rotational | Low | Low | Different baskets with familiar products |
| New-to-user | Low | High | Different baskets with more new-to-history products |
| Mixed | High | High | Similar baskets that also contain new-to-history products |

The group I am most interested in is **Rotational Shoppers**. In my sample, **50 of 484 shoppers (10.3%)** have both low basket similarity and low product novelty. These labels are based on sample medians and are a way to organize the story, not validated customer segments.

#### Example: Shopper 42

Shopper 42 makes the distinction easier to see. Order 9 contains six products and Order 10 contains seven. Only **Organic Blueberries** appears in both orders, giving them a Jaccard similarity of **8.3%**. However, all seven products in Order 10 had appeared earlier in the shopper's history.

The immediate basket changed almost completely, but the shopper did not buy anything new to their recorded history.

### Act 4 — Do These Patterns Continue?

Finally, I will compare the classifications from orders 5–10 with behavior during orders 11–15. Among 323 shoppers with enough history for both periods:

- **80.3%** of initially Routine shoppers (n = 127) remain Routine.
- **53.7%** of initially Rotational shoppers (n = 41) remain Rotational.

This suggests that some patterns continue across later orders, although Rotational behavior is less stable. My final takeaway will be that product teams should not treat a changing basket as automatic evidence of product discovery. Purchase history provides important context, but an experiment would still be needed to test whether a recommendation strategy causes better outcomes.

---

## Initial Sketches

These sketches show the planned flow of the story. The charts are based on my exploratory analysis and will be redesigned for the final project.

### Sketch 1 — Consecutive Baskets Often Change

![Distribution of Product-Level Basket Similarity](images/habitual-shopper/sketch_01_similarity.png)

This histogram introduces the project by showing the distribution of average product-level similarity across 484 shoppers. The annotation calls attention to the **19.4% average**.

### Sketch 2 — Different Products, Familiar Categories

![Product, Aisle, and Department Similarity](images/habitual-shopper/sketch_02_categories.png)

This chart compares product, aisle, and department similarity. In the final version, I will explain that broader categories mechanically create more overlap so readers do not interpret the increase as proof of loyalty.

### Sketch 3 — Basket Similarity vs. Product Novelty

![Basket Similarity vs. Product Novelty](images/habitual-shopper/sketch_03_discovery.png)

This will be the main chart in the story. Each point represents a shopper, and the 50 Rotational Shoppers are highlighted because they have both low consecutive-basket similarity and low product novelty.

#### Supporting Example — Shopper 42

![Real Shopping Basket Example: Shopper 42](images/habitual-shopper/sketch_03_basket_example.png)

The side-by-side orders turn the scatter plot into a concrete example: only one item overlaps, but every product in the second order has been purchased before.

### Sketch 4 — Pattern Persistence

![Shopping Pattern Persistence](images/habitual-shopper/sketch_04_persistence.png)

Two 100% stacked bars will compare how often Routine and Rotational shoppers retain their labels in orders 11–15. This provides a conclusion while also showing that the patterns are not permanent.

---

# The Data

## Primary Data Source

I am using the public **Instacart Market Basket Analysis** dataset from a 2017 Kaggle competition. It contains anonymized order histories, the products in each order, order sequence, and product metadata such as aisle and department. I have downloaded the data and completed an initial analysis in Python.

The project uses five files: `orders.csv`, `order_products__prior.csv`, `products.csv`, `aisles.csv`, and `departments.csv`. I join them using order, product, aisle, and department IDs. My initial analysis uses the first 1,000 eligible shoppers by user ID rather than a random sample. Of these, 484 have complete histories for orders 5–10, and 323 also have enough orders for the later comparison. This sample is useful for developing the story, but it should not be treated as representative of all Instacart shoppers.

## Data Sources

| Name | Link | Use in This Project |
|---|---|---|
| Instacart Market Basket Analysis | [Kaggle Dataset](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis) | Anonymized grocery orders and product metadata |
| Orders | [Dataset Download](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis) | User IDs, order sequence, and time between orders |
| Order Products (Prior) | [Dataset Download](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis) | Products in prior orders and reordered indicators |
| Products, Aisles, and Departments | [Dataset Download](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis) | Product names and category classifications |

**Code and exploratory analysis:** [The Habitual Shopper — GitHub Repository](https://github.com/Hanklin999/the-habitual-shopper)

## Analytical Approach

### Basket Similarity

I measure the overlap between consecutive baskets with the Jaccard Index:

**Jaccard Similarity = Products in Both Baskets / Unique Products Across Both Baskets**

I repeat the calculation using product, aisle, and department sets.

### Product Novelty

I measure novelty as the share of products marked `reordered = 0`. This means the item is new to the shopper's recorded history. It does **not** tell us whether the shopper intentionally discovered it or saw it in a recommendation.

### Shopping Patterns

I use each shopper's average basket similarity and product novelty during orders 5–10 to create the four exploratory groups. I then apply the same idea to orders 11–15 to see whether the patterns continue.

## Limitations

The dataset records purchases but not browsing, searches, recommendation impressions, or customer motivation. As a result, I cannot measure discovery directly or determine what caused a purchase. The sample is also not random, novelty tends to decline as more purchase history becomes available, and broader product categories naturally produce more overlap. The results should therefore be read as descriptive rather than causal.

---

# Method and Medium

I plan to build an interactive, scroll-driven story on **GitHub Pages**. I am using Python, Pandas, and NumPy for data preparation and analysis, and I created the current sketches in Matplotlib. For the final version, I plan to use **Tableau or Plotly** for the charts and place them within the four-part narrative above. The project will focus on a small number of annotated visuals rather than a dashboard.

---

## References

1. Instacart. (2017). *Instacart Market Basket Analysis*. Kaggle. https://www.kaggle.com/competitions/instacart-market-basket-analysis/data
2. Berinato, S. (2016). *Good Charts: The HBR Guide to Making Smarter, More Persuasive Data Visualizations*. Harvard Business Review Press.
3. Original exploratory analysis and visualization sketches developed for the CMU Telling Stories with Data course using the Instacart dataset.

---

## AI Acknowledgements

I used ChatGPT to help brainstorm the story structure, debug parts of the Python analysis, and revise the organization and wording of this proposal. I checked the results against the Instacart data and made the final decisions about the topic, analysis, visualizations, and interpretation. All numerical results and shopping examples shown here come from the dataset rather than generated data.
