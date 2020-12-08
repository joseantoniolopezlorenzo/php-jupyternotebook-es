# 1. PHP Basics

## Introduction

This chapter focuses on the nitty gritty details of PHP as a language. This  is a big chapter and it covers one of the most important aspects of the  exam. The best advice that I can give is not to skim over it. There are a lot of places where PHP has some peculiarities and even with a few  years of experience you might not have encountered them all.

## Basic Language Features

All statements in PHP must be terminated with a semicolon. An exception to  this is if the statement happens to be the last statement before a  closing tag.

Whitespace has no semantic meaning in PHP. There is no need to line code up, but  most coding standards enforce this to improve code readability.  Whitespace may not appear in the middle of function names, variable  names, or keywords.

Multiple statements are allowed on a single line.

Code blocks are denoted by the brace symbols { }.

PHP language construct and function names are not case-sensitive, but variable and constant names are.

```php
<?php

ECHO "Hello World"; // works
$variable = "Hello World";
echo $VARIABLE; // won't work
```

## Inserting PHP into Web Pages

Although  PHP is a general scripting language and can be used for other purposes,  it is most commonly deployed as a server-side scripting language used  for building web pages.

The PHP parser does not parse anything that is not included in the tags  that indicate PHP script. Content outside of PHP tags is simply output  without inspection. This allows PHP to be embedded in HTML.

There are several ways to delimit PHP script, but only the first two in this table are commonly used:

| Type     | Open                    | Close     | Note       |
| -------- | ----------------------- | --------- | ---------- |
| Standard | <?php                   | ?>        |            |
| Echo     | <?=                     | ?>        |            |
| Short    | <?                      | ?>        | Deprecated |
| ASP      | <%                      | %>        | Deprecated |

The echo tag allows you to easily echo a PHP variable and the shortened tag  makes your HTML document easier to read. It is commonly used in  templates where you want to output several values into various positions on a page. Using the short syntax keeps your template code much neater.

Its usage is easiest to understand when it’s shown along with the  equivalent in standard opening codes. The following two tags are  identical:

```php
<?php

<?= $variable ?>
<?php echo $variable ?>
```

Note

The echo statement is the last statement before a closing tag and so it does not need a semicolon to terminate it.

You can use PHP logic between opening and closing tags, as in this example:

Balance:

```php
<?php

if ($bankBalance > 0): ?>
<p class="black">
<?php else: ?>
<p class="red">
<?php endif; ?>
<?= $bankBalance?>
</p>
```

Let’s step through the code:

1. The PHP parser will output Balance: without evaluating it because it is not in the PHP tags.

2. The PHP tag then checks if the balance is greater than zero and terminates. The <p class="black"> tag is only output if that condition is true; otherwise, the <p class="red"> tag is output.

3. We use the echo tag syntax to output the $bankBalance variable.

4. Finally, the closing paragraph tag is output without being parsed because the PHP script has been closed.

Note: This approach will also work using the curly brace syntax of an if statement.

It is quite common in PHP programs to omit the closing tag ?> in a file. This is acceptable to the parser and is a useful way to  prevent problems with newline characters appearing after the closing  tag.

These newline  characters are sent as output by the PHP interpreter and could interfere with the HTTP headers or cause other unintended side-effects. By not  closing the script in a PHP file, you prevent the chance of newline  characters being sent.

Tip: It is a common coding standard to require that the closing tag is omitted in included files, but this is not a PHP requirement.

## Language Constructs

Language constructs are different from functions in that they are baked right into the language.

Language constructs can be understood directly by the parser and do not need to  be broken down. Functions, on the other hand, are mapped and simplified  to a set of language constructs before they are parsed.

Language constructs are not functions, and so cannot be used as a callback  function. They follow rules that are different from functions when it  comes to parameters and the use of parentheses.

For example, echo doesn’t always need parentheses when you call it and, if you call it  with more than one argument, then you can’t use parentheses.

<?php

// one parameter, no brackets

