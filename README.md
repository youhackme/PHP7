#A peek at PHP 7



**Slide 1:**
Release of PHP 7: 3 Décembre 2015
PHP 7 is now powered by PHPNG (the Next Generation of Zend Engine)

**Slide 2:**
Why PHP 7?
One Word: PERFORMANCE

**Slide 3:**
-- Insert Images here to show benchmarking results for
-- Magento
-- WordPress
-- ZF
--How fast dynamic languages render a Mandelbrot fractal

**Slide 4:**
Incompatibilities:
- Deletion of deprecated functionalities:
https://wiki.php.net/rfc/remove_deprecated_functionality_in_php7

Example:
ext/MySQL => deprecated since PHP 5.5 => Use PDO_MySQL or MySQLi
ext/ereg => deprecated since PHP 5.3 => Use ext/pcre

**Slide 5:**
Incompatibilities:

The PHP 4 constructors are now deprecated!
https://wiki.php.net/rfc/remove_php4_constructors

```
<?php
class ItWasTime{
	public function ItWasTime(){...}
}

new ItWasTime();
```

**Slide 6:**
Incompatibilities:
Certain types have become reserved keywords for Class names, traits and interfaces.

-int
-float
-bool
-string
-true
-false
-null
-resource
-object
-mixed
-numeric

```
<?php

class resource{
	public function __construct(){...}
}
new resource();
```
Returns a fatal error: `Fatal error: "Resource cannot be used as a class name"`

**Slide 7:**
Incompatibilities:

- Deletion of ASP and script tags

```
<script language="php">...</script>
<%  %>
<%= %>
```

**Slide 8:**

Incompatibilities:
- Switch case no longer accept multiple defaults. It should contain only one otherwise you will get a Fatal error.

```
<?php

switch($expression){
	default:
	echo 'Hello';
	break;
	default:
	echo 'Salut';
	break;
}
```

- Causes fatal error: Switch statements may contain one default clause.

**Slide 9:**
Incompatibilites:

An invalid octal now throws a fatal error.
```
- <?php

$octale = 0148;
echo $octale;
```

- Insert image here


**- Slide 10:**
Incompatibities:

Hexadecimal values are no longer recognized as numeric values.

```
<?php

var_dump(is_numeric('0x143'));

PHP 5.X           PHP 7
bool(true)        bool(false)

- Slide 11:
Incompatibilies:

```

<?php

$object = &new stdclass;

Returns a parse error
-- Insert image here.

**Slide 12:**
- Incompatibilies:
The two functions `func_get_arg` and `func_get_args` returns the value of the variable in their local context.

```
<?php

function doThis($what){
	$what++;
	echo func_get_arg(0);
}

doThis(2);

In PHP 5.X       PHP 7

Display 2        Display 3
```

**Slide 13:**
- Scalar type hinting
-- PHP 7 offer you the possibility to type hint with string, integer, float, boolean.

Activate by adding `declare(strict_types=1);` at the top.

```
<?php
declare(strict_types=1);

function test(int $param){
	return $param;
}

 echo test(1);        echo test("1");

Display 1               Fatal error: Argument 1 passed to test()...
```


**Slide 14:**

- Possibility to define the type of the returned value. A catchable fatal error is returned if it do not correspond.

```
<?php

function test():  DateTime{
	return 1;
}
// Return type is invalid
```

```
<?php
function test():array{
	return [0,1,2];
}
// Return type is valid

```


Note: __construct(), __destruct() and __clone() cannot
declare a return type.



**Slide 15:**
Group use declaration

- Commmon namespace declaration can be grouped.

```
//Before
<?php
use Symfony\Component\Console\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Input\InputOption;
use Symfony\Component\Console\Output\OutputInterface as Output;

```

```
<?php
//After
use Symfony\Component\Console\{
	Command\Command,
	Input\InputInterface,
	Input\InputOption,
	Output\OutputInterface as Output
}

```


**Slide 16:**
- Anonymous Class
- Same principle as for Anonymous function.

```
<?php

class Log{
	public function log($msg){...}
}

$obj->setLog(new Log());

```

```
<?php
$obj->setLog(new Class{
	public function log($msg){...}
});
```

**Slide 17:**

Spaceship Operator

- A new comparison operator (Combined Comparison Operator)

- It is identical to functions strcmp() et version_compare()
- But can compare all types as long as the type on the left is the same as on the right.
- It can compare numbers, strings, arrays, objects, ...

Returns:
* 0 if equal
* -1 if the value on the left is less
*1 if the value on the right is less

```
<?php
echo 1<=>2; // -1
echo 1<=>1; // 0
echo 2<=>1; // 1

echo "a"<=>"a";//0
echo "a"<=>"b";//-1
echo "b"<=>"a";//1
echo "a"<=>"aa";//-1


<?php
// PHP 5.X
 function order_func($a, $b) {
 return
 ($a < $b) ? -1 : (($a > $b) ? 1 : 0);
 }



 //PHP 7
 <?php
 function order_func($a, $b){
 return $a <=> $b;
 }
 ```




**Slide 18:**

 The Null Coalesce Operator
 - Returns the result of the left operation if it is not NULL
 else it returns the results of the right operation.

 ```
 <?php
 $name = isset($_GET['name']) ? $_GET['name'] : 'default';
```

```
<?php
 $name = $_GET['name'] ?? 'default';
```
