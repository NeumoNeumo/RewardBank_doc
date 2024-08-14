# Concepts

There are many concepts in RewardBank and this page would walk you through them
quickly.

## Project Entertainment Ratio(PER)

This ratio is set by yourself. It is a measure of the work/day balance. You can
get coins from finishing your project and use your coins to buy some
entertainment. We add some randomness to the process to achieve the intermittent
random reward.

## Task Management

### Project

A project is a long-term event, possibly last for months. We recommend to set a
deadline for every project to resist procrastination. A ideal period for a
project is [12-week
time](https://www.hubermanlab.com/newsletter/toolkit-for-setting-achieving-goals),
roughly a quarter. 

### Milestone
Milestones are used as subgoals in your project to track your rate of process.
Milestones should preferably be quantitative, at least qualitative, to guarentee
a definite measurability. Milestones not only provide you the track of your
project, but also give you an impulse to continue and the observable hope to
finish a seemingly unattainable project.

### Action

Actions are what you actually do every day. They are the most fine-grained
schedule for your project. You add actions to your daily schedule and finish
them. A action is not necessarily associated with a milestone or a project. For
example, take the trash can be a action but it is not categorized in any
projects in common cases.

Every action has a value, *interest*, indicating how interesting you find this
action is. This value is used in our [task
scheduling](../reference/algorithms.md#task-scheduling).


## Time management

### Time Record

Your time records track every moment of your day, including your sleep. It is not
necessarily to be tied with a specific project. For example, you never expect
your sleep as a project.😂

### Pomodoro

[The Pomodoro technique](https://en.wikipedia.org/wiki/Pomodoro_Technique)
enjoys a good reputation for its effectiveness of narrowing your focus on a
concrete task in a given time period. During this period, you should be 100%
focused on the task on your hand. Nothing can interrupt you or you cannot
harvest a tomato at the end of this pomodoro. We have a [quick
add](../features/quickadd.md) for you to add a task or something else that
just comes across your mind. Write it down and go back to your original task.
Everytime you finish focusing for a time interval, you ought to evaluate your
performance during this period to assist you to have a better control of
yourself. 

A pomodoro must be associated with a corresponding task (and a corresponding time
log because the logger is always tracking your time).


##  Reward Bank

### Coin

Coins are "fiat currency" in the reward bank system. Based on coins, we
implement the random intermittent reward system to enhance your urge to pursuit
your goal and maintain a balance between projects and entertainment.

#### Income

There are multiple ways you can earn coins.
- [Clock in](../features/clockin.md).
- Finish a [task](./concepts.md#task).
- Obtain a [bonus](./concepts.md#bonus).
- [Reach an achievements](./concepts.md#achievement)

#### Expenditure

You can exchange coins for the opportunities to get entertainment.

### Entertainment

Everything that is not in the list of projects and makes you happy is an
entertainment. It can be playing the piano, read novels. Every entertainment is
like a commodity in a shopping mall. The price is determined by yourself but we
have a [recommendation system](../reference/algorithms.md#price-recommendation)
to assist you to set and adjust the value.

### Bonus

We have a list of bonus for you to reduce your work friction -- for example, to
get into the state focusing on your work with less pain after a vacation or a
period when you have a low mood.

> "The only thing we have to fear is fear itself." -- Franklin D. Roosevelt

When you embark on the task itself, you would say, "well, it's easier than
expected". And bonuses are used to promote things like this stuff. The first
task you do every day would reward you a bonus.

### Achievement

Our system would reward your persistence. For example, [clocking
in](../features/clockin.md) for 100 days would unlock an achievement named
"100-day Legend" and give you a reward.

### Lucky Chest

This is a random reward that would appear occasionally anytime you are using
this plugin . You can disable this functionality or restrict when it can occur
if you do not want to be disrupted during a pomodoro.

