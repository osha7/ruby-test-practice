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
