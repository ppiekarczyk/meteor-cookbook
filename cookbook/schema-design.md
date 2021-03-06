## Schema Design 
**Q:  How should I go about designing my collections?**  

Well, instead of telling you what you ought to do; how about I tell you how I go about designing *my* collection schemas.  I've been working with Mongo for a couple years now, and document oriented database for maybe 8 years now.  There are few rules I use nowdays when designing data storage collections:

1.  Don't do data modeling in the collection schemas.  
2.  Do a careful analysis of the most commonly used queries in your application instead.   
3.  Collection schemas should be designed for optimizing server/client communications.  
4.  Therefore, collections should reflect the types of queries the application is going to perform.  
5.  If its not worth storing a billion records, odds are that it doesn't actually need to be a collection.  
6.  Collections with records containing only 2 or 3 fields are suspicious in the Mongo world.  
7.  As are collections with only a dozen records.  
8.  The exception are collections that contain unique configuration information, such as clients or stores.
9.  If a table is so small it can be converted into an enum, do so.    
10.  Consolidate and merge tables when possible.  
11.  Think in terms of document schemas, rather than table schemas.  
12.  Collections schemas should be about performance.  
13.  Document schemas are where you want to do your data modeling.  


####Naming Fields  
1.  Use camelCase or snake_case.  
2.  Don't use dot notation in your field names!  
3.  SmallTalk style type suffixes can be quite useful.  
4.  But don't go overboard with Hungarian notation prefixes.

````js
  // this naming convention works well
  user_d  
  user_key  
  user_tag
  
  // as does this
  userId  
  userKey  
  userTag
````