echo "hello\r\n";

// two parameters, brackets (syntax error)

//echo('hello', 'world');

// two parameters, no brackets

echo 'hello', 'world';

Furthermore, echo does not return a value, whereas every function will always return a value (or null).

The PHP Manual page on reserved keywords[1](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-516) has a complete list, but here are some of the constructs that you should be familiar with:

| Construct    | Used For                                                     |
| ------------ | ------------------------------------------------------------ |
| assert       | Debug command to test a condition and do something if it is not true. |
| echo         | Outputting a value to stdout.                                |
| print        | Outputting a value to stdout.                                |
| exit         | Optionally outputting a message and terminating the program. |
| die          | This is an alias for exit.                                   |
| return       | Terminates a function and returns control to the calling scope, or if called in the global scope, terminates the program. |
| include      | Includes a file and evaluates it. PHP will issue a warning if the file is not found or cannot be read. |
| include_once | If you specify include_once then PHP will make sure that it includes the file only once. |
| require      | PHP will include a file and evaluate it. If the file is not found or cannot be read, then a fatal error will be generated. |
| require_once | As for include_once, but a fatal error will be generated instead of a warning. |
| eval         | The argument is evaluated as PHP and affects the calling scope. |
| empty        | Returns a Boolean value depending on whether the variable is empty or not.  Empty variables include null variables, empty strings, arrays with no  elements, numeric values of 0, a string value of 0, and Boolean values of false. |
| isset        | Returns true if the variable has been set and false otherwise. |
| unset        | Clears a variable.                                           |
| list         | Assigns multiple variables at one time from an array.        |

One possible tricky exam question that might come up is in understanding the small difference between print and echo. The echo construct does not return a value, not even null, and so is not suitable for use inside an expression. The print construct will however return a value.

The reason not to use include_once() and require_once() all the time is a performance issue. PHP tracks a list of files that  has been included to support the functionality of these functions. This  requires memory so these functions are rather used when they are  necessary and not in favor of include or require.

##             Comments                            

There are three styles to mark comments:

<?php

\# Perl style comments

// C style comments

/*

  Multiline comment

*/

API documentation can additionally conform to external standards such as those used by the PHPDocumentor project.[2](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-517) This tool examines your API style comments and automatically creates documentation for you.

API documentation looks very similar to multiline comments:

<?php

/**

​    API documentation has two asterisks, this is not a PHP

​    syntax distinction, but is just a convention.

*/

##         Representing Numbers              

There are four ways in which an integer may be expressed in a PHP script:

| Notation    | Example       | Note                           |
| ----------- | ------------- | ------------------------------ |
| Decimal     | 1234          |                                |
| Binary      | 0b10011010010 | Identified by leading 0b or 0B |
| Octal       | 02322         | Identified by leading 0        |
| Hexadecimal | 0x4D2         | Identified by leading 0x or 0X |

Floating point numbers (called doubles in some other languages) can be expressed  either in standard decimal format or in exponential format.

| Form        | Example                  |
| ----------- | ------------------------ |
| Decimal     | 123.456                  |
| Exponential | 0.123456e3 or 0.123456E3 |

Note

The letter “e” in the exponential form is case-insensitive, as are the other letters used in the integer formats.

##             Variables                            

In  this section, I’m going to be focusing on how PHP handles variables. I’m assuming that you’ve had enough experience with PHP that I don’t need  to explain what variables are or how to use them. We’ll be looking at  the various types of variables PHP offers, how to change the type of a  variable, and how to check if a variable is set or not.

### Variable Types

PHP is a loosely typed language. It is important not to think that PHP  variables don’t have a type. They most definitely do, it’s just that  they may change type during runtime and don’t need their type to be  declared explicitly when initialized.

PHP will implicitly cast the variable to the data type required for an  operation. For example, if an operation requires a number, such as the  addition (+) operation, then PHP will convert the operands into a numeric format.

