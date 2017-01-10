# Finagle

[Finagle](https://twitter.github.io/finagle/) is an extensible RPC
system for the JVM, used to construct high-concurrency servers.

## Preceding research used

### [Algorithms for Unevenly Spaced Time Series: Moving Averages and Other Rolling Operators](http://www.eckner.com/papers/ts_alg.pdf)

_Andreas Eckner_

__Abstract.__ This paper describes algorithms for efficiently
calculating certain rolling time series operators for unevenly spaced
data. In particular, we show how to calculate simple moving averages
(SMAs), exponential moving averages (EMAs), and related operators in
linear time with respect to the number of observations in a time
series. A web appendix provides an implementation of these algorithms
in the programming language C and a package (forthcoming) for the
statistical software R.

### [The Power of Two Choices in Randomized Load Balancing](https://www.eecs.harvard.edu/~michaelm/postscripts/mythesis.pdf)

_Michael David Mitzenmacher_

Suppose that n balls are placed into n bins, each ball being placed
into a bin chosen independently and uniformly at random. Then, with
high probability, the maximum load in any bin is approximately
`log(n)/log(log(n))`. Suppose instead that each ball is placed
sequentially into the least full of d bins chosen independently and
uniformly at random. It has recently been shown that the maximum load
is then only `log(log(n))/log(d) + O(1)` with high probability. Thus
giving each ball two choices instead of just one leads to an
exponential improvement in the maximum load. This result demonstrates
the power of two choices, and it has several applications to load
balancing in distributed systems.

In this thesis, we expand upon this result by examining related models
and by developing techniques for studying similar randomized load
balancing schemes. We first remove the restriction above that the
balls be placed sequentially. We provide a lower bound demonstrating a
tradeoff between the number of rounds of communication used and the
maximum load achieved. Our lower bound shows that one cannot achieve a
maximum load of `O(log(log(n)))` with only a constant number of rounds
of communication. We also provide simple algorithms that match our
lower bounds within a constant factor.

We then consider dynamic models, where balls enter and leave the
system over time. This leads to a natural queueing problem: customers
arrive as a Poisson stream at a collection of `n` servers. Each
customer chooses `d` of these servers independently and uniformly at
random and queues at the server currently containing the fewest
customers.  Customers require an exponentially distributed amount of
service time before leaving the system. We call this model the
supermarket model. We determine the behavior of the supermarket model
by defining an idealized process, corresponding to a system of
infinite size, which is cleaner and easier to analyze. We then relate
the idealized system to the infinite system, bounding the error
between them. Using this technique, we also study several
generalizations of the supermarket model and many other load balancing
schemes. Our results demonstrate the effectiveness of having two
choices in many situations.

### [Dapper, a Large-Scale Distributed Systems Tracing Infrastructure](https://static.googleusercontent.com/media/research.google.com/en//archive/papers/dapper-2010-1.pdf)

_Benjamin H. Sigelman, Luiz André Barroso, Mike Burrows, Pat
Stephenson, Manoj Plakal, Donald Beaver, Saul Jaspan, and Chandan
Shanbhag_

__Abstract.__ Modern Internet services are often implemented as
complex, large-scale distributed systems. These applications are
constructed from collections of software modules that may be developed
by different teams, perhaps in different programming languages, and
could span many thousands of machines across multiple physical
facilities.  Tools that aid in understanding system behavior and
reasoning about performance issues are invaluable in such an
environment.  Here we introduce the design of Dapper, Google’s
production distributed systems tracing infrastructure, and describe
how our design goals of low overhead, application-level transparency,
and ubiquitous deployment on a very large scale system were
met. Dapper shares conceptual similarities with other tracing systems,
particularly Magpie and X-Trace, but certain design choices were made
that have been key to its success in our environment, such as the use
of sampling and restricting the instrumentation to a rather small
number of common libraries.  The main goal of this paper is to report
on our experience building, deploying and using the system for over
two years, since Dapper’s foremost measure of success has been its
usefulness to developer and operations teams. Dapper began as a
self-contained tracing tool but evolved into a monitoring platform
which has enabled the creation of many different tools, some of which
were not anticipated by its designers. We describe a few of the
analysis tools that have been built using Dapper, share statistics
about its usage within Google, present some example use cases, and
discuss lessons learned so far.

## Research produced

### [Your Server as a Function](https://monkey.org/~marius/funsrv.pdf)

_Marius Eriksen_

__Abstract.__ Building server software in a large-scale setting, where
systems exhibit a high degree of concurrency and environmental
variability, is a challenging task to even the most experienced
programmer. Ef- ficiency, safety, and robustness are paramount—goals
which have traditionally conflicted with modularity, reusability, and
flexibility.  We describe three abstractions which combine to present
a powerful programming model for building safe, modular, and efficient
server software: Composable futures are used to relate concurrent,
asynchronous actions; services and filters are specialized functions
used for the modular composition of our complex server software.
Finally, we discuss our experiences using these abstractions and
techniques throughout Twitter’s serving infrastructure.
