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
P(\text{unfair}|\text{10 heads}) = \frac{P(\text{10 heads}|\text{unfair})P(\text{unfair})}{P(\text{10 heads})}
{% endmathjax %}

Now, using the law of total probability, we have:

{% mathjax %}
P(\text{10 heads}) = P(\text{10 heads}|\text{unfair})P(\text{unfair}) + P(\text{10 heads}|\text{fair})P(\text{fair})
{% endmathjax %}

Combining both, we have our equation as:

{% mathjax %}
P(\text{unfair}|\text{10 heads}) = \frac{1 \times 1/1000}{1 \times 1/1000 + 0.5^{10} \times 999/1000} \approx 0.5
{% endmathjax %}

### Disease Odds

[DS Book](https://amzn.to/3ONSi8q)

> One in a thousand people have a particular disease, and the test for the disease is 98% correct in testing for the disease. On the other hand, the test has 1% error rate if the person being tested does not have the disease. If someone tests positive, what are the odds they have the disease?

{% mathjax %}
P(\text{Disease}|\text{Positive}) = \frac{P(\text{Positive}|\text{Disease})P(\text{Disease})}{P(\text{Positive})}
{% endmathjax %}

{% mathjax %}
P(\text{Positive}) = P(\text{Positive}|\text{Disease})P(\text{Disease}) + P(\text{Positive}|\text{Healthy})P(\text{Healthy})
{% endmathjax %}

{% mathjax %}
P(\text{Disease}|\text{Positive}) = \frac{0.98 \times 1/1000}{0.98\times1/1000 + 0.01 \times 999/1000} \approx 8.93\%
{% endmathjax %}

### Rainy Day

[DS Book](https://amzn.to/3ONSi8q)

> Three friends in Seattle each told you it is rainy, and each person has 1/3 probability of lying. What is the probability that Seattle is rainy, assuming that the likelihood of rain on any given day is 0.25?

{% mathjax %}
P(\text{Rainy}|\text{Three Yes}) = \frac{P(\text{Three Yes}|\text{Rainy})P(\text{Rainy})}{P(\text{Three Yes})}
{% endmathjax %}

{% mathjax %}
P(\text{Three Yes}) = P(\text{Three Yes}|\text{Rainy})P(\text{Rainy}) + P(\text{Three Yes}|\text{Not Rainy})P(\text{Not Rainy})
{% endmathjax %}

{% mathjax %}
P(\text{Rainy}|\text{Three Yes}) = \frac{(2/3)^3 \times 0.25}{(2/3)^3 \times 0.25 + (1/3)^3 \times 0.75} = \frac{8}{11}
{% endmathjax %}

### Diligent Rater

[DS Book](https://amzn.to/3ONSi8q)

> Facebook has a content team that labels pieces of content on the platform as either spam or not spam. 90\% of them are diligent raters and will mark 20\% of the content as spam and 80\% as non-spam. The remaining 10\% are not diligent raters and will mark 0\% of the content as spam and 100\% as non-spam. Assume the pieces of content are labeled independently of one another, for every rater. Given that a rater has labeled four pieces of content as good, what is the probability that this rater is a diligent rater?

{% mathjax %}
P(\text{Diligent}|\text{Four Good}) = \frac{P(\text{Four Good}|\text{Diligent})P(\text{Diligent})}{P(\text{Four Good})}
{% endmathjax %}

{% mathjax %}
P(\text{Four Good}) = P(\text{Four Good}|\text{Diligent})P(\text{Diligent}) + P(\text{Four Good}|\text{Not Diligent})P(\text{Not Diligent})
{% endmathjax %}

{% mathjax %}
P(\text{Diligent}|\text{Four Good}) = \frac{0.8^4 \times 0.9}{0.8^4 \times 0.9 + 1^4 \times 0.1} = 79\%
{% endmathjax %}

### Letter in Drawer

[DS Book](https://amzn.to/3ONSi8q)

> A desk has either drawers. There is a probability of 1/2 that someone placed a letter in one of the desk's either drawers and a probability of 1/2 that this person did not place a letter in any of the desk's either drawers. You open the first 7 drawers and find that they are all empty. What is the probability that the 8th drawer has a letter in it?

{% mathjax %}
P(\text{has letter}|\text{first 7 empty}) = \frac{P(\text{first 7 empty}|\text{has letter})P(\text{has letter})}{P(\text{first 7 empty})}
{% endmathjax %}

{% mathjax %}
P(\text{first 7 empty}) = P(\text{first 7 empty}|\text{has letter})P(\text{has letter}) + P(\text{first 7 empty}|\text{no letter})P(\text{no letter})
{% endmathjax %}

{% mathjax %}
P(\text{has letter}|\text{first 7 empty}) = \frac{1/8 \times 0.5}{1/8 \times 0.5 + 1 \times 0.5} = \frac{1}{9}
{% endmathjax %}
