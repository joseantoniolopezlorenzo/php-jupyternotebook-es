Andrew Beak

PHP 7 Zend Certification Study GuideAce the ZCE 2017-PHP Exam

Andrew Beak

Grafham, Cambridgeshire, UK

​Any source code or other supplementary material referenced  by the author in this book is available to readers on GitHub via the  book's product page, located at[ www.apress.com/978-1-4842-3245-3 ](http://www.apress.com/978-1-4842-3245-3). For more detailed information, please visit[ http://www.apress.com/source-code ](http://www.apress.com/source-code).          

​					ISBN 978-1-4842-3245-3e-ISBN 978-1-4842-3246-0

https://doi.org/10.1007/978-1-4842-3246-0

Library of Congress Control Number: 2017960936

© Andrew Beak 2017

This work is subject to copyright. All rights are reserved by the Publisher, whether the whole or part of the material is concerned, specifically  the rights of translation, reprinting, reuse of illustrations,  recitation, broadcasting, reproduction on microfilms or in any other  physical way, and transmission or information storage and retrieval,  electronic adaptation, computer software, or by similar or dissimilar  methodology now known or hereafter developed.

Trademarked names, logos, and images may appear in this book. Rather than use a  trademark symbol with every occurrence of a trademarked name, logo, or  image we use the names, logos, and images only in an editorial fashion  and to the benefit of the trademark owner, with no intention of  infringement of the trademark. The use in this publication of trade  names, trademarks, service marks, and similar terms, even if they are  not identified as such, is not to be taken as an expression of opinion  as to whether or not they are subject to proprietary rights.

While the advice and information in this book are believed to be true and  accurate at the date of publication, neither the authors nor the editors nor the publisher can accept any legal responsibility for any errors or omissions that may be made. The publisher makes no warranty, express or implied, with respect to the material contained herein.

Printed on acid-free paper

Distributed to the book trade worldwide by Springer Science+Business Media New  York, 233 Spring Street, 6th Floor, New York, NY 10013. Phone  1-800-SPRINGER, fax (201) 348-4505, e-mail orders-ny@springer-sbm.com,  or visit www.springeronline.com. Apress Media, LLC is a California LLC  and the sole member (owner) is Springer Science + Business Media Finance Inc (SSBM Finance Inc). SSBM Finance Inc is a Delaware corporation.

​For Duckems, Beastly, and Bratface          

​for whom I’d change the world if I had the source code          

# Introduction

​Welcome to what I hope is an accessible reference that  helps you quickly find and learn relevant facts about the PHP language.  I’m writing it with the following readers in mind:

- Intermediate PHP programmers with two or three years of experience who are hoping to sit for the Zend 2017 certification exams in the PHP 7.1 language.
- Programmers who are proficient in another language but want a quick reference book to dive into PHP.

This  book is specifically not an introduction to programming and no attempt  is made to introduce basic topics such as what a variable is. It is  purely a reference to learn the idiosyncrasies of PHP and serve as a  guide toward certifying.

Additionally, it does not intend to replace the PHP manual but rather to focus the  reader’s attention on aspects of PHP relevant to the Zend certification  exams. To that end, I make liberal use of footnotes linking to manual  pages and other reference pages.

​This guide cannot possibly cover the full depth of the PHP manual,[1](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-178)and you cannot consider yourself prepared until you have  worked through the manual pages. It is essential to follow the footnote  links, read the page, and even follow some links through the PHP manual  related to the topic.

This  book focuses on PHP 7.1 and in order to keep focused on the exam  syllabus does not attempt to exhaustively explain what features are  available in which version of PHP. You can assume that if a feature is  referenced in this book then it is available in PHP 7.1.

You won’t need to know when a feature was introduced into PHP, but you will need to know what features are deprecated in PHP 7.1. I've tried to  keep that in mind when giving information about the availability of a  feature.

Wherever possible, I'll flag where something has changed from PHP 5.6, especially where it is not backward compatible.

This book tries to avoid having an opinion about coding standards such as  PSR2, but it is strongly recommended that a practicing developer learn  these in parallel. You won’t be asked about them on the exam and so I  won't teach them here.

