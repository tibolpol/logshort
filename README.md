# logshort

Filter a text stream, replacing consecutive stable lines by a single placeholder.
Comparison is done not by character but by word. Detect multi-line pattern.
Langage is awk script.

Could be considered as a human-readable lossy text compression, fitting well for reporting huge repetitive log files.
