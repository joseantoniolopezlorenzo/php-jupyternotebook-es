# Operators

### Arithmetic

You should recognize the arithmetic functions:

| Operation| Example  | Description  |
| -------------- | -------- | ---------------------------------------- |
| Addition | 1 + 2.3  ||
| Subtraction| 4 – 5||
| Division | 6 / 7||
| Multiplication | 8 * 9||
| Modulus| 10 % 11  | Gives the remainder of dividing 10 by 11 |
| Power| 12 ** 13 | Raises 12 to the power of 13   |

These arithmetic operators take two arguments and so are called binary.

The unary operators following take only one argument and their placement  before or after the variable changes how they work. There are two unary  operators in PHP, namely prefix and postfix. They are named for whether  the operator appears before or after the variable that it affects.

- If the operator appears before the variable (prefix), then the interpreter will first evaluate it and then return the changed variable.
- If the operator appears after the variable (postfix), then the interpreter will return the variable as it was before the statement executed and  then increment the variable.

Let’s show their effects on a variable $a that we initialize to 1 and then operate on:

| Command| Output | Value of $a Afterwards | Description |
| ---------- | ------ | ---------------------- | ----------- |
| $a = 1;|  | 1|   |
| echo $a++; | 1| 2| Postfix |
| echo ++$a; | 3| 3| Prefix|
| echo $a--; | 3| 2| Postfix |
| echo --$a; | 1| 1| Prefix|

### Logic Operators

PHP uses both symbol and word form logic operators. The symbol form operators are C-based.

| Operator | Example   | True When  |
| -------- | --------- | -------------------------------------- |
| and| $a and $b | Both $a and $b evaluate true |
| and| $a && $b  |  |
| or | $a or $b  | Either $a or $b evaluate true|
| or | $a || $b  |  |
| xor| $a xor $b | One of (but not both) $a or $b is True |
| xor| $a ^ $b   |  |
| not| !$a | $a is not true (false) |

It is best practice not to mix the word form (e.g., and) and the symbol (e.g., &&) in the same comparison, as the operators have different precedence. It’s safest to stick to using the symbol form exclusively.

In this example, we see that operator precedence[14](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-529) results in the variables $truth and $pravda not being the same even though we’re performing the “same” logical operator to derive them.

This happens because the logical operators and and or have lower priority than the equality operator =.

<?php

$a = true;

$b = false;

$truth = $a and $b; // true

$pravda = $a && $b; // false

assert($truth === $pravda);

/*

  Warning: assert(): assert($truth === $pravda) failed

*/

### Ternary Operator

PHP implements the ternary operator in the same format as other C-ancestor languages. The general format is as follows:

condition ? expression1 : expression2;

If condition is true, then expression1 will be evaluated; otherwise expression2 is evaluated.

Here is an example that checks the condition of isset($a) and assigns the string value 'true' or 'false' to $b accordingly.

<?php

$a = 'foo';

$b = (isset($a)) ? 'true' : 'false';

echo $b;  // true

The syntax above is identical to the following if statement:

<?php

$a = 'foo';

if (isset($a)) {

 $b = 'true';

} else {

 $b = 'false';

}

echo $b;  // true

If the true value is omitted in the ternary operator, then the statement is evaluated as the expression, as follows:

<?php

$a = true;

$b = $a ?: 'foo';

echo $b;  // 1

Thisshortened version of the ternary operator is not suitable for testing if a variable exists, as the interpreter will throw a warning in thiscase.

### Null Coalescing Operator

The  null coalescing operator is just a special case of the ternary operator. It allows you to neaten up the syntax used when you’re using isset to assign a default value to a variable.

<?php

// Long form ternary syntax

$sortDirection = (isset($_GET['sort_dir'])) ? $_GET['sort_dir'] : 'ASC';

// Equivalent syntax using the null coalescing operator

$sortDirection = $_GET['sort_dir'] ?? 'ASC';

// The null-coalesce operator can be chained

$sortDirection = $_GET['sort_dir'] ?? $defaultSortDir ?? 'ASC';

// The Elvis operator raises E_NOTICE if the GET variable is not set

$sortDirection = $_GET['sort_dir'] ?: 'ASC';

It ispreferable to use the null-coalescing operator over Elvis because the  null-coalescing operator doesn’t raise a notice error if the variable is not set.

### Spaceship

The spaceship operator is used to compare two different values and isparticularly useful for writing callbacks for the sorting functions that we’ll be looking at later.

