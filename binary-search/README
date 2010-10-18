How it works (briefly)
----------------------

The general principle of binary search is that with a fully* sorted
set of data you can recursively split the data set into values below
and above the target value until you find it, meaning you can get
away with log2(n) seeks+reads instead of (n) reads.

For small data sets, this is not exceptionally useful, but for large
data sets (eg. 2GB log files) it can make a tremendous difference:
if the medium transfer rate were 100MB/s and the medium seek time
were say 100ms, straight line read would take 20 seconds and a
bytewise binary search** would take 3.1 seconds, discounting the
effort required to identify the log line. In short, "/" in "vi" is
not the best approach for huge log files.

Typically this requires either fixed-length records or variable-length
records with a totally unambiguous end-of-record (or start-of-record).
If you have variable-length records with an ambiguous EOR, as is
usually the case with compressed data***, then the data set is
effectively not seekable and binary search would not be possible.

Upper and lower bounds must always be outside the actual range****
to ensure that the first and last values are valid results.

It is entirely possible to have a record which is "on the line" but
not necessarily the desired result. It is also possible that the
record does not exist in the set at all. For these two reasons, you
always want to look for the boundary between an entry which is
greater than or equal to the target value, and a directly preceding
entry which is less than the target value.

Programs included
-----------------

gbs - generalised binary search. This demands user input for each
test, and requires an external program which can be run to extract
each value to test.

---

Footnotes:

* - log files are not always fully sorted: an entry might be added
by start time but only added at finish time, which is a problem for
things like long web requests. One false response can throw a binary
search right off, but generally such anomalies will be relatively
small.
** - for variable-length records, you have to treat them as being
byte-based, have a well-defined system for finding a start-of-record,
and carefully handle overlap.
*** - I gather that gzip in "rsyncable" mode has fixed output block
sizes and so might be suitable for binary search.
**** - In terms of start-of-record. If the upper bound you've already
got is not a start-of-record then it can stay as it is.
