# Algorithms

## Goal

- Make the ratio of the time spent on projects and entertainment fluctuated
  around your set PER.
- Make the interest value reflects your preference accurately.
- Keep the user as motivated as possible.

## Reward

After harvesting a tomato, you are required to self-evaluate yourself between 0%
to 100% according to your performance in this pomodoro period. If you are not
sure how to conduct the evaluation, here are some beneficial questions that
might enlight you.

- Is the outcome up to your expectation when you start this pomodoro?
- Are you fully immersed into this task?
- What about your performance compared to the last time you did similar tasks?

The coins you get from this pomodoro are calculated as

```js
coins = (10 * period_h * (1 + (self_eval - 0.7) * 0.5 + epsilon * 0.1)) / PER;
```

where `period_h` represents how long this pomodoro is in unit of hours,
`self_eval` represents your self-evaluation score, `epsilon` is a random variable
of a truncated normal distribution between -2 and 2.

## Price

One coin corresponds to one hour of entertainment on average. But we have
multiple algorithms to adjust the price with the following thoughts.

- The price is based on how much time this event costs. (Standard unit price)
- If an entertainment is more appealing to you, it has a higher price. (Interest)
- If an entertainment is recommended, it has a higher price. (Recommendation)

You can switch to a different strategy but sometimes additional information are
required in another strategy. So you have to fill in some information collection
forms.

### Fixed

The edition of the price is all in your hand. We will not change it or give any
recommendations.

### Zen Master

This strategy is suitable for those freelances who have no holiday or, in other
words, have holidays everyday -- what day it is today is not in their mind.

If the recent frequency of your entertainment is higher than before, it would be
assigned a higher score. This strategy encourages you to have a stable
entertainment schedule.

```js
price = clamp(avg_interval / last_time_till_now, 0.6, 1.5)
```

### Gradient Descent

The initial price is set by the user. This strategy would reevaluate the price
of entertainments based on your interest and their value.

Suppose we have \\(m\\) types of entertainments with prices \\(p_1, p_2, \cdots,
p_m\\) , durations \\(h_1, h_2, \cdots, h_m\\), and normal frequencies \\(f_1,
f_2, \cdots, f_m\\). The normal frequency represents how often you buy this
entertainment in common cases. For instance, it can be \\(1/1, 1/7, 1/30,
1/365\\), representing daily, weekly, monthly and yearly respectively. The real
frequency is different from normal frequency, it is \\(s_i f_i\\) where
\\(s_i\\) is a ratio like \\(0, 1.2, 1.5\\). It is recommended that the ratio is
less than \\(2\\) so that our algorithm could work the best.

We connect \\(s_i\\) and \\(p_i\\) by the following formula:

\\[s_ i = A(h_i/p_i + \mu_i - \sigma_i)\\]

where the activation function \\(A(x) = \text{max}\\{ 0, \text{log}(1+x) \\}\\)
and \\(\mu_i\\) represents the interest value \\(\sigma_i\\) represents the
recommendation value. Using this relation and historical data, we can calculated
the \\(\mu_i\\). This interest value can be used to predict the change on
\\(s_ i\\) in the next period when the price varies.

\\[s'_ i = A(h_i/p'_ i + \mu_i - \sigma_i)\\]

where \\(s'_ i\\) are predicted ratios in the next period based on historical
data and \\(p'_ i\\) are the price in the next period.


We are going to optimize the following cost using gradient descent with a small
learning rate:

\\[ \left(\sum_i s'_ i f_i p'_ i - \text{Income}\right)^2 + \left(\sum_i s'_ i
f_i h_i-\text{WorkingHour / PER}\right)^2 \\]


## Task Scheduling