Some paragraphs in this book are marked up with symbols, as explained next.


## The Zend Certification Syllabus

Zend certification is one of the few industry certifications that is widely  recognized as an established benchmark for proficiency in PHP. Part of  why this certification is so well respected is that it is not easy to  attain. To pass your exam, you need to have an in-depth knowledge of a  wide area of topics in PHP programming.

This book aims to highlight the topics that are important in the  certification examination. I’ve included a bunch of quizzes that test  the topics, and if you notice any gaps in your knowledge, you should  make sure to go carefully through the relevant sections in the manual.

The actual exam consists of about 70 questions drawn from a pool. Questions will vary in difficulty and will sometimes require you to apply the  principles from more than one area of the syllabus to solve them.

There are ten topics covered in the examination. Zend places varying amount  of importance to the topics in the exam. You can find a list of exam  topics on the Zend web site.

​You’ll notice that this guide has a chapter for each of the topics in the list:

| Very Important      | Average Importance | Lower Importance      |
| ------------------- | ------------------ | --------------------- |
| PHP basics          | Functions          | Databases and SQL     |
| Object-Oriented PHP | Web Features       | Data Format and Types |
| Security| Strings| Input-Output          |
|     | Arrays |       |
|     | Error Handling     |       |

The  sections on PHP basics, object-oriented programming, and security are  regarded as being the most important and are given the most weight in  the exam.

There are a lot of tricky questions in the PHP Basics section, so don’t be fooled  by the inclusion of the word “basics” in the topic title. It’s one of  the three most important topics in the exam syllabus, so don’t skimp on  the time you spend finding the gaps in your knowledge.

The sections on databases, data formats and types, and input-output are  considered less important. You’ll still need to know them, however, as  exam questions will often rely on a broad knowledge of PHP and may  require you to apply knowledge from different topics.

The exam has a mixture of multiple choice and free text questions. You’ll  be required to code short snippets to answer some questions.

Although you won’t be required to have an encyclopedic knowledge of the PHP  manual, you will be asked questions about function parameters, what  function to use in a particular situation, common classes, exceptions,  and other elements of PHP.

​Unless they note otherwise, all questions assume that  you are working with PHP 7.1 that has been configured with the  recommended settings. You can assume that error display is set on and  that error reporting is set toE_ALL.

You  can mark questions for review and come back to them later. Don't spend  more time than is allocated to a question; That just makes the following questions more difficult because you have less time!

Finally, there is no negative marking in the exam. You won’t be penalized for an incorrect answer, so taking a guess works in your favor.

Contents

​[Chapter 1: PHP Basics](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-137)

​[Introduction](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-179)

​[Basic Language Features](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-180)

​[Inserting PHP into Web Pages](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-181)

​[Language Constructs](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-182)

​[Comments](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-183)

​[Representing Numbers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-184)

​[Variables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-185)

​  [Variable Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-186)

​  [Naming Variables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-187)

​  [Checking If a Variable Has Been Set](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-188)

​[Constants](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-189)

​[Superglobals](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-190)

​[Magic Constants](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-191)

​[Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-192)

​  [Arithmetic](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-193)

​  [Logic Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-194)

​  [Ternary Operator](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-195)

​  [Null Coalescing Operator](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-196)

​  [Spaceship](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-197)

​  [Bitwise](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-198)

​  [Bit Shifting](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-199)

​  [Bitwise NOT](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-200)

​  [Assignment Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-201)

​  [Reference Operator](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-202)

​  [Comparison Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-203)

​  [Two More Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-204)

​[Control Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-205)

​  [Conditional Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-206)

​  [Loops](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-207)

​  [Breaking Out of Loops](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-208)

​  [Namespaces](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-209)

​  [Fully Qualified Namespace Names](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-210)

​[Configuration](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-211)

​  [Where Settings May Be Set or Changed](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-212)

​  [Php.ini](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-213)

​  [User INI Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-214)

​  [Apache Version of INI Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-215)

​[Performance](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-216)

​  [Memory Management](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-217)

​  [Symbols Are Pointed to zval Containers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-218)

​  [Arrays and Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-219)

​  [Memory Leaks in Arrays and Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-220)

