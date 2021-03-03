# Interview Questions

    https://www.javatpoint.com/ruby-interview-questions

## Four types of variables in Ruby

    *Local variable
    *Class variable
    *Instance variable
    *Global variable

## What is the difference between nil and false in Ruby?

    nil vs false
    nil cannot be a value. false can be a value.
    nil is returned where there is no predicate. in case of a predicate, true or false is returned by a method.
    nil is not a boolean data type. false is a boolean data type.
    nil is an object of nilclass. false is an object of falseclass.

## Ruby data types

    Numbers
    Strings
    Symbols
    Hashes
    Arrays
    Booleans

## Case statement in Ruby

    In Ruby, we use 'case' instead of 'switch' and 'when' instead of 'case'. The case statement matches one statement with multiple conditions just like a switch statement in other languages.

## How will you comment in Ruby.

    Ruby comments are non-executable lines in a program. They do not take part in the execution of a program.

    Single line comment syntax:

    #This is single line comment.
    Multi line comment syntax:

    =begin
    This
    is
    multi line
    comment
    =end

## create Ruby object

    objectName=className.new

## What are Ruby blocks

    Ruby code blocks are called closures in other programming languages. It consist of a group of codes which is always enclosed with braces or written between do...end

### multi-line block

    [10, 20, 30].each do |n|
        puts n
    end

### inline block

    [10, 20, 30].each {|n| puts n}

## The yield statement

    The yield statement is used to call a block within a method with a value.

    Example:

    #!/usr/bin/ruby

    def met
        puts "This is method"
        yield
        puts "You will be back to method"
        yield
    end
    met {puts "This is block"}


    def met
        yield 1
        puts "This is method"
        yield 2
    end
    met {|i| puts "This is block #{i}"}


    x = "Outer variable"
    3.times do |x|
      puts "Inside the block: #{x}"
    end
    puts "Outside the block: #{x}"


    BEGIN {
        puts "code block is being loaded"
    }

    END {
        puts "code block has been loaded"
    }
    puts "This is the code block"

            ==> "code block is being loaded"
            ==> "This is the code block"
            ==> "code block has been loaded"


        class Novel
            attr_accessor :pages, :category

            def initialize
                yield(self)
            end
        end

        novel = Novel.new do |n|
        n.pages = 564
        n.category = "thriller"
        end

        puts "I am reading a #{novel.category} novel which has #{novel.pages} pages."

## What is yield statement in Ruby.

    The yield statement is used to call a block within a method with a value.