You’ll be introduced to type juggling in the “Casting Variables” section and  you’ll need to know the rules PHP follows when changing a variable type. For now, you just need to know that PHP variables have a type, that  type can change, and although you can explicitly change the type PHP  does this implicitly for you.

PHP has three categories of variable—scalars, composite, and resources. A  scalar variable is one that can only hold one value at a time. Composite variables can contain several values at a time.

A resource variable points to something not native to PHP like a handle  provided by the OS to a file or a database connection. These variables  cannot be cast.

Finally, PHP has the null type, which is used for variables that have not had a  value set to them. You can also assign the null value to a variable, but you cannot cast to a null type in PHP 7.1.

####                 Scalar Types                                                      

There are four scalar types:

| Type    | Alias | Contains                              |
| ------- | ----- | ------------------------------------- |
| Boolean | bool  | True or False                         |
| Integer | int   | A signed numeric integer              |
| Float   |       | A signed numeric double or float data |
| String  |       | An ordered collection of binary data  |

Some types have aliases. For example, consider this code that shows that bool is an alias for boolean:

<?php

$a = (boolean)true;

$b = (bool)true;

var_dump($a === $b); // bool(true)

Strings in PHP are not simply a list of characters. Internally PHP strings  contain information about their length and are not null terminated. This means that they may contain binary information such as an image file  that has been read from disk. In other words, PHP strings are binary  safe.

####             Composite                                         Types

There are two composite types: arrays and objects. Each of these has its own section in this book.

####                 Casting Variables                                                                                                                

This is a very important section of understanding PHP and even very  experienced developers may not be aware of some of the rules that PHP  uses to cast variables.

PHP implicitly casts variables to the type required to perform an operation.

It is also possible to explicitly cast variables using one of two options:

- Use a casting operator
- Use a PHP function

Casting  operators are used by putting the name of the data type you want to cast into brackets before the variable name. For example:

<?php

$a = '123';    // $a is a string

$a = (int)$a;   // $a is now an integer

$a = (bool)$a;   // $a is now Boolean and is true

You  can cast a variable to null, as in the following example, but this  behavior is deprecated in PHP 7.2 so you shouldn’t do it even though PHP 7.1 supports it.

<?php

$a = "Hello World";

$a = (unset)$a; // Deprecated in PHP 7.2

var_dump($a);  // NULL

There are also PHP functions that will convert a variable to a data type. These are named in a way that is self-documenting: floatval, intval, strval, and boolval.

Additionally, the intdiv function will potentially cast a double to an integer when it returns the integer result of dividing two integers.

You can also call the settype function on a variable that takes the desired data type as a second argument.

There are some rules that need to be remembered regarding how variables are  cast in PHP. You should read the manual page on type juggling[3](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-518) carefully, because there are many trips and traps in type juggling.  Also make sure that you read the pages linked to from the type juggling  page.

Instead of  exhaustively listing the rules, I’ll focus on some of the rules that may be counter-intuitive or are commonly mistaken.

Casting from float to integer does not round the value up or down, but rather truncates the decimal portion.

<?php

$a = 1234.56;

echo (int)$a;  // 1234 (not 1235)

$a = -1234.56

echo (int)$a;  // -1234

Some general rules for casting to Boolean are that:

- Empty arrays and strings are cast to false.
- Strings always evaluate to Boolean true unless they have a value that’s considered “empty” by PHP.
- Strings containing numbers evaluate to true if the number is not zero. Recall that such strings return false when the empty() function is called on them.
- Any integer (or float) that is non-zero is true, so negative numbers are true.

Objects can have the magic method __toString() defined on them. This can be overloaded if you want to have a custom  way to cast your object to string. We look at this in the section on  “Casting Objects to String”.

Converting a string to a number results in 0 unless the string begins with valid numeric data (see the PHP Manual[4](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-519) for more detail). By default, the variable type of the cast number will be integer, unless an exponent or decimal point is encountered, in  which case it will be a float.

Here is an example script that shows some string conversions:

<?php

