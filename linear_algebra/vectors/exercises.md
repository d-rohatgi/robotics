# Vectors — Exercises 1.1–1.20

Questions from [the textbook, pages 25–28](https://web.stanford.edu/~boyd/vmls/vmls.pdf#page=35).
Write your explanations and mathematical answers
under each **Answer** prompt. Open a Markdown preview with math support to see
the equations rendered.

All of these exercises can be answered without code. Optional Python starters
are linked beside exercises 1.6, 1.7, 1.10, 1.13, and 1.20 for checking
calculations. For any other exercise, create a file using the same naming
pattern, such as `1_2.py`, when you want to experiment with code.

The questions use textbook notation: subscripts start at 1, slices include both
endpoints, and parentheses can denote concatenation. Translate this notation
when writing Python.

## 1.1 — Vector equations

Determine whether each of the equations below is true, false, or contains
bad notation (and therefore does not make sense).

**(a)**

$$
\begin{bmatrix}1\\2\\1\end{bmatrix} = (1,2,1).
$$

**Answer:**

True

**(b)**

$$
\begin{bmatrix}1\\2\\1\end{bmatrix} = \left[\,1,\quad 2,\quad 1\,\right].
$$

**Answer:**

False

**(c)** $(1,(2,1)) = ((1,2),1)$.

**Answer:**

True

## 1.2 — Vector notation

Which of the following expressions uses correct notation? When the expression
does make sense, give its length. In the following, $a$ and $b$ are 10-vectors,
and $c$ is a 20-vector.

**(a)** $a+b-c_{3:12}$.

**Answer (valid notation? length?):**

Valid, vector has length of 10

**(b)** $(a,b,c_{3:13})$.

**Answer (valid notation? length?):**

Valid, vector has a length of 31

**(c)** $2a+c$.

**Answer (valid notation? length?):**

Not valid

**(d)** $(a,1)+(c_1,b)$.

**Answer (valid notation? length?):**

Valid, has length of 11

**(e)** $((a,b),a)$.

**Answer (valid notation? length?):**

Valid, has length of 30

**(f)** $\begin{bmatrix}a & b\end{bmatrix}+4c$.

**Answer (valid notation? length?):**

not valid

**(g)**

$$
\begin{bmatrix}a\\b\end{bmatrix}+4c.
$$

**Answer (valid notation? length?):**

Valid, has length of 20
## 1.3 — Overloading

Which of the following expressions uses correct notation? If the notation is
correct, is it also unambiguous? Assume that $a$ is a 10-vector and $b$ is a
20-vector.

**(a)** $b=(0,a)$.

**Answer (valid notation? unambiguous?):**

<!-- Write your answer here. -->

**(b)** $a=(0,b)$.

**Answer (valid notation? unambiguous?):**

<!-- Write your answer here. -->

**(c)** $b=(0,a,0)$.

**Answer (valid notation? unambiguous?):**

<!-- Write your answer here. -->

**(d)** $a=0=b$.

**Answer (valid notation? unambiguous?):**

<!-- Write your answer here. -->

## 1.4 — Periodic energy usage

The 168-vector $w$ gives the hourly electricity consumption of a manufacturing
plant, starting on Sunday midnight to 1AM, over one week, in MWh
(megawatt-hours). The consumption pattern is the same each day, i.e., it is
24-periodic, which means that $w_{t+24}=w_t$ for $t=1,\ldots,144$. Let $d$ be
the 24-vector that gives the energy consumption over one day, starting at
midnight.

**(a)** Use vector notation to express $w$ in terms of $d$.

**Answer:**

<!-- Write your answer here. -->

**(b)** Use vector notation to express $d$ in terms of $w$.

**Answer:**

<!-- Write your answer here. -->

## 1.5 — Interpreting sparsity

Suppose the $n$-vector $x$ is sparse, i.e., has only a few nonzero entries.
Give a short sentence or two explaining what this means in each of the
following contexts.

**(a)** $x$ represents the daily cash flow of some business over $n$ days.

**Answer:**

<!-- Write your answer here. -->

**(b)** $x$ represents the annual dollar value purchases by a customer of $n$
products or services.

**Answer:**

<!-- Write your answer here. -->

**(c)** $x$ represents a portfolio, say, the dollar value holdings of $n$ stocks.

**Answer:**

<!-- Write your answer here. -->

**(d)** $x$ represents a bill of materials for a project, i.e., the amounts of
$n$ materials needed.

**Answer:**

<!-- Write your answer here. -->

**(e)** $x$ represents a monochrome image, i.e., the brightness values of $n$
pixels.

**Answer:**

<!-- Write your answer here. -->

**(f)** $x$ is the daily rainfall in a location over one year.

**Answer:**

<!-- Write your answer here. -->

## 1.6 — Vector of differences

Optional code: [1_6.py](1_6.py).

Suppose $x$ is an $n$-vector. The associated vector of differences is the
$(n-1)$-vector $d$ given by

$$
d=(x_2-x_1,x_3-x_2,\ldots,x_n-x_{n-1}).
$$

Express $d$ in terms of $x$ using vector operations (e.g., slicing notation,
sum, difference, linear combinations, inner product). The difference vector
has a simple interpretation when $x$ represents a time series. For example,
if $x$ gives the daily value of some quantity, $d$ gives the day-to-day changes
in the quantity.

**Answer:**

<!-- Write your answer here. -->

## 1.7 — Transforming between two encodings for Boolean vectors

Optional code: [1_7.py](1_7.py).

A Boolean $n$-vector is one for which all entries are either 0 or 1. Such
vectors are used to encode whether each of $n$ conditions holds, with $a_i=1$
meaning that condition $i$ holds. Another common encoding of the same
information uses the two values $-1$ and $+1$ for the entries. For example the
Boolean vector $(0,1,1,0)$ would be written using this alternative encoding as
$(-1,+1,+1,-1)$. Suppose that $x$ is a Boolean vector with entries that are 0
or 1, and $y$ is a vector encoding the same information using the values $-1$
and $+1$. Express $y$ in terms of $x$ using vector notation. Also, express $x$
in terms of $y$ using vector notation.

**Answer ($y$ in terms of $x$):**

<!-- Write your answer here. -->

**Answer ($x$ in terms of $y$):**

<!-- Write your answer here. -->

## 1.8 — Profit and sales vectors

A company sells $n$ different products or items. The $n$-vector $p$ gives the
profit, in dollars per unit, for each of the $n$ items. (The entries of $p$ are
typically positive, but a few items might have negative entries. These items
are called *loss leaders*, and are used to increase customer engagement in
the hope that the customer will make other, profitable purchases.) The
$n$-vector $s$ gives the total sales of each of the items, over some period
(such as a month), i.e., $s_i$ is the total number of units of item $i$ sold.
(These are also typically nonnegative, but negative entries can be used to reflect
items that were purchased in a previous time period and returned in this
one.) Express the total profit in terms of $p$ and $s$ using vector notation.

**Answer:**

<!-- Write your answer here. -->

## 1.9 — Symptoms vector

A 20-vector $s$ records whether each of 20 different symptoms is present in a
medical patient, with $s_i=1$ meaning the patient has the symptom and $s_i=0$
meaning she does not. Express the following using vector notation.

**(a)** The total number of symptoms the patient has.

**Answer:**

<!-- Write your answer here. -->

**(b)** The patient exhibits five out of the first ten symptoms.

**Answer:**

<!-- Write your answer here. -->

## 1.10 — Total score from course record

Optional code: [1_10.py](1_10.py).

The record for each student in a class is given as a 10-vector $r$, where
$r_1,\ldots,r_8$ are the grades for the 8 homework assignments, each on a 0–10
scale, $r_9$ is the midterm exam grade on a 0–120 scale, and $r_{10}$ is the
final exam score on a 0–160 scale. The student's total course score $s$, on a
0–100 scale, is based 25% on the homework, 35% on the midterm exam, and 40% on
the final exam. Express $s$ in the form $s=w^T r$. (That is, determine the
10-vector $w$.) You can give the coefficients of $w$ to 4 digits after the
decimal point.

**Answer:**

<!-- Write your answer here. -->

## 1.11 — Word count and word count histogram vectors

Suppose the $n$-vector $w$ is the word count vector associated with a document
and a dictionary of $n$ words. For simplicity we will assume that all words
in the document appear in the dictionary.

**(a)** What is $\mathbf{1}^T w$?

**Answer:**

<!-- Write your answer here. -->

**(b)** What does $w_{282}=0$ mean?

**Answer:**

<!-- Write your answer here. -->

**(c)** Let $h$ be the $n$-vector that gives the histogram of the word counts,
i.e., $h_i$ is the fraction of the words in the document that are word $i$.
Use vector notation to express $h$ in terms of $w$. (You can assume that the
document contains at least one word.)

**Answer:**

<!-- Write your answer here. -->

## 1.12 — Total cash value

An international company holds cash in five currencies: USD (US dollar),
RMB (Chinese yuan), EUR (euro), GBP (British pound), and JPY (Japanese yen),
in amounts given by the 5-vector $c$. For example, $c_2$ gives the number of
RMB held. Negative entries in $c$ represent liabilities or amounts owed.
Express the total (net) value of the cash in USD, using vector notation. Be
sure to give the size and define the entries of any vectors that you
introduce in your solution. Your solution can refer to currency exchange
rates.

**Answer:**

<!-- Write your answer here. -->

## 1.13 — Average age in a population

Optional code: [1_13.py](1_13.py).

Suppose the 100-vector $x$ represents the distribution of ages in some
population of people, with $x_i$ being the number of $i-1$ year olds, for
$i=1,\ldots,100$. (You can assume that $x\ne 0$, and that there is no one in
the population over age 99.) Find expressions, using vector notation, for
the following quantities.

**(a)** The total number of people in the population.

**Answer:**

<!-- Write your answer here. -->

**(b)** The total number of people in the population age 65 and over.

**Answer:**

<!-- Write your answer here. -->

**(c)** The average age of the population. (You can use ordinary division of
numbers in your expression.)

**Answer:**

<!-- Write your answer here. -->

## 1.14 — Industry or sector exposure

Consider a set of $n$ assets or stocks that we invest in. Let $f$ be an
$n$-vector that encodes whether each asset is in some specific industry or
sector, e.g., pharmaceuticals or consumer electronics. Specifically, we take
$f_i=1$ if asset $i$ is in the sector, and $f_i=0$ if it is not. Let the
$n$-vector $h$ denote a portfolio, with $h_i$ the dollar value held in asset
$i$ (with negative meaning a short position). The inner product $f^T h$ is
called the (dollar value) *exposure* of our portfolio to the sector. It gives
the net dollar value of the portfolio that is invested in assets from the
sector. A portfolio $h$ is called *neutral* (to a sector or industry) if
$f^T h=0$.

A portfolio $h$ is called *long only* if each entry is nonnegative, i.e.,
$h_i\ge 0$ for each $i$. This means the portfolio does not include any short
positions.

What does it mean if a long-only portfolio is neutral to a sector, say,
pharmaceuticals? Your answer should be in simple English, but you should
back up your conclusion with an argument.

**Answer:**

<!-- Write your answer here. -->

## 1.15 — Cheapest supplier

You must buy $n$ raw materials in quantities given by the $n$-vector $q$,
where $q_i$ is the amount of raw material $i$ that you must buy. A set of $K$
potential suppliers offer the raw materials at prices given by the
$n$-vectors $p_1,\ldots,p_K$. (Note that $p_k$ is an $n$-vector; $(p_k)_i$ is
the price that supplier $k$ charges per unit of raw material $i$.) We will
assume that all quantities and prices are positive.

If you must choose just one supplier, how would you do it? Your answer should
use vector notation.

**Answer:**

<!-- Write your answer here. -->

A (highly paid) consultant tells you that you might do better (i.e., get a
better total cost) by splitting your order into two, by choosing two
suppliers and ordering $(1/2)q$ (i.e., half the quantities) from each of the
two. He argues that having a diversity of suppliers is better. Is he right?
If so, explain how to find the two suppliers you would use to fill half the
order.

**Answer:**

<!-- Write your answer here. -->

## 1.16 — Inner product of nonnegative vectors

A vector is called *nonnegative* if all its entries are nonnegative.

**(a)** Explain why the inner product of two nonnegative vectors is
nonnegative.

**Answer:**

<!-- Write your answer here. -->

**(b)** Suppose the inner product of two nonnegative vectors is zero. What
can you say about them? Your answer should be in terms of their respective
sparsity patterns, i.e., which entries are zero and nonzero.

**Answer:**

<!-- Write your answer here. -->

## 1.17 — Linear combinations of cash flows

We consider cash flow vectors over $T$ time periods, with a positive entry
meaning a payment received, and negative meaning a payment made. A (unit)
*single period loan*, at time period $t$, is the $T$-vector $l_t$ that
corresponds to a payment received of \$1 in period $t$ and a payment made of
$(1+r)$ dollars in period $t+1$, with all other payments zero. Here $r>0$ is
the interest rate (over one period).

Let $c$ be a \$1 $(T-1)$-period loan, starting at period 1. This means that
\$1 is received in period 1, $(1+r)^{T-1}$ dollars is paid in period $T$, and
all other payments (i.e., $c_2,\ldots,c_{T-1}$) are zero. Express $c$ as a
linear combination of single period loans.

**Answer:**

<!-- Write your answer here. -->

## 1.18 — Linear combinations of linear combinations

Suppose that each of the vectors $b_1,\ldots,b_k$ is a linear combination of
the vectors $a_1,\ldots,a_m$, and $c$ is a linear combination of
$b_1,\ldots,b_k$. Then $c$ is a linear combination of $a_1,\ldots,a_m$. Show
this for the case with $m=k=2$. (Showing it in general is not much more
difficult, but the notation gets more complicated.)

**Answer:**

<!-- Write your answer here. -->

## 1.19 — Auto-regressive model

Suppose that $z_1,z_2,\ldots$ is a time series, with the number $z_t$ giving
the value in period or time $t$. For example $z_t$ could be the gross sales
at a particular store on day $t$. An *auto-regressive* (AR) model is used to
predict $z_{t+1}$ from the previous $M$ values, $z_t,z_{t-1},\ldots,z_{t-M+1}$:

$$
\hat{z}_{t+1}=(z_t,z_{t-1},\ldots,z_{t-M+1})^T\beta,
\qquad t=M,M+1,\ldots.
$$

Here $\hat{z}_{t+1}$ denotes the AR model's prediction of $z_{t+1}$, $M$ is
the memory length of the AR model, and the $M$-vector $\beta$ is the AR model
coefficient vector. For this problem we will assume that the time period is
daily, and $M=10$. Thus, the AR model predicts tomorrow's value, given the
values over the last 10 days.

For each of the following cases, give a short interpretation or description
of the AR model in English, without referring to mathematical concepts like
vectors, inner product, and so on. You can use words like 'yesterday' or
'today'.

**(a)** $\beta\approx e_1$.

**Answer:**

<!-- Write your answer here. -->

**(b)** $\beta\approx 2e_1-e_2$.

**Answer:**

<!-- Write your answer here. -->

**(c)** $\beta\approx e_6$.

**Answer:**

<!-- Write your answer here. -->

**(d)** $\beta\approx 0.5e_1+0.5e_2$.

**Answer:**

<!-- Write your answer here. -->

## 1.20 — Storage and computation

Optional code: [1_20.py](1_20.py).

How many bytes does it take to store 100 vectors of length $10^5$? How many
flops does it take to form a linear combination of them (with 100 nonzero
coefficients)? About how long would this take on a computer capable of
carrying out 1 Gflop/s?

**Answer (storage in bytes):**

<!-- Write your answer here. -->

**Answer (number of flops):**

<!-- Write your answer here. -->

**Answer (time at 1 Gflop/s):**

<!-- Write your answer here. -->
