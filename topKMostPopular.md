# Top K most popular
## Requirements
### Functional
1. Given a system(Google search/ youtube/stock brokarage etc.) , give the most popukar K items(searched/ viewed / traded respectively).
2. You will be asked to give the top K popular items in last 15 minutes/5 minutes etc as well as last 1 hr or last 24 hrs etc.
### Non functional
1. Performance should be good.
2. reliable
3. highly available.
4. 90% accuracy - immediate result
5. 99% accuracy - less performant is applicable.

### Questions to be asked
1. How the user will query. Is it always referenced as last 1 min/5 min/1 hr/ 5 hr etc. 
   or it can be range queries as well like 5pm to 7pm ?
2. What is the maximum amount of time the query will be asked for?
    like last 24 hr or last 1 year etc.
### Assmuptions
1. let say range queries are not supported. The queries will always be with respect to current time. eg. last 1 minute/last 3 hr / last year / last month etc.
### Scope
We will be desigining for the last few minutes and last few hours for now and make sure the design is extensible for the month and year requirements.

## Approaches
### Approach1
Maintain a hash map for all the items and increament their counter whenever it is searched.
Every minute write the hashmap state in DB, for the max K entries with max count.
Whenever query for last few minutes comes then we need to make a db call to get the top K for the exact number of minutes.
Eg: 
