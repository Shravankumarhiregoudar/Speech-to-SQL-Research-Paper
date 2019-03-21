# Speech-to-SQL

ABSTARCT

Recent developments in speech recognition system and natural language processing have given rise to a new generation of powerful voice-based interfaces. In this proposed system, user interacts with the system through a voice based user interface to fetch the desired results. To make the system smooth and interactive, the query is based on casual human speech/conversation. The spoken query undergoes many steps to arrive at the final results. It includes synonym table which is used to convert the spoken query into SQL keywords. This proposed work will give the good results for simple and complex queries. The accuracy of the system depends on the complexity of the database. This system will show that the voice based user interface is an effective means of querying and fetching data from the stored database.


INTRODUCTION

Speech recognition has become an essential part of a system with the fast growing technology. These interactive applications should be able to process the human communicating language queries. Natural Language Processing is the field of study that focuses on the interactions between human language and computers. It sits at the intersection of computer science, artificial intelligence, and computational. The spoken query undergoes many steps to arrive at the final results. It includes synonym table which is used to convert the spoken query into SQL keywords. This proposed work will give the results for simple and complex queries. The accuracy of the system depends on the complexity of the database. This system will show that the voice based user interface is an effective means of querying and fetching data from the stored database.


PROBLEM STATEMENT
The aim of the work is to provide a voice based system to fetch the data using synonym table. Speech to SQL query generator is a process by which the user query in natural language will be converted to a SQL query based on the speech query entered. Any person is not expected to know the SQL language, and hence the system would help in connecting to the backend database.


CONTRIBUTION
The contribution towards the work is adding synonym table which helps the user to speak in his/her own language and then converting it into the SQL key.


INTRODUCTION TO NLP

The field of study that focuses on the interactions between human language and computers is called Natural Language Processing, or NLP. It sits at the intersection of computer science, artificial intelligence, and computational.
Steps involved in the process,

Morphology
In this phase, the text is broken down into words called tokens- the smallest unit of a text. We seperate the given input query sentence in natural language into all the words it contains and store the words in a list. For example, if the given input query is ―get title of the course‖, then in this phase, each word of the sentence, i.e. get, title, of, the, course will be stored in a list like [ ‗get‗, ‗title‗, ‗of‗, ‗the‗, ‗course‗]

Lexical
At this level, humans and NLP systems, interpret the meaning of individual words. Each word of the tokenized sentence will be mapped with the meaning of the same word present in the data dictionary and database. For example, from the list generated in the morphology phase, the words will be mapped as ―get: select, ―title: title, ―course: course.

Syntactic
At this level at first we will be having all the attributes present in the query in lexical analyser. Each of them is mapped with the attributes in the dictionary which contains all the tables along with their attributes. And then we find the tables which contain the attributes of the given input query. For example, of the output generated in the previous phase, we derive the attributes in the query as ―title and which belongs to table ―course

Semantic
Semantics focuses on the study of meaning of the words present in the natural language query and the relation between signifiers like words, signs, phrases and what do they actually stand for. A field of semantics called Linguistic semantics deals with the study of meaning which interprets human expression through language. This level deals with checking the different conditions like where clause, relational operators, aggregate functions, natural join and build the SQL query accordingly. The final SQL query after checking all the conditions is ―select title from course.


PROPOSED METHOD

The proposed model is composed of two modules those are Query intent and refine intent, which allows user to communicate with the system. The primary module that is typically used whenever a user starts a new conversation with our system is the query module. The input for this module is called a query request. 
The Query Intent is the primary intent that is typically used whenever a user starts a new conversation with our system. The input for this intent is called a query request. Basic Query Requests: In its current version, this system supports simple non-aggregation and aggregation query requests using one of the aggregation types (COUNT, SUM, AVG, MAX and MIN). 
In the current version of this system, basic query request can only contain one result column but allows multiple where clauses, and also multiple group-by columns. It is more convenient to the user when using a voice-based interface where results are displayed on the screen based on the speech request. The most basic query request is of the following form: Get the {column}(s) of {table}(s)? What is the {aggregation} {column}(s) of {table}(s) ? Here {column}(s) {table}(s) are elements of the database schema, while {aggregation} refers to one of the spoken variants of the standard aggregation functions; i.e., ‖total", ―average", ―minimum", and "maximum", In the following, we consider how where and group-by clauses can be formulated in a query request. Multiple where Clauses: Where clauses can be added to a basic query request by appending:

where {table}(s) {column}(s) {Comparator}{value}? Here {column}(s) and {table}(s) refer to elements of the database schema, while {Comparator} and {value} refer to the comparison operator ―is", ―is equal to", ―is greater than‖, ―is less than", etc., and the value to compare the column against, respectively. When referring to a column the {table}(s) phrase is optional in all query requests. For example, two equivalent query requests that use a simple where clause is: Get title of course with student whose name is Shravan? In the system, multiple where clauses are also supported. Inner join operation takes place. The primary and foreign keys are compared to remove the redundant bits and correct result is being obtained Having Clauses: Having clauses can be added to a query with the comparator operators and multiple tables are involved in the operation. For example, Get name of student having course credits greater than 3. Like Clauses: Like clauses are also implemented. For example; Get title of course where teacher is like Hegde. The main features of the voice-based interface of EchoQuery are: 
1. Hands-free Access: This system only requires the user to press a button or start an application using a gesture or a mouse-click. Then, users can interact with the database by solely using their voice at any time. 
2. Dialogue-based Querying: While traditional database systems provide a one-shot (i.e., stateless) query interface, natural language conversations are incremental (i.e., stateful) in nature. To that end, this provides a stateful dialogue-based query interface between the user and the database where (1) users can start a conversation with an initial query and refine that query incrementally over time, and (2) System can seek for clarification if the query is incomplete or has some ambiguities that need to be resolved.
3. Personalizable Vocabulary: Domain experts often use their own terms to formulate queries, which might be different from the schema elements (i.e., table and column names) of a database. Learning the terminology of a user and its translation to the underlying schema is similar to the problem of constructing a schema mapping in data integration. This system constructs these mappings incrementally on a per-user basis by issuing clarification questions using its dialogue-based query interface.


The Algorithm is as follows,
Step 1. Accept the input from the user in the form of speech.
Step 2. The speech is converted into text by using speech recognition engine.
Step 3. The correct form of the statement is saved and other statements are discarded.
Step 4. Divide the input query and store it in a list, i.e. tokenising the input query statement.
Step 5. Remove the unnecessary token from the list like, the, an, etc.
Step 6. Map the tokens with the table name and attributes of the database.
Step 7. Now find the tables which will contain the pair of ((attribute which do not belong to the table in the query), (other attributes present in the table in the query)).
Step 8. For a natural join, find out the common attribute and form the inner query. Then form the outer query according to the different conditions. Merge both of them and generate the final query.
Step 9. For a simple query, generate the final query by checking the all conditions.
Step 10. Obtain the conditions of the where clause and other clause such as comparators, aggregate function and relational operators, add these to the final query.
Step 11. Print the final query on command prompt and display results on UI.


CONCLUSION AND FUTURE WORK

In our method we have used the voice based interface to help all kind of users and allow them to access data. User doesn't need to know the detailed structure of database; we find tables with the help of attributes specified in the query. System has been checked for single tables and multiple tables and it gives correct result if the input speech query is correctly pronounced and the attributes are mapped with the database. System is also database independent i.e. it can be configured automatically for different databases. Areas of improvement can be working on improving the grammar in order to ensure that even the more general query is being executed. Further we can work on DML like insertion, deletion of tables and attributes and DDL like create, alter of tables.