$examples = [

  "12 o clock",

  "Half past 12",

  "12.30",

  "7.2e2 minutes after midnight"

];

foreach ($examples as $example) {

  $result = 0 + $example;

  var_dump($result);

}

/*

This outputs:

  int(12)

  int(0)

  double(12.3)

  double(720)

*/

####                 Floats and Integers                                                      

Be very careful when casting between floats and integers. The PHP Manual[5](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-520) has a very good example of how internal implementation details of numeric types can have counter-intuitive results:

<?php

echo (int) ( (0.1+0.7) * 10 ); // 7

echo (int) ( (0.1+0.5) * 10); // 6

One would expect the first example to display 8, but in fact the internal floating-point representation is just slightly less than 8.

When PHP converts a floating point number to integer it rounds toward zero, so it becomes 7.

The reason behind this is that some numbers are rational in base 10 but are irrational in base 2. Although 0.7 can be expressed as a rational  number in base 10, when expressed in base 2 it is irrational. Because  there are a limited number of bits available to store the number, it is  inevitable that some loss of precision will occur.

PHP integers are always signed. The range of values that an integer can take will depend on the system PHP is running on.

You can determine the size of an integer in bytes at runtime by querying the constant PHP_INT_SIZE. The constants PHP_INT_MAX and PHP_INT_MIN will give you the maximum and minimum values that can be stored in an  integer, respectively. There are similar constants for other numeric  types. They are listed in the PHP Manual page on reserved constants.[6](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-521)          

Caution

You should not rely on floats precision up to the last digit.

You should avoid testing floats directly for equality and rather test if  they are the same up to a given degree of precision, as in this example:

<?php

$pi = 3.14159625;

$indiana = 3.2;

$epsilon = 0.00001; // degree of error

if(abs($pi - $indiana) < $epsilon) {

  echo "Those values look the same to me";

} else {

  echo "Those values are different";

}

This code is checking if the values are the same to five degrees of precision. This script will output Those values are different because the difference is greater than the degree of error that we defined.

###               Naming Variables                                  

PHP variables begin with the dollar symbol $ and PHP variable names adhere to the following rules:

- Names are case sensitive
- Names may contain letters, numbers, and the underscore character
- Names may not begin with a number

Coding  conventions differ on the use of camelCase, StudlyCase, or snake_case,  but all of these formats are valid PHP variable name formats.

PHP also allows for variable variable names. This is best illustrated by example:

<?php

$a = 'foo';

$$a = 'bar'; // $a is 'foo', so variable $foo is set

echo $foo;  // bar

PHP 7  will always evaluate access strictly left to right. Older versions had a complicated set of rules to determine how it would evaluate this sort  of syntax. Happily, PHP 7 is simpler and consistent and I won’t worry  about explaining older versions.

Here is a more complicated example that illustrates how PHP evaluates from left to right:

<?php

$a = 'foo';

$$a['bar'] = 'Murky code';

// this assert passes

assert($$a['bar'] === $foo['bar']);

var_dump($foo);

/*

  array(1) {

   ["bar"]=>

   array(1) {

​    ["baz"]=>

​    string(10) "Murky code"

   }

  }

*/

There  are several caveats to using variable variable names. They could impact  on your code security and can also make your code a little murky to  read.

### Checking If a Variable Has Been Set

The command isset()                                                         will return true if a variable has been set and false otherwise. It is preferable to use this function instead of checking if the variable is null because it won’t cause PHP to generate a warning.

The command empty()                                                         will return true if a variable is not set and will not generate a warning. This is not a bulletproof way to test if a variable is set.

Note

Remember that the string “0” is considered empty, but is actually set.

Variables become unset when they become out of scope and you can use the command unset()                                                         to manually clear a variable. We’ll see later in  the book that the garbage collector is responsible for freeing up the  memory allocated to variables that have been unset.

##             Constants                            

Constants[7](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-522) are similar to variables but are immutable. They have the same naming  rules as variables, but by convention will have uppercase names.

