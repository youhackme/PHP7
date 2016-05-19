#A peek at PHP 7

1. **Slide 1:**
- Release of PHP 7: 3 December 2015
- PHP 7 is now powered by PHPNG (the **Next Generation** of Zend Engine)

2. **Slide 2:**

	Why PHP 7?

	One Word: **PERFORMANCE**


3. **Slide 3:**

- Insert Images here to show benchmarking results for:

	* Magento

	* WordPress

	* ZF

	* Laravel

4. **Slide 4:**

##### Incompatibilities:

* ###### Deletion of deprecated functionalities:

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/1.png?raw=true)




5. **Slide 5:**

##### Incompatibilities:


```
<?php
class ItWasTime{
	public function ItWasTime(){...}
}

new ItWasTime();
```

6. **Slide 6:**

##### Incompatibilities:

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/2.png?raw=true)


7. **Slide 7:**

##### Incompatibilities:

- Deletion of ASP and script tags

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/3.png?raw=true)


8. **Slide 8:**

##### Incompatibilities:

- Switch case no longer accept multiple defaults. It should contain only one otherwise you will get a Fatal error.

- Causes fatal error: Switch statements may contain one default clause.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/4.png?raw=true)


9. **Slide 9:**

##### Incompatibilities:

An invalid octal now throws a fatal error.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/5.png?raw=true)



10. **Slide 10:**

##### Incompatibilities:

Hexadecimal values are no longer recognized as numeric values.
![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/6.png?raw=true)


11. **Slide 11:**

##### Incompatibilities:


![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/7.png?raw=true)


12. **Slide 12:**

##### Incompatibilities:

The two functions `func_get_arg` and `func_get_args` returns the value of the variable in their local context.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/8.png?raw=true)


13. **Slide 13:**
- Scalar type hinting
-- PHP 7 offer you the possibility to type hint with string, integer, float, boolean.

Activate by adding `declare(strict_types=1);` at the top.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/9.png?raw=true)



14. **Slide 14:**

- Possibility to define the type of the returned value. A catchable fatal error is returned if it do not correspond.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/10.png?raw=true)


15. **Slide 15:**

Group use declaration

- Commmon namespace declaration can be grouped.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/11.png?raw=true)



16. **Slide 16:**
- Anonymous Class
- Same principle as for Anonymous function.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/12.png?raw=true)


17. **Slide 17:**

Spaceship Operator

- A new comparison operator (Combined Comparison Operator)

- It is identical to functions strcmp() et version_compare()
- But can compare all types as long as the type on the left is the same as on the right.
- It can compare numbers, strings, arrays, objects, ...

**Returns:**
* 0 if equal
* -1 if the value on the left is less
* 1 if the value on the right is less


![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/13.png?raw=true)

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/14.png?raw=true)


18. **Slide 18:**

 The Null Coalesce Operator
 - Returns the result of the left operation if it is not NULL
 else it returns the results of the right operation.

![Deprecated extensions](https://github.com/youhackme/php7/blob/master/img/15.png?raw=true)