It returns -1, 0, or 1 when the left operand is respectively less than, equal to, or greater than the right.

| Operation| Value |
| ---------------------- | ----- |
| 1 <=> 0  | 1 |
| 1 <=> 1  | 0 |
| 1 <=> 2  | -1|
| 'apples' <=> 'Bananas' | 1 |
| 'Apples' <=> 'bananas' | -1|

The spaceship operator uses the standard PHP comparison rules.

We’ll see why there is this surprising difference in the string comparison in the section on “Strings” later.

### Bitwise

​Bitwise operators work on the bits of integers represented in binary  form. Using them on a different variable type will cause PHP to cast the variable to integer before operating on it.

There are three standard logical bitwise operators:

| Operator | Operation   | Description|
| -------- | ----------- | ------------------------------------------------------------ |
| &  | Bitwise AND | The result will have a bit set if both of the operands bits were set |
| \| | Bitwise OR  | If one or both of the operands have a bit set then the result will have that bit set |
| ^  | Bitwise XOR | If one and only one of the operands (not both) has the bit set then the result will have the bit set. |

The result  of a bitwise operator will be the value that has its bits set according  to these rules. In other words, the bit in each position of the operands is evaluated against the corresponding bit in the same position of the  other operand.

It’seasier to consider the binary representations of numbers when using  these operators. You can calculate the binary representation of the  result by comparing bits (from right to left) and then converting to  decimal when you’re done.

Let’s look at 50 & 25 as an example. I’ve put the binary representations in comments in the  three rows. You can see that I calculated the binary representation of $c by checking whether the bit in that position is set in $a and in $b. In this case, only one such bit is true in both positions.

<?php

$a = 50;// 0b110010

$b = 25;// 0b011001

$c = 50 & 25;  // 0b010000

echo $c;// 16

Here is a tabular format that might make it easier to follow. I’m placing the  bits from each number in columns. The row marked “operation” shows the  comparison that happens—for every position the bits from the two valueshave the logical “and” operator applied to them.

| Value/Operator | Bits in Each Position |   |   |   |   |   |
| -------------- | --------------------- | ------- | ------- | ------- | ------- | ------- |
| 50   | 1   | 1 | 0 | 0 | 1 | 0 |
| 25   | 0   | 1 | 1 | 0 | 0 | 1 |
| Operation| 1 and 0 | 1 and 1 | 0 and 1 | 0 and 0 | 1 and 0 | 0 and 1 |
| Result   | 0   | 1 | 0 | 0 | 0 | 0 |

When we echo out the result. PHP gives us the integer value and you can quickly  confirm that the binary representation you evaluated matches it, because 2 raised to the power of 4 is 16.

### Bit Shifting

PHP also has operators to shift bits left and right. The effect of these  operators is to shift the bit pattern of the value either left or right  while inserting bits set to 0 in the newly created empty spaces.

To understand how these operators work, picture your number represented in binary form and then all the 1s and 0s being stepped to the left or  right.

The following table shows shifting bits, one to the right and one to the left.

| Operation | Operation   | Result in Binary | Result in Decimal |
| --------- | ----------- | ---------------- | ----------------- |
| 50  |   | 00110010   | |
| 50 >> 1   | Shift Right | 00011001   | 25  |
| 50 << 1   | Shift Left  | 01100100   | 100 |

I’ve included enough leading zeroes in the binary forms to make it easier to see the pattern of what’s happening.

You can see that when we shifted to the right, the right-hand bit was“lost”. When we shift left, we insert new bits that are set to 0 on the  right.

It’s important to be cautious when using bitwise operations to perform calculations,  as the integer overflow size may vary between the different environments that PHP is deployed on.

For example, although a 64-bit system will have the same result for both operations, on a 32-bit integer system they will not:

<?php

$x = 1;

echo $x << 32;

echo $x * pow(2, 32);

The  first line will echo 0 as shifting left 32 bits will fill the 32-bit  integer with 0 bits. The second line will use the maths library and  output the correct value of 2 raised to the power of 32.

Tip

If you want to experiment with binary operators, you’ll find the base_convert() function extremely useful. For example, to output the binary representation of the decimal number 50, you could echo base_convert(50, 10, 2) . PHP_EOL;.

### Bitwise NOT

You  won’t need to know the details of the mathematics behind this operator,  so don’t spend too much time worrying about the details. If you  understand the effect it has on the bits, you should be ready to answer  questions about it.

