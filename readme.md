
 Storage
 - SQL - tables rows.
 - NoSQL - kv, documents, collections

 Schema
 - SQL - fixed, columns decided, modify, then you need alter the database.
 - NoSQL- dynamic

 Scalability
 - SQL- highly vertically scalable, harder to scale RDBMS across multiple servers.
 - NoSQL - horizontally scalable ( sharding ),

Reliability - ACID ( atomicity, consistency, isolation, durability)
- SQL -> ACID compliant.
- NoSQL => within document -> Atomic, ACID, performance, and scalability

SQL - ACID compliance structured and unchanging.

NoSQL - large amounts of data, horizontal distribution rapid dev.


Develop the application Define our data model improve the two steps:-
- Understand business requirements
Expected scenarios what stats, information

workload

- No of users on your system -> ERD ( Entity Relation Diagram) collection relation diagram
- No of reads
- No of writes
- No of queries

operations,
ranked by priority

{
    username ->  tweet_id
                 tweet-name
                 author-id
                 likes
    email
}


Relationships:
 - one to one
 - one to many
 - many to many

one and only one,
Zero or one,
Zero or Many,
One to a Zillion,
One to a 1000,
One to a million


One to One:

User
 - id
 - address
 - email
   address:{

   }

Orders
 - id
 - content
 - items

 - user_id
 - user_address:{
                (duplication)
 }


One to Many:

 array of refs/ links

 User:{
     id
     name
     email
     blogs:[ blog_id1, blog_id2, blog_id3, blog_id4 ]
 }

 Document basis
  blogs
   - user_id


Many to Many:

 Arrays on both documents
     
     Article
     categories: [1,2]


     categories:{
         article: []
     }


     Movie 
     casts: [] 1,20,53


     Cast:{
         name
          movies: [1,3,15]
     }


- How are the queries being made?
- How many times do the information (the embedded info, ) get queried

- When you query, are you using the embedded information?

- Does the embedded information change a lot?

Duplication
Staleness


 { - Evaluate and understand your application workload
- entities and relationship
- patterns }  => collections, indexing, sizes, Contraints


Twitter

Users: 
 - post tweets
 - follow other users
 - like / favorite tweets

 - retweet
 - trending topics
 - notifications
 - suggestions
 - search for a tweet
 - tag users
 - hashtags


Load 

- 200 million daily active users

Read:
 - 200 M * 100 tweets : 20 Billion per day

Write: 
- text: 400 M * 340 bytes per tweet => 130 GB daily

 - 100m x 300kb = 35GB


 per second
 - read  300k per second
 - write 5000-6000 per second


 simplicity, performance