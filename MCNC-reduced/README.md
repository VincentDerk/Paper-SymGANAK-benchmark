These problems were obtained from the [LGSynth91 benchmark](http://web.archive.org/web/20191103092508/https://ddd.fit.cvut.cz/prj/Benchmarks/). Primarily meant for logic synthesis and optimization.

The files in the original benchmark were in .blif format, blif2cnf.pl was used to transform them to DIMAC format. The source of this script is [here](https://web.archive.org/web/20050217212056/sat.inesc-id.pt/~jpms/scripts/bin/blif2cnf).

Any CNF that was finished in less than 10s using the GANAK model counter has been removed, resulting in only the following files:

* apex5.cnf
* apex6.cnf
* C499.cnf
* C880.cnf
* C1355.cnf
* C1908.cnf
* C2670.cnf
* C3540.cnf
* C5315.cnf
* C6288.cnf
* C7552.cnf
* pair.cnf
* t481.cnf
* term1.cnf
* too_large.cnf
* x1.cnf
* x3.cnf

The problem instances dataset is a collection of public benchmarks that is made available for research purposes by the respective authors.
