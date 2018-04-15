http/2 is a major revision of http protocal since http 1.1. New protocal doesnot require changes to existing applicaiton, but new application can take advantage of new features and performance improvement. 

### Major difference from http 1.1
* http/2 allows server to "push" content to client
* perfornmance improvement
    1. using multiplexing of http request and response over same tcp connection to improve performance, this helps to avoid head-of-line blocking problem.
    2. header compression
    3. prioritization of requests