​  [Garbage Collection](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-221)

​  [The Opcode Cache](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-222)

​  [Extensions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-223)

​[Chapter 2: Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-91)

​[Arguments](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-224)

​  [Argument Type Declarations](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-225)

​  [Optional Arguments](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-226)

​  [Overloading Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-227)

​  [Variadics](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-228)

​[References](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-229)

​[Variable Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-230)

​[Returns](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-231)

​  [Return Type Declarations](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-232)

​  [Return Void](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-233)

​  [Return by Reference](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-234)

​[Variable Scope in Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-235)

​[Lambda and Closure](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-236)

​  [Early and Late Binding](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-237)

​  [Binding Closures to Scopes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-238)

​  [Self-Executing Closures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-239)

​[Callables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-240)

​[Chapter 3: Strings and Patterns](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-134)

​[Declaring Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-241)

​  [Embedding Variables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-242)

​  [Control Characters](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-243)

​  [Heredoc and Nowdoc](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-244)

​[Referencing Characters in Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-245)

​[PHP and Multibyte Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-246)

​  [Unicode](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-247)

​  [Telling Clients How a String Is Encoded](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-248)

​  [Changing Between Encoding Schemes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-249)

​  [Practical Example](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-250)

​  [Matching Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-251)

​[Extracting Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-252)

​[Searching Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-253)

​  [Useful Tips](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-254)

​  [Quick Overview of Search Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-255)

​  [Replacing Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-256)

​[Formatting Strings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-257)

​[Formatting Numbers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-258)

​[String Patterns: Regular Expressions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-259)

​  [Delimiters](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-260)

​  [Meta-Characters](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-261)

​  [Generic Character Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-262)

​  [Boundaries](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-263)

​  [Character Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-264)

​  [Matching More Than Once](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-265)

​  [Capturing Groups](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-266)

​  [Greed and Laziness](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-267)

​  [Getting All Matches](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-268)

​  [Naming Groups](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-269)

​  [Pattern Modifiers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-270)

​[Chapter 4: Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-48)

​[Declaring and Referencing Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-271)

​[Functions That Create an Array](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-272)

​[Array Operators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-273)

​[Properties of PHP Array Keys](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-274)

​  [Filling Up Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-275)

​  [Push, Pop, Shift, and Unshift (Oh My!)](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-276)

​[Comparing Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-277)

​  [array_diff()](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-278)

​  [array_intersect()](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-279)

​  [User-Defined Matching Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-280)

​  [Quick List of Comparison Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-281)

​[Combining Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-282)

​[Splitting Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-283)

​[Destructuring Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-284)

​[Calculating with Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-285)

​[Iterating Through Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-286)

​  [Looping Through Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-287)

​  [Using Array Cursors](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-288)

​  [Walking Through Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-289)

​[Sorting Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-290)

​  [Natural Order Sorting](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-291)

​[Standard PHP Library (SPL): ArrayObject Class](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-292)

​[Chapter 5: Object-Oriented PHP](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-156)

​[Declaring Classes and Instantiating Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-293)

​[Autoloading Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-294)

​[Visibility or Access Modifiers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-295)

​[Instance Properties and Methods](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-296)

​  [Properties](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-297)

​  [Methods](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-298)

​[Static Methods and Properties](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-299)

​  [Static Properties](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-300)

​[Working with Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-301)

​  [Copying Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-302)

​  [Serializing Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-303)

​  [Casting Between Arrays and Objects](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-304)

​  [Casting Objects to String](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-305)

​  [Class Aliases](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-306)

​[Constructors and Destructors](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-307)

​  [Constructor Precedence](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-308)

​  [Constructor Parameters](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-309)

​[Inheritance](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-310)

​  [The final Keyword](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-311)

​  [Overriding](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-312)

​[Interfaces](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-313)

​[Abstract Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-314)

​[Anonymous Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-315)

​[Reflection](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-316)

​[Type Hinting](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-317)

​[Class Constants](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-318)

​[Late Static Binding](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-319)

​  [Forwarding calls](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-320)

​[Magic (__*) Methods](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-321)

​  [__get and __set](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-322)

​  [__isset and __unset](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-323)

​  [__call and __callStatic](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-324)

​  [__invoke](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-325)

