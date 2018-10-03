# logshort

Filter a text stream, replacing consecutive stable lines by a single placeholder.
Comparison is done not by character but by word. Detect multi-line pattern.

Could be considered as a human-readable lossy text compression, fits well for reporting huge repetitive log files.
