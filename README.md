# Indeed Machine Learning CodeSprint
Code for [HackerRank Indeed Machine Learning CodeSprint](https://www.hackerrank.com/contests/indeed-ml-codesprint-2017/challenges/tagging-raw-job-descriptions) on Tagging Raw Job Descriptors.

## Dependencies

The code was completely written in [Python 2.7](https://www.python.org/), with the following dependencies:

- [IPython](https://ipython.org/): Used to write [IPython Notebooks](https://ipython.org/ipython-doc/3/notebook/), where the model was implemented.
- [Numpy](http://www.numpy.org/): Python package for numerical computation.
- [scikit-learn](http://scikit-learn.org/): Python package with Machine Learning algorithms.

## Execution

The code is executed via an IPython Notebook by executing the following steps:

1) Install all dependencies.
2) Run the `indeed.ipynb` with the command `$ ipython notebook indeed.ipynb` at the command line. This will open a browser.
3)
3) Place `train.tsv` (containing training data) `test.tsv` (that will be the input descriptions) file a directory called `data/` with respect to where the notebook is located at. For instance, if the notebook is at `/home/user/indeed.ipynb`, the files must be at the paths `/home/user/data/train.tsv` and `/home/user/data/test.tsv`.
4) Return to the browser and open the IPython Notebook tab. In the top menu, select `Cell` and click on `Run All`. This will execute all steps in the notebook.
5) The notebook will generate a `tags.tsv` file at the `data/` directory, e.g., `/home/user/data/tags.tsv` with the output for the given `test.tsv` file.


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