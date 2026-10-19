## Theory

Probability is a measure of how likely an event is to occur, ranging from 0 (impossible) to 1 (certain). A probability distribution describes the possible outcomes of a random variable and their probabilities. Discrete probability distributions are used when outcomes are countable.

- Binomial Distribution: Calculates the probability of a fixed number of successes in a fixed number of independent trials, with the same probability of success each time.
- Poisson Distribution: Calculates the probability of a specific number of events occurring in a fixed interval when events occur at a constant average rate.
- Geometric Distribution: Calculates the probability that the first success occurs on a particular trial, assuming independent trials with a constant probability of success.

## What I Learned

Through this module, I learned how to understand and apply Binomial, Poisson, and Geometric probability distributions. I explored their formulas, calculated probabilities, and understood concepts such as mean and variance. I also learned how changing parameters affects probability outcomes and visualized distributions using interactive graphs. This helped me connect theoretical probability concepts with practical applications.


# Prompts Used to Build the Web App

## Binomial Distribution

### Prompt 1 — Create the Basic Lab Application

Create a simple educational web application for an undergraduate AIML laboratory.

Title: Discrete Probability Distributions

The application will eventually contain:

1. Binomial Distribution
2. Poisson Distribution
3. Geometric Distribution

For now, implement only the basic application structure and the Binomial Distribution module.

Keep the UI simple and clean. Do not add unnecessary features.

Create a navigation/header with:

- Home
- Binomial
- Poisson
- Geometric

Only the Binomial page needs to be functional at this stage.

### Prompt 2 — Add Binomial Inputs

Implement the Binomial Distribution section.

Add two input controls:

- Number of trials \\(n\\)
- Probability of success \\(p\\)

Set default values:

- \\(n = 20\\)
- \\(p = 0.35\\)

Validate the inputs:

- \\(n\\) must be a positive integer.
- \\(p\\) must be between 0 and 1.

Display the selected values clearly. Do not add simulation yet.

### Prompt 3 — Calculate Binomial Statistics

Add the Binomial probability calculations using the selected \\(n\\) and \\(p\\).

Calculate and display:

- Mean
- Variance
- Standard deviation
- Second moment \\(E[X^2]\\)
- Skewness

Use the following formulas:

- Mean: \\(np\\)
- Variance: \\(np(1-p)\\)
- Second moment: \\(\operatorname{Var}(X)+[E(X)]^2\\)
- Skewness: \\(\frac{1-2p}{\sqrt{np(1-p)}}\\)

Display the results in simple statistic cards.

For the default values \\(n=20\\) and \\(p=0.35\\), verify that the mean is 7 and variance is 4.55.

### Prompt 4 — Add PMF

Add a Binomial PMF calculator.

For \\(X \sim \operatorname{Binomial}(n,p)\\), calculate \\(P(X=k)\\).

Allow the student to enter \\(k\\).

Validate that:

\\[ 0 \leq k \leq n \\]

Display the probability clearly.

Also display the mathematical expression:

\\[ P(X=k)=\binom{n}{k}p^k(1-p)^{n-k} \\]

Explain in one simple sentence what the result means.

### Prompt 5 — Add CDF

Add a Binomial CDF calculator.

Allow the student to enter \\(k\\).

Calculate:

\\[ P(X\leq k) \\]

Also calculate:

\\[ P(X>k)=1-P(X\leq k) \\]

Display both results.

Explain: “P(X ≤ k) means the probability of getting k or fewer successes.”

### Prompt 6 — Add Binomial PMF Graph

Add a bar chart showing the Binomial PMF.

- X-axis: Number of successes \\(X\\)
- Y-axis: Probability \\(P(X)\\)
- Plot values for \\(X=0,1,2,\ldots,n\\).
- Use the current values of \\(n\\) and \\(p\\).
- Add a vertical dashed reference line at the mean.
- Add a tooltip showing:
  - \\(X=\\) value
  - \\(P(X=\text{value})=\\) probability

Update the graph automatically whenever \\(n\\) or \\(p\\) changes.

## Poisson Distribution

### Prompt 7 — Add Poisson Inputs

Implement the Poisson Distribution module in the existing application.

Add input controls for:

- Average number of events (\\(\lambda\\))
- Number of events (\\(k\\))

Set default values:

- \\(\lambda=3\\)
- \\(k=2\\)

Validate the inputs:

- \\(\lambda\\) must be greater than 0.
- \\(k\\) must be a non-negative integer.

Display the selected values clearly and maintain the existing UI design.

### Prompt 8 — Calculate Poisson Statistics

Add Poisson Distribution statistics using the selected value of \\(\lambda\\).

Calculate and display:

- Mean
- Variance
- Standard deviation
- Second moment \\(E[X^2]\\)
- Skewness

Use the following formulas:

- Mean: \\(\lambda\\)
- Variance: \\(\lambda\\)
- Standard deviation: \\(\sqrt{\lambda}\\)
- Second moment: \\(\lambda+\lambda^2\\)
- Skewness: \\(\frac{1}{\sqrt{\lambda}}\\)

Display the results in simple statistic cards.

For the default value \\(\lambda=3\\), verify that the mean and variance are both 3.

### Prompt 9 — Add Poisson PMF

Add a Poisson PMF calculator.

For \\(X \sim \operatorname{Poisson}(\lambda)\\), calculate \\(P(X=k)\\).

Use the selected values of \\(\lambda\\) and \\(k\\).

Display the mathematical formula:

\\[ P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!} \\]

Display the calculated probability clearly and explain in one simple sentence what it means.

Validate the inputs before performing the calculation.

### Prompt 10 — Add Poisson CDF

