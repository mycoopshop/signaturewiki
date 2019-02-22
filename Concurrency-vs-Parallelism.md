Async is for messages that do not need a response for the program to continue(https://www.quora.com/What-are-the-differences-between-parallel-concurrent-and-asynchronous-programming)

Parallel is for splitting calculations across multiple instances of a compiler or interpreter by spawning processes within a loop(https://rosettacode.org/wiki/Parallel_calculations#Racket, https://docs.oracle.com/cd/A97630_01/server.920/a96524/c20paral.htm, https://www.percona.com/blog/2014/01/07/increasing-slow-query-performance-with-parallel-query-execution/)

Concurrent is for time sharing by not waiting for the result of one line of code while executing subsequent lines of code (https://developer.apple.com/library/archive/documentation/General/Conceptual/ConcurrencyProgrammingGuide/ThreadMigration/ThreadMigration.html, https://developer.apple.com/library/archive/documentation/General/Conceptual/ConcurrencyProgrammingGuide/Glossary/Glossary.html)

## Actor Model
* http://www.dtic.mil/dtic/tr/fulltext/u2/a132326.pdf
* http://wiki.c2.com/?UsefulnessOfNonDeterminism
* https://ercim-news.ercim.eu/en101/special/programming-actors-for-the-internet-of-things
* http://www.erlang-factory.com/upload/presentations/858/euc_pres.pdf
* https://jstoelm.com/episodes/18-ports-by-example/
* https://theburningmonk.com/2012/09/takeaways-from-hewitt-meijer-and-szyperskis-talk-on-the-actor-model/
* http://blogs.perl.org/users/rafael_garcia-suarez/2011/10/why-dart-is-not-the-language-of-the-future.html

## References

* https://www.codeproject.com/Articles/1204189/Handling-Concurrency-in-ASP-NET-Core-Web-API?msg=5431982
* https://www.codeproject.com/Articles/38042/Single-threaded-concurrency-model-design?msg=5155626
* https://www.codeproject.com/Articles/131990/Introduction-to-Parallelism-in-NET?msg=4919364
* https://www.mozilla.org/en-US/security/advisories/mfsa2006-59/
* http://www.oracle.com/technetwork/database/bi-datawarehousing/pres-best-practices-for-extreme-per-130805.pdf
* https://users.soe.ucsc.edu/~dph/mypubs/debugConcProg89.pdf
* https://en.wikipedia.org/wiki/Embarrassingly_parallel
* https://docs.microsoft.com/en-us/azure/architecture/patterns/sharding
* https://www.clustrix.com/bettersql/challenges-sharding-mysql/