## Chapter 2

# Multi-armed Bandits

The most important feature distinguishing reinforcement learning from other types of
learning is that it uses training information that evaluates the actions taken rather
than instructs by giving correct actions. This is what creates the need for active
exploration, for an explicit search for good behavior. Purely evaluative feedback indicates
how good the action taken was, but not whether it was the best or the worst action
possible. Purely instructive feedback, on the other hand, indicates the correct action to
take, independently of the action actually taken. This kind of feedback is the basis of
supervised learning, which includes large parts of pattern classification, artificial neural
networks, and system identification. In their pure forms, these two kinds of feedback
are quite distinct: evaluative feedback depends entirely on the action taken, whereas
instructive feedback is independent of the action taken.

In this chapter we study the evaluative aspect of reinforcement learning in a simplified
setting, one that does not involve learning to act in more than one situation. This
nonassociative setting is the one in which most prior work involving evaluative feedback
has been done, and it avoids much of the complexity of the full reinforcement learning
problem. Studying this case enables us to see most clearly how evaluative feedback differs
from, and yet can be combined with, instructive feedback.

The particular nonassociative, evaluative feedback problem that we explore is a simple
version of the k-armed bandit problem. We use this problem to introduce a number
of basic learning methods which we extend in later chapters to apply to the full reinforcement learning problem. At the end of this chapter, we take a step closer to the full
reinforcement learning problem by discussing what happens when the bandit problem
becomes associative, that is, when actions are taken in more than one situation.

---

## 2.1 A k-armed Bandit Problem

Consider the following learning problem. You are faced repeatedly with a choice among
$k$ different options, or actions. After each choice you receive a numerical reward chosen
from a stationary probability distribution that depends on the action you selected.

Your objective is to maximize the expected total reward over some time period, for example,
over 1000 action selections, or time steps.

This is the original form of the k-armed bandit problem, so named by analogy to a slot
machine, or “one-armed bandit,” except that it has $k$ levers instead of one. Each action
selection is like a play of one of the slot machine’s levers, and the rewards are the payoffs
for hitting the jackpot. Through repeated action selections you are to maximize your
winnings by concentrating your actions on the best levers. Another analogy is that of
a doctor choosing between experimental treatments for a series of seriously ill patients.
Each action is the selection of a treatment, and each reward is the survival or well-being
of the patient. Today the term “bandit problem” is sometimes used for a generalization
of the problem described above, but in this book we use it to refer just to this simple
case.

In our k-armed bandit problem, each of the $k$ actions has an expected or mean reward
given that that action is selected; let us call this the value of that action. We denote the
action selected on time step $t$ as $A_t$, and the corresponding reward as $R_t$.  
The value then of an arbitrary action $a$, denoted $q^\ast(a)$, is the expected reward given that $a$ is selected:

$$
q^\ast(a) = \mathbb{E}[R_t \mid A_t = a]
$$

If you knew the value of each action, then it would be trivial to solve the k-armed bandit
problem: you would always select the action with highest value. We assume that you do
not know the action values with certainty, although you may have estimates. We denote
the estimated value of action $a$ at time step $t$ as $Q_t(a)$. We would like $Q_t(a)$ to be close
to $q^\ast(a)$.

If you maintain estimates of the action values, then at any time step there is at least
one action whose estimated value is greatest. We call these the greedy actions. When you
select one of these actions, we say that you are exploiting your current knowledge of the
values of the actions. If instead you select one of the nongreedy actions, then we say you
are exploring, because this enables you to improve your estimate of the nongreedy action’s
value.

Exploitation is the right thing to do to maximize the expected reward on the one
step, but exploration may produce the greater total reward in the long run. For example,
suppose a greedy action’s value is known with certainty, while several other actions are
estimated to be nearly as good but with substantial uncertainty. The uncertainty is
such that at least one of these other actions probably is actually better than the greedy
action, but you don’t know which one. If you have many time steps ahead on which
to make action selections, then it may be better to explore the nongreedy actions and
discover which of them are better than the greedy action. Reward is lower in the short
run, during exploration, but higher in the long run because after you have discovered
the better actions, you can exploit them many times. Because it is not possible both to
explore and to exploit with any single action selection, one often refers to the “conflict”
between exploration and exploitation.

