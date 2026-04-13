# wayfair-shipping-days-impact-on-sales

## **Project Summary**

Our client, Wayfair, is an American e-commerce company which sells furniture and home goods. For their 2027 big project, they are planning to build a logistical hub center to enhance shipping speed all over the US states.

However, before they start planning this $335M project, they want us to answer this question: How does the reduced average days to ship affect generated sales?

They will need the estimate of numbers in the sales difference in order to officially launch this project or not.

## **DAG Analysis**

From the DAG analysis, the criteria are Y (Outcome - Sales by products), X(Treatment - Average days to ship), A (Confounders - category, weight, fulfillment type, price, popularity ), and IV(weather exposure).

The DAG shows A → X, A → Y, X → Y, which illustrates that A affect both X and Y, creating a backdoor path between X and Y and leading to potential omitted variable bias. IV provides exogenous variation in X that is independent of A, allowing us to identify the causal effect of X on Y. With IV, the DAG shows IV → X → Y (Not IV → Y directly), and IV ⟂ A.

## **Methods Used**

We estimate this effect using three steps: a baseline OLS model, a multivariate OLS controlling for product characteristics, and an IV (2SLS) model using weather exposure as an external source of variation in shipping delays. This progression allows us to address omitted variable bias and endogeneity.

## **Results of Analysis**

Across all models, shipping time has a negative and significant effect on sales. The impact becomes smaller after adding controls and using IV, showing that simple OLS overstated the effect. The IV estimate indicates that each additional day of delay reduces annual sales by about -13% per product.

## **Method**

- Short Regression: -13.5%/day

- Long Regression: -14.4%/day

- 2SLS (IV): -13.3%/day

## **Business Implications to Clients**

Delivery speed is a key revenue driver. Even small delays can meaningfully reduce sales, so improving logistics and fulfillment efficiency can generate measurable returns. Products more prone to delays may offer the greatest gains from targeted shipping improvements.

Therefore, assuming this investment reduces average delivery time by one day for all customers, Wayfair could generate approximately $36.3 million in additional annual revenue, and a total of 309.3 million annual revenue across 10,000 customers.

With the project cost estimated at $335 million, the investment would generate approximately $36 million in additional annual revenue, implying an annual ROI of about 10.8% and a payback period of roughly 9 years.