Add a Poisson CDF calculator.

Allow the student to enter \\(k\\) and calculate:

\\[ P(X\leq k)=\sum\_{i=0}^{k} \frac{e^{-\lambda}\lambda^i}{i!} \\]

Also calculate:

\\[ P(X>k)=1-P(X\leq k) \\]

Display both probabilities clearly.

Explain that \\(P(X\leq k)\\) represents the probability of observing \\(k\\) or fewer events in a fixed interval.

### Prompt 11 — Add Poisson PMF Graph

Add an interactive bar chart showing the Poisson PMF.

- X-axis: Number of events \\(X\\)
- Y-axis: Probability \\(P(X)\\)
- Plot event counts starting from \\(X=0\\).
- Use the current value of \\(\lambda\\).
- Add a vertical dashed reference line at the mean.
- Add tooltips displaying the event count and corresponding probability.
- Update the graph automatically when \\(\lambda\\) changes.

Choose a suitable range of event counts so the graph displays the distribution clearly.

### Prompt 12 — Add Poisson Parameter Comparison

Add a feature that allows students to compare Poisson distributions for different values of \\(\lambda\\).

Use default comparison values of \\(\lambda=2\\), \\(\lambda=3\\), and \\(\lambda=5\\).

Display the distributions on a comparison graph with a clear legend.

Explain how increasing \\(\lambda\\) changes the distribution's center, spread, and probability of observing different event counts.

Keep the comparison interactive and consistent with the existing design.

## Geometric Distribution

### Prompt 13 — Add Geometric Inputs

Implement the Geometric Distribution module in the existing application.

Add input controls for:

- Probability of success (\\(p\\))
- Trial number (\\(k\\))

Set default values:

- \\(p=0.8\\)
- \\(k=3\\)

Define \\(X\\) as the trial number on which the first success occurs, so \\(X\\) starts at 1.

Validate the inputs:

- \\(p\\) must be greater than 0 and less than or equal to 1.
- \\(k\\) must be a positive integer.

Display the selected values clearly and maintain the existing UI design.

### Prompt 14 — Calculate Geometric Statistics

Add Geometric Distribution statistics using the selected value of \\(p\\).

Calculate and display:

- Mean
- Variance
- Standard deviation
- Second moment \\(E[X^2]\\)
- Skewness

Use the following formulas:

- Mean: \\(\frac{1}{p}\\)
- Variance: \\(\frac{1-p}{p^2}\\)
- Standard deviation: \\(\frac{\sqrt{1-p}}{p}\\)
- Second moment: \\(\frac{2-p}{p^2}\\)
- Skewness: \\(\frac{2-p}{\sqrt{1-p}}\\), for \\(0\<p<1\\)

Display the results in simple statistic cards.

Handle \\(p=1\\) safely, since success is guaranteed on the first trial and the variance is zero.

### Prompt 15 — Add Geometric PMF

Add a Geometric PMF calculator.

For \\(X \sim \operatorname{Geometric}(p)\\), where \\(X\\) represents the trial number of the first success, calculate \\(P(X=k)\\).

Use the formula:

\\[ P(X=k)=(1-p)^{k-1}p \\]

Allow the student to enter \\(k\\).

Validate that \\(k\\) is a positive integer.

Display the calculated probability clearly and explain that it represents the probability that the first success occurs on exactly the \\(k\\)-th trial.

### Prompt 16 — Add Geometric CDF

Add a Geometric CDF calculator.

Allow the student to enter \\(k\\) and calculate:

\\[ P(X\leq k)=1-(1-p)^k \\]

Also calculate:

\\[ P(X>k)=(1-p)^k \\]

Display both probabilities clearly.

Explain that \\(P(X\leq k)\\) represents the probability of achieving the first success within the first \\(k\\) trials.

### Prompt 17 — Add Geometric PMF Graph

Add an interactive bar chart showing the Geometric PMF.

- X-axis: Trial number \\(X\\)
- Y-axis: Probability \\(P(X)\\)
- Plot probabilities for trial numbers starting from \\(X=1\\).
- Use the current value of \\(p\\).
- Add a vertical dashed reference line at the mean.
- Add tooltips displaying the trial number and probability.
- Update the graph automatically whenever \\(p\\) changes.

Choose a suitable range of trial numbers so the distribution is easy to understand.

### Prompt 18 — Add Input Validation and Dynamic Updates

Review the Binomial, Poisson, and Geometric modules.

Ensure that:

- All inputs are validated correctly.
- Invalid inputs show clear error messages.
- Probabilities remain within the range 0 to 1, allowing for minor floating-point rounding.
- Statistics, PMF, CDF, and graphs update whenever their relevant inputs change.
- Edge cases, such as \\(p=1\\) in the Geometric Distribution, are handled safely.
- All three modules follow a consistent layout and visual style.

## Home Page and Navigation

### Prompt 19 — Create the Home Page

Create a simple home page for the Discrete Probability Distributions educational web application.

Include:

- The application title.
- A brief introduction to discrete probability distributions.
- Short descriptions of the Binomial, Poisson, and Geometric distributions.
- Navigation links or buttons to open each distribution module.

Keep the home page clean, simple, and easy to navigate. Do not place calculators or probability graphs on the home page.

### Prompt 20 — Final UI Consistency

Review the entire web application and ensure that the Home, Binomial, Poisson, and Geometric pages work correctly.

Maintain a consistent header, navigation, spacing, typography, input styling, statistic cards, and graph styling across all modules.

Ensure the website is responsive and that all calculations and graphs work correctly without requiring a page reload.

Do not add unnecessary features. Focus on mathematical correctness, usability, and a clean interface.
