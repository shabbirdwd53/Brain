#linkedIn #prompt 


You are an expert copywriter specializing in social media, particularly Linkedin.

‍

Please turn the following article into a LinkedIn post showcasing the main points, using a step-by-step approach. The post should be actionable, non-fluff, approachable, and use simple vocabulary.

Use the below few LinkedPost for the reference to identify the way of tone and how to write a post.

1)
I always wondered how SQL databases executed the JOINs. Always knew the theory, but today I spent some time digging into MySQL's code to understand the nuances.  
  
Turns out, MySQL builds the best join plans incrementally to make sure it figures out the most optimal join order. It goes from single-table access paths to 2-table joins, then to 3-table joins, and so on. As an optimization, it prunes any subtrees that are guaranteed to result in suboptimal costs.  
  
Interestingly, I noticed traces of dynamic programming in action. MySQL caches intermediate results to avoid redundant cost computations as it builds up join plans.  
  
This is what I absolutely love about open source - if you have a question, you can just dive into the code and find the answer for yourself.  
  
If you're curious, start with the file sql_optimizer, and in that, you will find the function called - get_best_combination. More importantly, use your favorite LLM to understand the code; I did the same.  
  
I’ve linked the relevant part of the source code in the comments.


2)
I am never going to write a new db, so why study database internals?  
  
This is the most common argument I get when I encourage people to read database internals. I always say this, database is the most brittle component of your architecture and it makes or breaks your system. It determines  
  
- the performance of your system,  
- the peak your system will handle, and  
- how your system will react when there is a sudden spike  
  
You do whatever it takes to keep your database up and running. For example, you add a cache to reduce the load on the database and add replicas for analytical queries. Most outages happen because of a database outage, so it is critical to understand databases well.  
  
Understanding database internals, or at least having a rough idea helps you select the right tool for the right job. For example, a write-heavy use case should be naturally inclined toward an LSM-based database instead of a B-tree-based one.  
  
Never shy away from going deeper into things that you find amusing. be naturally curious about how things work, and you will fall in love with engineering.


3)
Classic exponential decay.  
  
Everyone starts, but very few make it to the end. The real difference is made not at the beginning, but when we actually finish the things we start like - the course, the book, the playlist.  
  
This snippet is from my Hash Table Internals series where I dissected the hash table and explained it all through and through.  
  
I went through 2 books, 4 papers, 13 articles, and 3 codebases to understand them end to end and if you are a curious engineer and love diving deep, you'll love it.  
  
Give it a watch, link in the comments.


4)
One of the best courses I took during my college years was called "Storage and Virtualization" and one of the assignments was to write our own file system.  
  
This one project taught me a ton of things and the best part? I had to do it without much access to the internet :) Going through a ton of books and struggling through documentation, helped me a lot to build a much deeper understanding of  
  
- how file systems work  
- inodes, blocks, and allocation strategies  
- handling concurrent access  
- block caching mechanisms  
- and to a very minor extent optimizations for read/write  
  
If you have some time, I would highly recommend you try to build your own fs. it is not as difficult as it sounds. To start with you can just use FUSE and that would do the trick.  
  
Computer science is so much fun. I can't understand how students these days don’t take these subjects seriously. But once you try it, you’ll fall in love with the entire domain.


5)
Some time back, in my live cohort, we were discussing BLOB vs TEXT, and while I was skimming MySQL documentation to brush up on some concepts, I stumbled upon something interesting.  
  
MySQL supports "generated columns" and you can provide an expression that will be used by MySQL to automatically create a new column (virtual or stored) and populate the value as per it.  
  
Two interesting use cases of generated columns can be  
  
1. A complicated condition can be created as a virtual generated column making it simpler for engineers to not type complex WHERE clause every time.  
  
2. Generated columns can be used as a materialized cache e.g. Hash of a subset of columns for quick lookups and saving you the effort of computing and inserting every time.  
  
The best part about this feature is that you cannot update the value of the column, which means no accidental edits to the data by humans or buggy code. Pretty cool.  
  
Link to read more about it in the comment.  
  
I keep writing and sharing content about engineering, career growth, and becoming a better engineer. The link to all my write-ups is in the comment below.

6)
I keep screaming, that you need both curiosity and a high bias for action to make an impact. But what does that really mean and why does it matter? Let's break it down combinatorially :)  
  
1. Neither Curiosity nor Bias for Action - Stagnation  
  
This is the absolute worst case. No curiosity means no learning. No action means no execution. This way, you stay stuck with no growth, no relevance, just fading into the background.  
  
2. Curiosity without Bias for Action - Analysis Paralysis  
  
Because you are curious, you will ask great questions, dive deep into concepts, and accumulate knowledge. But without action, it's all theoretical. Because you have been learning a lot, overthinking kicks in, procrastination follows, and nothing gets built.  
  
Many brilliant minds fall into this trap - they understand problems deeply but never take the steps to solve them. This also leads to frustration and you start to build a negative outlook towards life and others.  
  
3. Bias for Action without Curiosity - Thoughtless Execution  
  
You move fast but without questioning whether you're moving in the right direction or are taking the shorter path or not. That means inefficiencies, repeated mistakes, and wasted effort. You are effectively working hard, but not smart.  
  
4. Curiosity and a High Bias for Action - Impact  
  
This is where the magic happens. Curiosity helps you learn and innovate, while a high bias for action turns those insights into reality. You prototype, experiment, and iterate quickly.  
  
I've seen this firsthand - some of the best ideas I've had only became impactful because I acted on them sooner; and some of my biggest mistakes? Moving fast without questioning enough.  
  
The world doesn't reward just thinkers or just doers - it rewards those who learn fast and act faster.


Use the AIDA framework (Attention, Interest, Desire, Action) to structure the content. Use bullet points and emojis to enhance readability but avoid using hashtags. Remember to keep the content engaging and easy to follow.



Your tone should be:

-Actionable

-Catchy

-Non fluff

-simple vocabulary (a 6th grader should understand it)

‍

Article: {INSERT YOUR ARTICLE HERE}