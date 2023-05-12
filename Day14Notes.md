# **Lecture 14 Notes, 3/6/23**

## **Introduction**
----
#### Definition
**Test suite quality** assesses the quality of a test suite (with respect to an external notion of utility) and allows test suites to be compared.
#### Definition
**Code coverage** is how much code is executed by a test suite.

## **Test Suite Quality Metrics**
----
- Determine "how good" a test suite is compared to another test suite.
- Higher quality test suite -> greater confidence in code.

#### Defintion
**Line Coverage** is one possible measurement that looks at statements that are executed as all tests are run.
- Coverage libraries will instrument the code to collect the data.
- What is wrong with line coverage?
    - Covering all lines ≠ finding all bugs.
    - Implicit control flow -> Code with hidden if statements.

#### Definition
**Interesting Tests** are those that trigger both implicit and explicit control flow changes.
- Cause different branches to execute.

#### Definition
**Branch Coverage**: Count the total number of conditional branches exercised by a test suite.
- Count each outcome of an if statement seperately.
- 100% branch coverage typically implies 100% line coverage.
- Branch coverage subsumes line coverage.
    - Comes at a cost: branch coverage is "more expensive" in that it is harder for a test suite to house high branch voverage than it is to have high line coverage.

#### **Other Types of Coverage**
- Function Coverage
- Condition Coverage
- Modified Condition / Decision Coverage (MC/DC)
    - Loosely: Function + Branch

**Is it worth maximizing these metrics?**
- Yes - It finds more corner case bugs in practice.

## **Alternative View on Testing**
----
- Bugs experienced by users are the bugs that matter.
- If user-experienced bugs are the ones that matter then testing should be devoted to sampling these inputs.
    - Exhaustive testing is usually too expensive.
- Potential options
    - Uniform random sample
    - Sample from most common
    - Sample from most harmful
- The problem with sampling
    - Bias or error
- Testing gives us confidence the same way sampling or pollion for a survey gives us confidence.
- Sampling Bias - Some members of a population are less likely to be selected.
    - Unrepresentative of that segment of population.
- Solutions to Sampling Bias
    - In stats -> Increase sample size or know something about the distribution.
    - In software Engineering -> We don't know possible distributions.

## **Kinds of Testing to Assess External Quality**
----
#### Definition
- **Alpha Testing** -> Done by developers.

#### Definition
- **Beta Testing** -> Done by external users.
    - How does this information get back to the developer?
        - Bug report.
        - Automatic data collection and crash reports.
#### Definition
- **A/B Testing** -> Release two variables of software

#### **Mutation Testing**
- A seemingly unrelated question: How do you tests if a bloodhound is any good?
    - Intentionally hide person and see if the hound can find them.
- How can we test if a test suite is any good?
    - Intentionally hide bugs in the code and see if the tests can find them.

#### Definition
- **Defect Seeding** is the process of adding defects/bugs to the code.
    - Typically similar to real bugs.
    - Done by changing or mutating the source code.

#### Definition
- **Mutation Analysis/Testing** is defined as intentionally seeding defects and counting how many are found.
    - It is only as good as the bugs that are seeded.
## **Conclusion**
----
- Test suite quality metircs determines how good a test suite is in comparison to another test suite.
- Test suite quality metrics gives us confidence in our test suite.
- There are various forms of coverage such as:
    - Line, branch, function, condition, and modified condition / decision coverage.
- There are various forms of testing such as:
    - Alpha, beta, A/B, and mutation testing.