In any specific case, whether it is better to explore or exploit depends in a complex
way on the precise values of the estimates, uncertainties, and the number of remaining
steps. There are many sophisticated methods for balancing exploration and exploitation
for particular mathematical formulations of the k-armed bandit and related problems.

However, most of these methods make strong assumptions about stationarity and prior
knowledge that are either violated or impossible to verify in applications and in the full
reinforcement learning problem that we consider in subsequent chapters. The guarantees
of optimality or bounded loss for these methods are of little comfort when the assumptions
of their theory do not apply.

In this book we do not worry about balancing exploration and exploitation in a
sophisticated way; we worry only about balancing them at all. In this chapter we present
several simple balancing methods for the k-armed bandit problem and show that they
work much better than methods that always exploit. The need to balance exploration
and exploitation is a distinctive challenge that arises in reinforcement learning; the
simplicity of our version of the k-armed bandit problem enables us to show this in a
particularly clear form.

---

## 2.2 Action-value Methods

We begin by looking more closely at methods for estimating the values of actions and
for using the estimates to make action selection decisions, which we collectively call
**action-value methods**. Recall that the true value of an action is the mean reward when
that action is selected. One natural way to estimate this is by averaging the rewards
actually received:

$$
Q_t(a) = \frac{\text{sum of rewards when $a$ taken prior to $t$}}{\text{number of times $a$ taken prior to $t$}}
$$

$$
Q_t(a) = \frac{\sum_{i=1}^{t-1} R_i \cdot \mathbf{1}_{A_i = a}}{\sum_{i=1}^{t-1} \mathbf{1}_{A_i = a}}
\tag{2.1}
$$

where $\mathbf{1}_{\text{predicate}}$ denotes the random variable that is 1 if *predicate* is true and 0 if it is not.  
If the denominator is zero, then we instead define $Q_t(a)$ as some default value, such as 0.  
As the denominator goes to infinity, by the law of large numbers, $Q_t(a)$ converges to $q^\ast(a)$.  
We call this the **sample-average method** for estimating action values because each
estimate is an average of the sample of relevant rewards. Of course this is just one way
to estimate action values, and not necessarily the best one. Nevertheless, for now let us
stay with this simple estimation method and turn to the question of how the estimates
might be used to select actions.

The simplest action selection rule is to select one of the actions with the highest
estimated value, that is, one of the greedy actions as defined in the previous section.
If there is more than one greedy action, then a selection is made among them in some
arbitrary way, perhaps randomly. We write this greedy action selection method as

$$
A_t = \arg\max_a Q_t(a)
\tag{2.2}
$$

where $\arg\max_a$ denotes the action $a$ for which the expression that follows is maximized
(again, with ties broken arbitrarily). Greedy action selection always exploits current
knowledge to maximize immediate reward; it spends no time at all sampling apparently
inferior actions to see if they might really be better.

A simple alternative is to behave greedily most of the time, but every once in a while,  
say with small probability $\epsilon$, instead select randomly from among all the actions with equal probability, independently of
the action-value estimates. We call methods using this near-greedy action selection rule
**$\epsilon$-greedy methods**. An advantage of these methods is that, in the limit as the number of
steps increases, every action will be sampled an infinite number of times, thus ensuring
that all the $Q_t(a)$ converge to $q^\ast(a)$. This of course implies that the probability of selecting
the optimal action converges to greater than $1 - \epsilon$, that is, to near certainty. These are
just asymptotic guarantees, however, and say little about the practical effectiveness of
the methods.

---

**Exercise 2.1**  
In $\epsilon$-greedy action selection, for the case of two actions and $\epsilon = 0.5$,  
what is the probability that the greedy action is selected? $\;\;\;\; \ast$
