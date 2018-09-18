PHP Documentation From Php Manual(IMP Notes)
<?php
PHP Coding Patern
ANS :
1) <?php echo 'While this is going to be parsed.'; ?>
2) <?php if ($expression == true): ?>
This will show if the expression is true.
<?php else: ?>
Otherwise this will show.
<?php endif; ?>
3) <script language="php">
echo 'some editors (like FrontPage) don\'t
like processing instructions within these tags';
</script>
-------------------------------------------------------------------------------------------------------
Variable Type in PHP
ANS :
Four scalar types:
1)Boolean : Always True or False
2)Integer
3)Float
4)String
Two compound types:
1)Array
2)Object
Two compound types
1)Resource
2)Null
IMP : gettype function is useful for get current data type same as var_dump
Type Casting are possible in php.
Integer :
Type of Integer value : decimal(0 to 9),hexadecimal,octal(0 to 7),binary
Type of String value : Single quated,Double quated,Heredoc
Heredoc Notes : A third way to delimit strings is the heredoc syntax: <<<. After this operator,
an identifier is provided, then a newline. The string itself follows, and then the same identifier
again to close the quotation.
The closing identifier must begin in the first column of the line. Also, the identifier must follow the
same naming rules as any other label in PHP: it must contain only alphanumeric characters and underscores,
and must start with a non-digit character or underscore.
Ex :
<?php
/*
class foo {
public $bar = <<<EOT
bar
EOT;
}
*/
?>
Null : No Value in variable same as unset(for clear value).
-------------------------------------------------------------------------------------------------------
Escape Character in PHP
ANS :
\n linefeed (LF or 0x0A (10) in ASCII)
\r carriage return (CR or 0x0D (13) in ASCII)
\t horizontal tab (HT or 0x09 (9) in ASCII)
\v vertical tab (VT or 0x0B (11) in ASCII) (since PHP 5.2.5)
\e escape (ESC or 0x1B (27) in ASCII) (since PHP 5.4.4)
\f form feed (FF or 0x0C (12) in ASCII) (since PHP 5.2.5)
\\ backslash
\$ dollar sign
\" double-quote
\[0-7]{1,3} the sequence of characters matching the regular expression is a character in octal notation,
which silently overflows to fit in a byte
(e.g. "\400" === "\000")
\x[0-9A-Fa-f]{1,2}the sequence of characters matching the regular expression is a character in hexadecimal
notation
\u{[0-9A-Fa-f]+} the sequence of characters matching the regular expression is a Unicode codepoint, which
will be output to the string as that codepoint's
UTF-8 representation (added in PHP 7.0.0)
-------------------------------------------------------------------------------------------------------
Any other way to declare variable in php?.if yes,Kindly mention.
ANS : Yes
<?php
$str = <<<EOD
Example of string
spanning multiple lines
using heredoc syntax.
EOD;
echo "This is {$str}";
echo "This is $str";
echo 'This is '.$str;
?>
IMP : 3 ways to declare variable same as we can declare fuction using class.
?>
-------------------------------------------------------------------------------------------------------
What id Object?
ANS : Object of collection of related entities like class and method.
-------------------------------------------------------------------------------------------------------
What is Type Juggling?
ANS : it is called type casting.
Ex : $foo = (int) $bar;
-------------------------------------------------------------------------------------------------------
Constant : Can't change value entire programme.
Ex : <?php
define("CONSTANT", "Hello world.");
echo CONSTANT; // outputs "Hello world."
echo Constant; // outputs "Constant" and issues a notice.
?>
-------------------------------------------------------------------------------------------------------
What is $$ mean in php?
ANS :
A variable variable takes the value of a variable and treats that as the name of a variable.
Ex :
$$n = 'ans';
here ans be a variable.
-------------------------------------------------------------------------------------------------------
IMP : Set multiple value in one value using cookie set via serialize() And Explode().
-------------------------------------------------------------------------------------------------------
Arithmetic Operator : ** usage?
ANS : ** is for power.
Ex : 3**3(PHP) = 3*3*3(As Per Maths) = 27
-------------------------------------------------------------------------------------------------------
How to assign by reference?
ANS :
$a = 5;
$b = &$a;
IMP : Here in change value of b variable, changes will be implemented in mother variable.
more details : study call by value And call by reference
-------------------------------------------------------------------------------------------------------
<=> mean in comparison operator?
ANS :
Ex : $a <=> $b
An integer less than, equal to, or greater than zero when $a is respectively less than, equal to,
or greater than $b. Available as of PHP 7
-------------------------------------------------------------------------------------------------------
@ is error control operator.Why we use @ operator in php?
ANS : 1)It is use for ignore error.
2)ini_set('error.silent',TRUE) set in php ini file.
3)try
{}
catch(Exception $ex)
{$x->getMessage();}
4) $var = @new some_class(); Declare class
-------------------------------------------------------------------------------------------------------
Array Operator Comparison Example.
ANS :
$a = array("apple", "banana");
$b = array(1 => "banana", "0" => "apple");
var_dump($a == $b); // bool(true)
var_dump($a === $b); // bool(false)
EX2 : Access each element of array using list method
$myArray=array('aa','bb','cc','dd');
while (list ($key, $val) = each ($myArray) ) echo $val."<br>";
reset($myArray);
while (list ($key, $val) = each ($myArray) ) echo $val."<br>";
Way of Array Declaration
$people = array(
array('name' => 'Kalle', 'salt' => 856412),
array('name' => 'Pierre', 'salt' => 215863)
);
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Welcome To PHP OOPS
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Type Operators in PHP
ANS : instanceof is PHP variable is use to check objact of class is declare or not.
Ex :
class MyClass
{
}
class NotMyClass
{
}
$a = new MyClass;
var_dump($a instanceof MyClass); // bool(true)
var_dump($a instanceof NotMyClass); // bool(false)
Notes :
in the case of extend class both value are true
or function overloading And Overiding both are possible.
-------------------------------------------------------------------------------------------------------
Function Overloading Example
Ex :
class abc //overloading example with access parent function
{
public static $count = 0;
public static function getCount()
{
return self::count;
}
public funtion __construct()
{
self::count++;
}
}
class xyz extends abc
{
public static function getCount()
{
parent::getCount();
}
}
-------------------------------------------------------------------------------------------------------
Data Type Declare on function Declaration
function sum($a, $b): float
return $a + $b;
}
-------------------------------------------------------------------------------------------------------
Anonymous functions
ANS :
Anonymous functions mean functions without name.Anonymous functions, also known as closures.
They are most useful as the value of callback parameters, but they have many other uses.
-------------------------------------------------------------------------------------------------------
Get value after call in function
public function __construct($self)
{
$this->_self = $self;
$this->_refl = new ReflectionObject($self);
}
-------------------------------------------------------------------------------------------------------
What is Object?Explain about behaviers and attributes.
ANS :
Object is collection of related entities.
Ex.Moniter : attribute -> Model no,Screen Size
Behaviers -> it's function like volume up down etc.
-------------------------------------------------------------------------------------------------------
Endcapesolution : Data memeber And Member function are combine in class.It is use for security object in
Data memeber And Member function.
There are three visibility mode in Encapesolution.
1)Private
2)Public
3)Protected
Notes : 1)Public member And Member function can be accessable within And Outer class.
2)Private memeber And Member function can be accessable within class.It is possible
to access outer class using scope resolution operator(::).
3)Protected member And Member function can be accessable within class.It can't access
out class but possible to access using extendable class as per inheritance concept.
4)class member And Member functions both are public if not mention before.
5)public keyword not essential to write before member And Member function.
-------------------------------------------------------------------------------------------------------
Abstract class : It mean half class.Here function define in class but not be declare in class using abstract keyword.
Ex : abstract class abc
{
public abstract function xyz();
public function def();
{
echo 'Hello';
}
}
class def extends abc
{
public function xyz()
{
echo 'xyz';
}
}
Ex : class abc
{
public abstract function xyz();
public function def();
{
echo 'Hello';
}
}
Why usage : If our application large,How to handle common function in class exist or not.This case
Abstract class is useful.
Notes : 1)our above example xyz() class defined.If other class extends class abc,xyz function
Declare in extended class must be essential otherwise it generate error.
2)Abstract class object is nothing possible.
3)It should be use for enforcement using abstract function define and abstract class.
4)function defined and declare both are possible.
5)if any member fuction in class,this class automatically be abstract class.
6)Data member And member function declare with abstract class possible.
Module : Employee management system : common field is monthly salaray function is compulsary so how to h
handle.Abstract class widely use of handle common function in extended class.
-------------------------------------------------------------------------------------------------------
Interfaces : Interfaces suchs as Abstract class.
Syntax :
interface abc
{
public function aaa();
}
interface def
{
public function bbb();
}
class ghi implement abc,def
{
publlic function aaa()
{
echo 'Abc';
}
public function bbb()
{
echo 'Def';
}
}
note : interface not be extend but it should be implement to anoter class.
Why Interfaces : 1)Extend class is always extend once class but interface implement multiple class.
2)data member can not be declare in Interfaces class.
3)Member function always public.
4)other advantage same as abstract class.
5)Member function can't be declare and function should always define.
-------------------------------------------------------------------------------------------------------
Static Members : static member is related class not to object.
Syntax :
class abc
{
public static $data = 'abc';
public static function xyz()
{
echo 'xyz';
}
}
echo abc::xyx;
echo abc::xyz();
class abc
{
public static $data = 'abc';
public static function xyz($val)
{
return self::$val;
}
}
echo::xyz('abc');
class abc
{
public static $count = 0;
public static function getCount()
{
return self::count;
}
public funtion __construct()
{
self::count++;
}
}
$obj1 = new abc();
$obj2 = new abc();
$obj3 = new abc();
echo abc::getCount();//Output : 3
Advantage : 1)access data member and function without delclare object.
2)Static value can not be change outside class but change within class possible
3)this keyword work with object only.
4)Using internal function and data member using self keyword.
5)Get count of object of specific class.
-------------------------------------------------------------------------------------------------------
Late Static Binding : Compile programme and get response in run time.In other programme,Get response from
compile time.it take value from extended class and response as per extended class.
Ex.
class baseTable
{
protected $table = 'user_master';
public static function select1()
{
return 'select * from'.static::$table;
}
public static function select2()
{
return 'select * from'.self::$table;
}
}
class mainTable extends baseTable
{
protected $table = 'result_master';
}
$obj = new mainTable();
echo $obj->select1(); //Output : select * from result_master
echo $obj->select2(); //Output : select * from user_master
note : Dofferent analyze using select1 and select2 method
-------------------------------------------------------------------------------------------------------
Dependecy Injection : It is one type of coding patern.
Ex : Dependecy Example
class Logger
{
public function log($message)
{
echo 'Log Message'.$message;
}
}
class User
{
private $logger;
public function __construct()
{
$this->logger = new Logger();
}
public function createUser()
{
$this->logger->log('Create User Successfully');
}
public function updateUser()
{
$this->logger->log('Update User Successfully');
}
}
Ex : Dependecy Injection Example
class Logger
{
public function log($message)
{
echo 'Log Message'.$message;
}
}
class User
{
private $logger;
public function __construct($log)
{
$this->logger = new $log();
}
public function createUser()
{
$this->logger->log('Create User Successfully');
}
public function updateUser()
{
$this->logger->log('Update User Successfully');
}
}
$logger = new Logger();
$profile = new User($logger);
$profile->createUser();
-------------------------------------------------------------------------------------------------------
Polymorphism : one name in multilple form.
Example module attached.
-------------------------------------------------------------------------------------------------------
Trait : It is new features in php 5.4.
Ex :
class abc
{
function one()
{
echo 'One';
}
function two()
{
echo 'Two';
}
}
in above examle , our extended class def we access one fuction one not to two.what should do.
in above case trait is so useful.
class abc
{
function one()
{
echo 'One';
}
}
trait two
{
function two()
{
echo 'Two';
}
}
class def extends abc
{
//Here include one function only.
}
class ghi extends abc
{
use two;
//Here include one function from class and two funtion from trait.
}
how to solve conflicts if two trais hold same method.What should do this case?
trait test1
{
public function test()
{
echo 'test1';
}
}
trait tes2
{
public function test()
{
echo 'test2';
}
}
class abc
{
use test1,test2;//this syntax generate error due to conflicts.
use test1,test2 // Solve above error using instead of and as keyword.
{
test1::test insteadof test2;
test2::test as test_two;//Change the name of class using as keyword
}
}
$obj = new abc();
$obj->new test1();
$obj->new test_two();
Access Level in Trait
trait abc
{
private function xyz()
{
echo 'xyz';
}
}
class test
{
use abc
{
abc::xyz as public;//Change visibility mode in trait
abc::xyz as xyztest//Change method name in trait
}
}
$obj->test();
obj->xyz();
-------------------------------------------------------------------------------------------------------
Namespaces : same name class and function not allow in php.use same name class using namespace.
Ex :
namespace abc
{
class test
{
public function __construct()
{
echo "test from abc";
}
}
}
namespace def
{
class test
{
public function __construct()
{
echo "test from def";
}
}
use abc\test as abc;//run abc namespace
$obj1 = new abc();
$obj2 = new abc\test(); // it generate error due to same class available in current namespace
use def\test as def;//run def namespace
$obj2 = new def();
}
//global name space syntax
namespace
{
class test
{
public function __construct()
{
echo "test from global";
}
}
//use abc\test as abc;
$obj = new test();
}
note : Namespace work as directory structor.
namespace create as below syntax
namespace a/b/c/d //use as complate name or create alias
{
}
-------------------------------------------------------------------------------------------------------
Type Hinting : It is implement with function.It can also use with Interface and class.
Ex :
class test
{
function admin()
{
return 'Welcome Admin';
}
function user()
{
return 'Welcome User';
}
function till_user()
{
return 'Welcome Till User';
}
}
$utype = new test();
function user(test $utype)
{
echo $utype->user();
}
user($utype);
-------------------------------------------------------------------------------------------------------
Method Chaining : method chaining is called function chaining.Super Object And Sub Object is a part of
method chaining.
Ex :
class abc
{
public $value='ABC Class';
}
class xyz
{
public $abc;
public function __construct()
{
$this->abc = new abc();
}
}
$obj = new xyz();
echo $obj->abc->value; //Output : ABC Class
Note : In above example obj is super object and abc is sub object.
Method Chaining Example :
class abc
{
public function func1()
{
echo 'One';
return $this;//This syntax retun class object where this function call.
}
public function func2()
{
echo 'Two';
return $this;//This syntax retun class object where this function call.
}
public function func3()
{
echo 'Three';
return $this;//This syntax retun class object where this function call.
}
}
$obj = new abc();
$obj->func1()->func2()->func3();//Output : OneTwoThree
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Welcome To Magic Method
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Introduction : It is call automatically when object created.It is always start from __(Two times underscote).
autoload :
Ex : if you have lost of class file in specific folder,how to manage classes?
Ans : In above case , manage all the classes via autoload method.
solve via below mention code.
function __autoload($class_name)
{
$fname = "model/". $class_name .".php";
require_once($fname);
}
$abc = new abc();
Note : File name and class name both are same must be essential.
above code process : when create object,autoload check regarding class available or not.
if class is not include , it include automatically and provide access of class via object.
-------------------------------------------------------------------------------------------------------
construct : it is call automatically when object created.
ex :
In class file
class demo
{
public function __construct()
{
echo 'OK';
}
}
In index file
$obj = new demo(); // output : OK
-------------------------------------------------------------------------------------------------------
destructor : It is destroy object for free memory when object created.It is opposite againt constructor.
Syntax :
class demo
{
public function __destruct()
{
$this->disconnect();
}
}
-------------------------------------------------------------------------------------------------------
get : private and protected varible can not be use outside class or create object.this type of variables
and function can be access via get method.
Ex :
In class file :
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public fuction __get($name)
{
if(array_key_exists($name,$this->array))
{
return 'True'.'-'.$this->array[$name];
}
else
{
return 'False'.'-'.$this->array[$name];
}
}
}
In Index file
$abc = new abc();
echo $abc->xyz;//Output : False-xyz
echo $abc->abc;//Output : True-abc
Note : in $abc->abc syntax,we pass value in get function and response.
-------------------------------------------------------------------------------------------------------
set : It is opposite against get.It is use for set or change value in existing variable or array variable.
Ex :
In class file :
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public fuction __set($name,$value)
{
if(array_key_exists($name,$this->array))
{
return 'True'.'-'.$this->array[$name]=$value;
}
else
{
return 'False'.'-'.$this->array[$name];
}
}
}
In Index file
$abc = new abc();
echo $abc->abc;//Output : True-abc=hello abc
echo $abc->abc = 'Hello again abc';//Output : True-abc=hello again abc
-------------------------------------------------------------------------------------------------------
call : if you want to call non exist function or access private and protected variable or access private
and protected array variable using call method.
Syntax :
In Class file
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __call($name,$array)
{
return "Method name is : $name and it's parameter is : $array";
print_r($array);
}
}
class def
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __call($name,$array)
{
if(array_key_exists($name,$array))
{
return 'True';
}
}
}
In Index file
$abc = new abc();
echo $abc->create_user_type('admin','user');
//Output : Method name is : create_user_type and it's parameter is : Array([0]=>admin,[1]=>user)
echo $abc->def;
//Output : True
Note : when call function , it is check rearding avilable or not. If it is not available, it is create
function and get parameter after get response.
-------------------------------------------------------------------------------------------------------
callstatic : It is combination of static class and call megic method.both advantages include in callstatic.
if you want to call non function without create object via call static.
Syntax :
In Class file
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __callstatic($name,$array)
{
return "Method name is : $name and it's parameter is : $array";
print_r($array);
}
}
In Index file
include 'abc.php';
abc::create_user_type('admin','user');
//Output : Method name is : create_user_type and it's parameter is : Array([0]=>admin,[1]=>user)
echo $abc->def;
Note : when call function , it is check rearding avilable or not. If it is not available, it is create
function and get parameter after get response.
-------------------------------------------------------------------------------------------------------
isset : It is lots of use of avaibility like in session,if condition.isset magic method use for check
availability on variable and array variable when create object.
Syntax :
In Class file
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __isset($name)
{
if(isset($this->array[$name]))
{
return TRUE;
}
else
{
return FALSE;
}
}
}
In Index file
$obj = new abc();
echo $obj->abc; //Output : TRUE
-------------------------------------------------------------------------------------------------------
unset : It is againt isset which is use for remove value in variable or remove value in array elements.
Syntax :
In Class file
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __unset($name)
{
unset($this->array[$name]);
}
}
In Index file
$obj = new abc();
echo $obj->abc;
Note : call $obj->abc syntax remove element in array.
-------------------------------------------------------------------------------------------------------
tostring : if you call object name without function or variable,it generate error regarding convert to
string error.if you want access any private or protected variable or function using object
name,So how to access without constructor?
Ex. $abc = new abc(); echo $abc; //This type of syntax
if call above type of syntax,when call tostring magic method.
Syntax :
n Class file
class abc
{
private $array = ['abc'=>'hello abc','def'=>'hello def'];
public function __tostring()
{
return get_class();
}
}
In Index file
$obj = new abc();
echo $obj;//Output : abc
Note :
It is not receive any parameter,but it is return value as per in tostring function code block.
-------------------------------------------------------------------------------------------------------
sleep : It use for serialize.serialize mean object to string.unserialize mean string to object.
and object access using print_r.
Example :
class student
{
private $name;
private $roll_no;
function setName($name)
{
$this->name = $name;
}
function getName() {
return $this->name;
}
function setRn($cc) {
$this->roll_no = $cc;
}
function getRn() {
return $this->roll_no;
}
function __sleep() {
return array("name");
}
}
$obj = new student();
$obj->setName("abc");
$obj->setRn("101");
$data = serialize($obj);
echo $data; //Output : O:7:"student":1:{s:13:"studentname";s:6:"abc";}
print_r(unserialize($data));
//Output : student Object ( [name:student:private] => abc [roll_no:student:private] => 101 )
-------------------------------------------------------------------------------------------------------
invoke : if you want call object name as a function using invoke magic method.
Ex.$abc = new abc(); echo $abc('abc',def);
Example1 :
class test
{
public function __invoke($x,$y)
{
echo $x.'-'.$y;
}
}
$abc = new test();
echo $abc('abc','xyz')
//Output : abc-xyz
Example2 :
class test
{
public function abc()
{
return 'ABC';
}
public function def()
{
return 'DEF';
}
public function __invoke($n)
{
return $this->$n();
}
}
$abc = new test();
echo $abc('def'); //Output : DEF
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Welcome To OOP(Additional Notes)
-------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------
Notes :
->class is reserve keyword to create class.
->new keyword is use to create instance of class(Object of class).
->In function oveloading,parent constructor can be access by extended class using parent::construct();
->parent::construct() also use in function in above case.parent::myfunc();
-------------------------------------------------------------------------------------------------------
How to handle error in php?
ANS : In php,Handle access using try_catch block or try_catch_throw or try_catch_finally.
Example1
try
{
doStuff();
} catch(Exception $e)
{
do {
printf("%s:%d %s (%d) [%s]\n", $e->getFile(), $e->getLine(), $e->getMessage(), $e->getCode(), get_class($e));
} while($e = $e->getPrevious());
}
Example2
try
{}
catch(Exception $e)
{
throw new MyCustomException("Something happened", 911, $e);
}
Example3
try
{}
catch(Exception $ex)
{
echo $ex->getMessage();
}
finally
{
echo "Error In Programme";
}
notes : finally use for print messagge if error generate error.
-------------------------------------------------------------------------------------------------------
Types Of Error in Php.
ANS : Error hierarchy
Throwable
1)Error
1)Arithmatic Error :
Error occurs mathematical operations.
2)Assertion Error :
AssertionError is thrown when an assertion made via assert() fails.
3)Parse Error :
ParseError is thrown when an error occurs while parsing PHP code, such as when eval() is called.
4)Type Error :
There are three scenarios where a TypeError may be thrown. The first is where the argument type being
passed to a function does not match its corresponding declared parameter type. The second is where a
value being returned from a function does not match the declared function return type. The third is
where an invalid number of arguments are passed to a built-in PHP function (strict mode only).
5)DivisionByZero Error :
DivisionByZeroError is thrown when an attempt is made to divide a number by zero.
2)Exception
-------------------------------------------------------------------------------------------------------
Types of Exception :
getMessage : Gets Error in Message.
getPrevious : Gets previous Error
getCode : Gets the Exception code
getFile : Gets the file in which the exception occurred
getLine : Gets the line in which the exception occurred
getTraceAsString : Gets Error as string
Exaple :
try
{
test();
}
catch(Exception $e)
{
echo $e->getTraceAsString();
}
//Output
#0 /home/bjori/tmp/ex.php(7): test()
#1 {main}
getTrace : Gets Error in array
Example :
try
{
test();
}
catch(Exception $e)
{
var_dump($e->getTrace());
}
//Output
array(1) {
[0]=>
array(4) {
["file"]=>
string(22) "/home/bjori/tmp/ex.php"
["line"]=>
int(7)
["function"]=>
string(4) "test"
["args"]=>
array(0) {
}
}
-------------------------------------------------------------------------------------------------------
