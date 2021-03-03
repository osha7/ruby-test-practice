# 21 Essential Ruby Interview Questions

    https://www.toptal.com/ruby/interview-questions

## What will val1 and val2 equal after the code below is executed? Explain your answer.

    val1 = true and false  # hint: output of this statement in IRB is NOT value of val1!
    val2 = true && false

### Answer:

    val1 === true
    val2 === false

    *  employ and / or vs. && / ||
    * the and and or operators have lower precedence than the = operator, whereas the && and || operators have higher precedence than the = operator, based on order of operations

## Which of the expressions listed below will result in "false"?

    true    ? "true" : "false"
    false   ? "true" : "false"
    nil     ? "true" : "false"
    1       ? "true" : "false"
    0       ? "true" : "false"
    "false" ? "true" : "false"
    ""      ? "true" : "false"
    []      ? "true" : "false"

### Answer:

    false   ? "true" : "false"
    nil     ? "true" : "false"

    * 0 is not a false value in Ruby

## What will be the result of each of the following lines of code:

    def times_two(arg1);
        puts arg1 * 2;
    end

    def sum(arg1, arg2);
        puts arg1 + arg2;
    end

    times_two 5
    times_two(5)
    times_two (5)
    sum 1, 2
    sum(1, 2)
    sum (1, 2)

### Answer:

    The first three lines of code will all print out 10, as expected.
    The next two lines of code will both print out 3, as expected.

    However, the last line of code (i.e., sum (1,2)) will result in the following:
    syntax error, unexpected ',', expecting ')'
    sum (1, 2)
       ^
        The problem is the space between the method name and the open parenthesis. Because of the space, the Ruby parser thinks that (1, 2) is an expression that represents a single argument, but (1, 2) is not a valid Ruby expression, hence the error.

        Note that the problem does not occur with single argument methods (as shown with our timesTwo method above), since the single value is a valid expression (e.g., (5) is a valid expression which simply evaluates to 5).

## Consider the following code:

    VAL = 'Global'

    module Foo
        VAL = 'Foo Local'

        class Bar
            def value1
            VAL
            end
        end
    end

    class Foo::Bar
        def value2
            VAL
        end
    end

### What will be the value of each of the following:

    Foo::Bar.new.value1
    Foo::Bar.new.value2

### Answer:

    Foo::Bar.new.value1 will be equal to 'Foo Local' and Foo::Bar.new.value2 will be equal to 'Global'.

    Here’s why:

    The module keyword (as well as the class and def keywords) will create a new lexical scope for all of its contents. The above module Foo therefore creates the scope Foo in which the VAL constant equal to 'Foo Local' is defined. Inside Foo, we declare class Bar, which creates another new lexical scope (named Foo::Bar) which also has access to its parent scope (i.e., Foo) and all of its constants.

    However, when we then declare Foo::Bar (i.e., using ::), we are actually creating yet another lexical scope, which is also named Foo::Bar (how’s that for confusing!). However, this lexical scope has no parent (i.e., it is entirely independent of the lexcial scope Foo created earlier) and therefore does not have any access to the contents of the ‘Foo’ scope. Therefore, inside class Foo::Bar, we only have access to the VAL constant declared at the beginning of the script (i.e., outside of any module) with the value 'Global'.

## Is the line of code below valid Ruby code? If so, what does it do? Explain your answer.

    -> (a) {p a}["Hello world"]

### Answer:

    2.6.1 :001 > -> (a) {p a}["Hello world"]
    "Hello world"
    => "Hello world"


    Yes, it’s valid. Here’s how to understand what it does:

    The -> operator creates a new Proc, which is one of Ruby’s function types. (The -> is often called the “stabby proc”. It’s also called the “stabby lambda”, as it creates a new Proc instance that is a lambda. All lambdas are Procs, but not all Procs are lambdas. There are some slight differences between the two.)

    This particular Proc takes one parameter (namely, a). When the Proc is called, Ruby executes the block p a, which is the equivalent of puts(a.inspect) (a subtle, but useful, difference which is why p is sometimes better than puts for debugging). So this Proc simply prints out the string that is passed to it.

    You can call a Proc by using either the call method on Proc, or by using the square bracket syntax, so this line of code also invokes the Proc and passes it the string “Hello World”.

    So putting that all together, this line of code (a) creates a Proc that takes a single parameter a which it prints out and (b) invokes that Proc and passes it the string “Hello world”. So, in short, this line of code prints “Hello World”.
