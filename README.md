# Stats_learning
In simple words statistics is the study and manipulation of given data. It deals with the analysis and computation of given numerical data.
Statistics is a branch of mathematics that deals with collecting, analyzing, interpreting, and visualizing empirical data. Descriptive statistics and inferential statistics are the two major areas of statistics. Descriptive statistics are for describing the properties of sample and population data (what has happened). Inferential statistics use those properties to test hypotheses, reach conclusions, and make predictions (what can you expect).
POPULATION :: In statistics, the population comprises all observations (data points) about the subject under study.
SAMPLE :: In statistics, a sample is a subset of the population. It is a small portion of the total observed population.

MEASURES OF CENTRAL TENDENCIES-
MEAN :: The arithmetic mean is the average of all the data points.If there are n number of observations and xi is the ith observation, then mean is:
Mean = sum of all the observations/ total numbers of observations

def mean(xs: List[float]) -> float:
    return sum(xs) / len(xs)

mean(num_friends)   # 7.333333


assert 7.3333 < mean(num_friends) < 7.3334



MEDIAN :: Median is the middle value that divides the data into two equal parts once it sorts the data in ascending order.
If the total number of data points (n) is odd, the median is the value at position (n+1)/2
When the total number of observations (n) is even, the median is the average value of observations at n/2 and (n+2)/2 positions.

# The underscores indicate that these are "private" functions, as they're
# intended to be called by our median function but not by other people
# using our statistics library.
def _median_odd(xs: List[float]) -> float:
    """If len(xs) is odd, the median is the middle element"""
    return sorted(xs)[len(xs) // 2]

def _median_even(xs: List[float]) -> float:
    """If len(xs) is even, it's the average of the middle two elements"""
    sorted_xs = sorted(xs)
    hi_midpoint = len(xs) // 2  # e.g. length 4 => hi_midpoint 2
    return (sorted_xs[hi_midpoint - 1] + sorted_xs[hi_midpoint]) / 2

def median(v: List[float]) -> float:
    """Finds the 'middle-most' value of v"""
    return _median_even(v) if len(v) % 2 == 0 else _median_odd(v)

assert median([1, 10, 2, 9, 5]) == 5
assert median([1, 9, 2, 10]) == (2 + 9) / 2


assert median(num_friends) == 6
