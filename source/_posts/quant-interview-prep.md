---
title: Quant Finance Interview Resources
date: 2022-07-30 15:42:02
tags:
  - statistics
  - leetcode
  - interview
---

# Quant Interview Resources

We are going to go through how to prepare for quant finance interview in three sections:

- the behavioral interview
- the coding interview
- the probability + statistics interview

and I am going to highlight some resources I've used along the way.

## Behavioral

### Strategy

Normally, the bahavioral interview is conducted by the HR or the hiring manager. This is going to be your first round of interviews. To do well, make sure you know how to:

- deliver a brief and concise self introduction in a minute
- give an overview on every item on your resume in the "STAR" format
- dive into any of these projects
- hightlight the things on your resume that show your potential and achievements

Also, sometimes interviewers like to challenge you to see how you react under pressure. Be confident, and know when to hold your grounds! The behavioral interview is not an easy process. It will take a lot of practice to appear confident and convincing.

I've found the following (paid) resource to be very useful for me when I was preparing for the behavioral interview. If you are a student, you can get 6-month free by using Github Student:

### Resources

- 4/5: [Educative: Grokking the behavioral interview](https://www.educative.io/courses/grokking-the-behavioral-interview)
  This course provides a lot of great tips from the interviewer's perspective, and gives a great list of questions to prepare answers for. Even though I just skimmed through it, I feel like I have learned a thing or two from it. If you are more experienced at interviewing, you may not need it.

## Coding

### Strategy

If you've not done a coding interview before, this can be intimidating. There are primarily two types of coding interview: a take home exam/online assessment, or a live session with your interviewer.

For the live session, I'd focus on my communication while I am solving the problem. People tend to say some times hearing you communicate can be more important than your solution. It gives your interviewer an idea about what it is going to be like to work with you.

- When you begin, spend some time to go through the question with your interviewer. Ask clarifying question. The questions can be regarding the main task itself, or you can also ask about edge cases.
- Once you have a good understanding of the questions, think about the programming patterns you've seen before. Is it a two-pointer problem, a binary search, a dynamic programming, or a DFS porblem? Propose the route you are going to take, and get some hint from the interviewer's response. This will help you staying on the right track.
- The next period can be a little quite. Spend 10 - 15mins on write the actual algorithm. Put comments along the way, keep your code organized, and name your variables wisely. If you are able to compile your program, also write a couple of test cases to show that your function is working.
- Once you are done, let the interviewer know, and you guys can go through your solution together. Walk through your code, explain what each section is doing, and discuss the test cases.
- Ask whether the interviewer wants to go ahead with optimizing the code. You can then optimize along both time and space complexity.

### Resources

There are several resources I've found useful:

- (5/5) [Educative: Grokking the coding interview](https://www.educative.io/courses/grokking-the-coding-interview)
  This course trains you on 16 common patterns you are going to use during interviews. It provided me with many common "templates" that I can use during coding interviews. Personally, I find having these templates very convenient, as you can stop wasting time on coming up with variable names, or the correct range for your for loop.
- (4/5) [Leetcode Patterns](https://seanprashad.com/leetcode-patterns/)
  This is a list of leetcode questions organized by common patterns. There are a total of 171 is questions. This can be a good complement to the Educative course, but as this is a collection of different leetcode questions, just from the solutions themselves it is hard to come up with "templates".
- (4/5) [Cracking the Coding Interview](https://amzn.to/3PIpFLg)
  This is a classic book for coding interview prep. It begins with interview tips, the big O notation, and then have different types of problems by chapters. You can find leetcode question lists for questions in the book. I took away one point because it is not as interactive as the online solutions.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=0984782850&asins=0984782850&linkId=920925119dc06fe13a713eb6cf4f60a6&show_border=true&link_opens_in_new_window=true"></iframe>

- (?/5) [Elements of Programming Interviews](https://amzn.to/3JhwwJ7)
  I have not personally read this book, but I have seen people recommending it.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1537713949&asins=1537713949&linkId=997fe87ce764835c859ef5b0240adb1d&show_border=true&link_opens_in_new_window=true"></iframe>

In additional to the above resources, if you are interviewing for a more senior role in quant development, you can expect system design questions. There are a couple of resources you can use:

- (5/5) System Design Interview I and II by Alex Xu
  Alex Xu has published two book on system design interviews, and both books are extremely fun to read, even if you are not interviewing. The first book covered more basic patterns, like sharding, API throttler, while the second book went through design of real life applications (e.g. location based recommendation system).

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=B08B3FWYBX&asins=B08B3FWYBX&linkId=8ddbefde194d22475f45778ae2989a05&show_border=true&link_opens_in_new_window=true"></iframe>
  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1736049119&asins=1736049119&linkId=e71b04e8fc722342116a9f19a710f919&show_border=true&link_opens_in_new_window=true"></iframe>

- (5/5) [Designing Data-Intensive Applications](https://amzn.to/3oEMbJd)
  This book is not directly marketed as a book for interview preparataion. However, if you are a data engineer/machine learning engineer, this book solidifies a lot of principals in designing data-intensive applications. It was extremely fun to read, and I have learned a lot from it.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1449373321&asins=1449373321&linkId=18d0dc7e2fc09576b109b46e46a1c8bc&show_border=true&link_opens_in_new_window=true"></iframe>

- (?/5) [Educative: Grokking the system design interview](https://www.educative.io/courses/grokking-the-system-design-interview)
  Once again, Educative has a course on this topic! I have not personally taken it, but I think pretty much everyone I've talked to recommended it.

## Statistics

Statistics is one of the more traditional topics in quant finance interviews. It has been around for a long time, and if you are interviewing for a quant researcher role, there is a very high likelihood you'll be given at least one technical on it.

Answering a probability/statistics question shares a lot of the same pattern as answering a coding interview question. You have to seen enough questions to be able to recognize patterns in statistics interview.

### Resources

- (5/5) [Ace the Data Science Interview](https://amzn.to/3ONSi8q)
  This is a relatively new book, and is not marketed directly towards quant finance. However, the questions in it appears to come from hedge funds like Citadel, 2 Sigma, along big tech companies. Therefore, it is a very good resource for prepping the quant interview. Chapter 5 Probability, Chapter 6 Statistics, and Chapter 7 Machine Learning are especially useful.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=0578973839&asins=0578973839&linkId=120be56990d168aa6c8952c2e6ffa5e1&show_border=true&link_opens_in_new_window=true"></iframe>

- (5/5) [A Practical Guide To Quantitative Finance Interviews](https://amzn.to/3zJO39H)
  This book is a classic, period. Known as the "green book", it has been around for a long time. Most people in the industry has used it at one point, and I am still seeing a lot of the questions in it getting asked during interviews. If you can only buy one book, get this one.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1438236662&asins=1438236662&linkId=0cb18b7f0a64f0c8f908da99c7b301dd&show_border=true&link_opens_in_new_window=true"></iframe>

- (4/5) [Heard on The Street](https://amzn.to/3zm9tZ4)
  This is another classic, the "red book". The author is a fun guy, and kept many anectodes in the book. One of the first story is: One candidate for a futures trading position in Chicago was asked: "Would you rather be beaten up, beat someone up, or run around the block naked?" The last respond did not get him the job. The book has more weight on brainteasers than other books.

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1991155417&asins=1991155417&linkId=7c57933943f1e263c5fdb6fa05367e4f&show_border=true&link_opens_in_new_window=true"></iframe>

- (?/5) There are several books that I find interesting, but haven't read them yet:

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=097975769X&asins=097975769X&linkId=cb263c0bf74c5e40ffee06198e3165a2&show_border=true&link_opens_in_new_window=true"></iframe>

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1734531223&asins=1734531223&linkId=72c367421469e915ce05f98eae5db6cd&show_border=true&link_opens_in_new_window=true"></iframe>

  <iframe sandbox="allow-popups allow-scripts allow-modals allow-forms allow-same-origin" style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=shawnlinxl-20&language=en_US&marketplace=amazon&region=US&placement=1801817472&asins=1801817472&linkId=ad1420c204b86ea28f088d65a65a2d98&show_border=true&link_opens_in_new_window=true"></iframe>