​  [__debugInfo](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-326)

​  [More Magic Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-327)

​[Standard PHP Library (SPL)](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-328)

​  [Data Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-329)

​  [Iterators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-330)

​  [Exceptions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-331)

​  [File Handling](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-332)

​  [ArrayObject](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-333)

​  [Observer Pattern](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-334)

​[Generators](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-335)

​  [Yield Keyword](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-336)

​  [Yielding with Keys](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-337)

​  [Yielding NULL](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-338)

​  [Yielding by Reference](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-339)

​  [Returning from a Generator](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-340)

​  [Generator Delegation](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-341)

​[Traits](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-342)

​  [Declaring and Using Traits](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-343)

​  [Namespacing Traits](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-344)

​  [Inheritance and Precedence](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-345)

​  [Conflict Resolution](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-346)

​  [Visibility](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-347)

​[Chapter 6: Security](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-11)

​[Configuration](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-348)

​  [Errors and Warnings](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-349)

​  [Disabling Functions and Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-350)

​  [PHP as an Apache Module](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-351)

​  [PHP as a CGI Binary](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-352)

​  [Running PHP-FPM](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-353)

​[Session Security](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-354)

​  [Session Hijacking](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-355)

​  [Session Fixation](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-356)

​  [Improving Session Security](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-357)

​[Cross-Site Scripting](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-358)

​  [Mitigating XSS Attacks](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-359)

​[Cross-Site Request Forgeries](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-360)

​[SQL Injection](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-361)

​  [Prepared Statements](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-362)

​  [Escaping](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-363)

​  [General Principles](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-364)

​[Remote Code Injection](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-365)

​  [Functions That Evaluate Strings as Code](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-366)

​  [Gaming include and require](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-367)

​[Email Injection](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-368)

​[Filter Input](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-369)

​[Escape Output](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-370)

​  [Avoid Log Poisoning](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-371)

​[Encryption and Hashing Algorithms](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-372)

​  [Encryption in PHP](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-373)

​  [Hash Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-374)

​  [Secure Random Strings and Integers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-375)

​  [Salting Passwords](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-376)

​  [Checking a Password](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-377)

​  [A Quick Note on Error Messages](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-378)

​[File Uploads](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-379)

​[Database Storage](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-380)

​[Avoid Publishing Your Password Online](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-381)

​[Chapter 7: Data Formats and Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-0)

​[XML](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-382)

​  [The Basics of XML](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-383)

​  [Well-Formed and Valid](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-384)

​  [XML Processing Instructions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-385)

​  [XML Transformations with PHP XSL](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-386)

​  [Parsing XML in PHP](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-387)

​  [DOM](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-388)

​  [SimpleXML](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-389)

​[SOAP](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-390)

​  [What SOAP Does](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-391)

​  [Using a SOAP Service](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-392)

​  [Offering a SOAP Service](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-393)

​[REST Web Services](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-394)

​  [Application and Resource States](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-395)

​  [REST Verbs](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-396)

​  [HATEOAS](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-397)

​  [Request Headers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-398)

​  [Response Headers and Codes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-399)

​  [Sending Requests](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-400)

​[JSON](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-401)

​[Date and Time](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-402)

​  [Formatting Dates](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-403)

​  [Date Calculations](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-404)

​  [Manual Date Calculations](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-405)

​  [Comparing Dates](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-406)

​[PHP SPL Data Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-407)

​  [Interfaces Related to Data Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-408)

​  [Lists](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-409)

​  [Heaps](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-410)

​  [Arrays](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-411)

​  [Maps](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-412)

​  [Summary of SPL Data Structures](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-413)

​[Chapter 8: Input-Output](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-169)

​[Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-414)

​  [Opening Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-415)

​  [File Modes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-416)

​  [File Mode Flags](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-417)

​  [Reading Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-418)

​  [Writing to Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-419)

​[File System Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-420)

​  [Directories](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-421)

​  [File Information](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-422)

​  [Managing Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-423)

​  [Determining the Type of a File System Object](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-424)

​  [Magic File Constants](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-425)

​[Streams](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-426)

​  [Stream Wrappers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-427)

​  [Filters](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-428)

