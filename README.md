# Indeed Machine Learning CodeSprint
Code for [HackerRank Indeed Machine Learning CodeSprint](https://www.hackerrank.com/contests/indeed-ml-codesprint-2017/challenges/tagging-raw-job-descriptions) on Tagging Raw Job Descriptors.

## Summary

[Indeed.com](https://www.indeed.jobs/career) is an website for matching job seekers and open positions. In this contest, the goal is to automatically generate tags for given a job description, among the following 12:

- `part-time-job`
- `full-time-job`
- `hourly-wage`
- `salary`
- `associate-needed`
- `bs-degree-needed`
- `ms-or-phd-needed`
- `licence-needed`
- `1-year-experience-needed`
- `2-4-years-experience-needed`
- `5-plus-years-experience-needed`
- `supervising-job`

Note that some tags are mutually exclusive (for instance, a job description cannot be `1-year-experience-needed` and `2-4-years-experience-needed` at the same time) whereas others aren't.

## Data

`data.zip` contains two tabs-separated-value (`tsv`) files, as follows:

- `train.tsv`: In the first value, there is a list of tags, separated by spaces, followed by the job description.
- `test.tsv`: Each line contains a job description.

## Output

The algorithm must produce a `tags.tsv` file containing the `tags` header and followed by the tags for each job description in one line, separated by spaces:

```
tags
2-4-years-experience-needed licence-needed
1-year-experience-needed associate-needed

2-4-years-experience-needed licence-needed
1-year-experience-needed licence-needed
.
.
.
part-time-job
bs-degree-needed
ms-or-phd-needed
licence-needed
```

## Evaluation

The [F1 score](https://en.wikipedia.org/wiki/F1_score) will be used as the performance metric, considering the **sum of true/false positives/negatives over all 12 tags**.