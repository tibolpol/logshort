# logshort

Filter a text stream, replacing consecutive stable lines by a single placeholder.
Comparison is done not by character but by word. Detect multi-line pattern.
Language is Awk.

Could be considered as a human-readable lossy text compression, fitting well for reporting huge repetitive log files.
Performance is very poor with large window, but compression rate is good since it is done for human readability.

<pre>test1@tlpbuster:~$ time logshort </tmp/log >/tmp/x
real    2m18,955s
user    2m18,566s
sys     0m0,345s
test1@tlpbuster:~$ time logshort argntail=3 < /tmp/log >/tmp/x1
real    0m46,657s
user    0m46,184s
sys     0m0,373s
test1@tlpbuster:~$ time gzip </tmp/log >/tmp/y
real    0m0,684s
user    0m0,639s
sys     0m0,045s
test1@tlpbuster:~$ ls -lh /tmp/{log,x,x1,y}
-rw-rw-r-- 1 test1 test1  41M oct.   4 09:07 /tmp/log
-rw-rw-r-- 1 test1 test1 470K oct.   4 09:07 /tmp/x
-rw-rw-r-- 1 test1 test1  20M oct.   4 09:07 /tmp/x1
-rw-rw-r-- 1 test1 test1 2,3M oct.   4 09:07 /tmp/y</pre>

