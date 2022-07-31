---
title: Probability Pattern - Bayes Rule
date: 2022-07-30 20:44:59
tags:
  - probability
  - interview
---

# Bayes Rule

Bayes rule is a very common probability question pattern. It usually involves using the Bayes rule, together with the law of total probability, to compute some conditional probability. When you seen in the question statement, "given" a conditional, what is the probability of an event happening, you should think of using Bayes rule.

## Concepts

### Bayes rule

{% mathjax %}
P(A|B) = \frac{P(B|A)P(A)}{P(B)}
{% endmathjax %}

### Law of total probability

{% mathjax %}
P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + ... + P(A|B_n)P(B_n)
{% endmathjax %}

## Questions

### Unfair Coin

[Green Book](https://amzn.to/3zJO39H)

> You are given 1000 coins. Among the, 1 coin has heads on both sides. The other 999 coins are fair coins. You randomly choose a coin and toss it 10 times. Each time, the coin turns up heads. What is the probability that the coin you choose is the unfair one?

Using Bayes rule, we have:

{% mathjax %}
P(unfair|10 head) = \frac{P(10 head|unfair)P(unfair)}{P(10 head)}
{% endmathjax %}

Now, using the law of total probability, we have:

{% mathjax %}
P(10 head) = P(10 head|unfair)P(unfair) + P(10 head|fair)P(fair)
{% endmathjax %}

Combining both, we have our equation as:
{% mathjax %}
P(unfair|10 head) = \frac{1 \times 1/1000}{1 \ times 1/1000 + 0.5^{10} \times 999/1000} \approx 0.5
{% endmathjax %}