They can be defined using the define        [8](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-523) function as shown:

<?php

define('PI', 3.142);

echo PI;

define('UNITS', ['MILES_CONVERSION' => 1.6, 'INCHES_CONVERSION' => '2.54']);

echo "5km in miles is " . 5 * UNITS['MILES_CONVERSION'];

/*

 3.1425km in miles is 8

*/

The third parameter of define is optional and indicates whether the constant name is case sensitive or not.

You can also use the const keyword to define constants. Constants can only contain arrays or scalar values and not resources or objects.

<?php

const UNITS = ['MILES_CONVERSION' => 1.6,

​        'INCHES_CONVERSION' => '2.54'];

echo "5km in miles is " . 5 * UNITS['MILES_CONVERSION'];

/*

 5km in miles is 8

*/

Only the const keyword can be used to create a namespaced constant, as in this example where we create constants in the "Foo" namespace and then try to reference them in the "Bar" namespace.

<?php

namespace Foo;

const AVOCADO = 6.02214086;

// using define() will generate a warning

define(MOLE, 'hill');

namespace Bar;

echo \Foo\AVOCADO;

// referencing the constant we tried to define() results in a fatal error

echo \Foo\MOLE;

You cannot assign a variable to a constant.

You can use static scalar values to define a constant, like this:

const STORAGE_PATH = __DIR__ . '/storage';

Note

Note the use of the “magic” constant __DIR__ that is set by PHP at runtime and contains the path that the script  resides in on the file system. These constants are discussed in the  section “Magic Constants”.

The constant() function[9](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-524) is used to retrieve the value of a constant.
```php
<?php

const MILES_CONVERSION = 1.6;

echo 'There are ' . constant('MILES_CONVERSION') . ' miles in a kilometer';

/*

 There are 1.6 miles in a kilometer

*/
```
##             Superglobals                                                                      

PHP has several superglobals[10](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-525) that are available automatically to the script. Superglobals are available in every scope.

You can alter the values of superglobals, but it’s generally suggested to  rather assign a locally scoped variable to the superglobal and modify  that. You need to know what each of the superglobals stores.

| Suberglobal | Stores                                                       |
| ----------- | ------------------------------------------------------------ |
| $GLOBALS    | An array of variables that exist in the global scope.        |
| $_SERVER    | An array of information about paths, headers, and other information relevant to the server environment. |
| $_GET       | Variables sent in a GET request.                             |
| $_POST      | Variables sent in a POST request.                            |
| $_FILES     | An associative array of files that were uploaded as part of a POST request. |
| $_COOKIE    | An associative array of variables passed to the current script via HTTP cookies. |
| $_SESSION   | An associative array containing session variables available to the current script. |
| $_REQUEST   | POST, GET, and COOKIE request variables.                     |
| $_ENV       | An associative array of variables passed to the current script via the environment method. |

The $_SERVER superglobal has many keys, and you should be familiar with them. The PHP Manual[11](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-526) has a list of them and you should make sure that you’ve read the manual page and understood all of the keys.

Tip

Note that the $_SERVER['argv'] contains arguments sent to the script, which is distinct from $_ENV. Knowledge of this level of detail is required for the certification exam.

##             Magic Constants                                                                  

Magic constants are those which PHP provides automatically to every running script. There are quite a lot of reserved constants[12](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-527) and you will need to know the error constants, as well as the commonly used predefined constants.[13](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-528)

| Constant      | Contains                                                     |
| ------------- | ------------------------------------------------------------ |
| __LINE__      | The current line number of the PHP script being executed     |
| __FILE__      | The fully resolved (including symlinks) name and path of the file being executed |
| __CLASS__     | The name of the class being executed                         |
| __METHOD__    | The name of the class method being executed                  |
| __FUNCTION__  | The name of the function being executed                      |
| __TRAIT__     | The namespace and name of the trait that the code is running in |
| __NAMESPACE__ | The current namespace                                        |

Note

The value of these magic constants changes depending on where you use it.