​  [Stream Contexts](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-429)

​[Chapter 9: Web Features](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-101)

​[Request Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-430)

​[Request Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-431)

​  [The Request Superglobal](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-432)

​  [POST](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-433)

​  [GET](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-434)

​  [PUT](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-435)

​[Sessions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-436)

​  [Starting a Session](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-437)

​  [Session Identifier and Session Variables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-438)

​  [Ending a Session](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-439)

​  [Session Handlers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-440)

​[File Uploads](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-441)

​  [Limiting the Size of Uploads](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-442)

​  [Temporary Files](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-443)

​[Forms](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-444)

​  [Form Elements](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-445)

​  [Arrays in HTML Forms](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-446)

​  [Selecting Multiple Items from a List](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-447)

​[Cookies](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-448)

​  [Setting Cookies](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-449)

​  [Retrieving Cookies](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-450)

​[HTTP Headers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-451)

​  [Sending Headers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-452)

​  [Tracking Headers](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-453)

​[HTTP Authentication](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-454)

​[HTTP Status Codes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-455)

​[Output Control Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-456)

​[Chapter 10: Databases and SQL](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-41)

​[Database Basics](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-457)

​  [Keys](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-458)

​  [Indexes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-459)

​  [Relationships](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-460)

​  [SQL Data Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-461)

​  [Numeric Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-462)

​  [Character Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-463)

​[Working with SQL](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-464)

​  [Creating a Database and Table](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-465)

​  [Dropping Database and Tables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-466)

​  [Retrieving Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-467)

​  [Inserting New Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-468)

​  [Updating Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-469)

​  [Aggregating Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-470)

​  [Grouping Data](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-471)

​[Joins](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-472)

​  [Join Types](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-473)

​[Prepared Statements](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-474)

​[Transactions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-475)

​[PHP Data Object (PDO)](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-476)

​  [Connecting to PDO](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-477)

​  [Transactions in PDO](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-478)

​  [Fetching PDO Results](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-479)

​  [Prepared Statements in PDO](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-480)

​  [Repeated Calls to PDO Prepared Statements](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-481)

​[Chapter 11: Error Handling](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-97)

​[Throwables](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-482)

​  [The Throwable Interface](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-483)

​[Errors](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-484)

​  [Error Constants](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-485)

​  [Using an Error-Handler Function](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-486)

​  [Displaying or Suppressing Non-Fatal Error Messages](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-487)

​  [Error-Handling Functions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-488)

​[Exceptions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-489)

​  [Extending Exception Classes](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-490)

​  [The Exception Hierarchy](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-491)

​[Handling Exceptions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-492)

​  [Catching Exceptions](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-493)

​  [The finally Block](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-494)

​  [Setting the Default Exception Handler](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-495)

​[Chapter 12: Exercises](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-176)

Appendix: Quiz Answers

Chapter 1: PHP Basics

Chapter 2: Functions

Chapter 3: Strings and Patterns

Chapter 4: Arrays

Chapter 5: Object-Oriented PHP

Chapter 6: Security

Chapter 7: Data Structures

Chapter 8: Input-Output

Chapter 9: Web Features

Chapter 10: Databases and SQL

Chapter 11: Error Handling

Chapter 12: Exercises

Index

About the Author and About the Technical Reviewer

About the Author

Andrew Beak

is a software architect responsible for the cloud platform of an Internet  television company. He is a ZCE and has over six years of professional  experience working in PHP. He has been the technical lead for teams in  South Africa and the United Kingdom. His enjoyment for writing coupled  with his interest in empowering staff inspired him to write this book.  He has also written a book on scaling PHP and published a series of  video courses focused on the Zend examinations.


About the Technical Reviewer

Nico Loubser

is the lead software developer and team lead in a company that specializes in the payment industry, with a degree in information systems. He has  been working in PHP since PHP 3.8, as well as working in numerous  industries, and is a serious PHP 7 enthusiast.


Footnotes

[1](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-496)

​  [       https://php.net/     ](https://php.net/)


© Andrew Beak 2017

Andrew BeakPHP 7 Zend Certification Study Guide[https://doi.org/10.1007/978-1-4842-3246-0_1](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-137)