PHP uses the ∼ (tilde) symbol for bitwise NOT. The effect of this operator is to flip  the bits in a value—if a bit is set it becomes unset, and if it were not set it becomes set.

This is best understood by example:

|   | Bits ||||||
| ------- | ---- | ---- | ---- | ---- | ---- | ---- |
| 50| 1| 1| 0| 0| 1| 0|
| ∼ (NOT) | 0| 0| 1| 1| 0| 1|

The value (in decimal) of the result is -51.

Just for enrichment purposes, you could read up on Wikipedia about two’s complement.[15](file:///home/antonio/Escritorio/PHP 7 Zend Certification Study Guide - Andrew Beak.htmlz_FILES/index.html#calibre_link-530) It is chiefly used to get to a binary representation of a negative number.

### Assignment Operators

PHP uses the = symbol as an assignment operator. The following line sets the value of $a to 123.

<?php

$a = 123;

The  assignment operator can be combined with just about all the binary and  arithmetic operators. This syntax serves as a shortcut that is best  shown by providing an example of equivalent statements:

<?php

$a += 345;  // equivalent to $a = $a + 345;

$a .= 'foo'; // equivalent to $a = $a . 'foo';

The result of any assignment expression is the value of the variable following the assignment.

A fairly common typing error is to mistakenly forget the second = symbol in an equality check. Consider the following example where we’re using the assignment operator in the if statement where we intended to use the equality operator.

<?php

$foo = "hello";

if ($foo = "world") {

 echo "matches";

} else {

 echo "does not match";

}

Had this been an equality operator, the if statement would be false and the script would output “does not match”.  However, because we’re assigning the string “world” to the variable $foo, the result is the value “world”, which when cast to Boolean is true (see “Casting Variables”).

Some coding conventions use what is called the “Yoda Condition” to assist  with this error. It uses the fact that PHP will not let you change the  value of a constant. If you always place the constant on the left of an  equality comparison, you’ll be warned if you mistype the operator.  Whether the cost of code readability is worth it is a matter of personal style.

### Reference Operator

By default, PHP assigns all scalar variables by value.

PHP has optimizations to make assignment by value faster than assigning by  reference (see the section on “Memory Management”), but if you want to  assign by reference, you can use the & operator as follows:

<?php

$a = 1;

$b = &$a; // assign by reference

$b += 5;

echo $a; // 6

PHP always assigns objects by reference; if you try to explicitly create it by reference, PHP will generate a parse error.

<?php

class MyClass {}

// Parse error: syntax error, unexpected 'new'

$a = &new MyClass;

### Comparison Operators

PHP uses the following comparison operators:

| Operator | Description|
| -------- | ------------------------------------------------------------ |
| >  | Greater than   |
| >= | Greater than or equal to   |
| <  | Less than  |
| <= | Less than or equal to  |
| <> | Not equal  |
| == | Equivalence; values are equivalent if cast to the same variable type |
| ===| Identity; values must be of the same data type and have the same value |
| != | Not equivalent |
| !==| Not identical  |

It is important to understand the difference between an equivalent comparison and an identity comparison:

- Operands are equivalent if they can be cast to a common data type and have the same value.
- Operands are identical if they share the same data type and have the same value.

Arrays are  equivalent if they have the same key and value pairs. They are identical if they have the same key and value pairs, in the same order, and the  key-value are of the same type.

When using comparison operators on arrays, the count of their keys is used to determine which is greater or lesser.

When compared to a scalar variable, both an object and an array will be considered greater than the scalar.

<?php

$a = [1];

$b = 100;

echo $a <=> $b; // 1

Be  careful when using comparison operators on strings, or when using them  on mismatching variable types. See the section on “Casting Variables”  for more information.

### Two More Operators

PHP provides an operator to suppress error messages. This will work only if the library that the function is based on uses PHP standard error reporting.

<?php

// Error messages will be suppressed

$dbConnection = @mysqli_connect(...);

It’s bad practice to suppress PHP errors with the @ operator. It is better to use PHP settings to suppress errors in your  production environment and to allow your development environment to  display errors. Having code that fails silently without producing an  error makes debugging much more difficult than it needs to be.

The last operator we will discuss is the backtick operator. It is not commonly used and is equivalent to calling the shell_exec() command. In the following example, the variable $a will contain the name of the user running the PHP interpreter.

<?php

// This is the equivalent of echo shell_exec('whoami');

echo `whoami`;

In a web environment this will probably be www-data. This is the default for Nginx and Apache, but from the command line will be the name of the user who is logged in.
