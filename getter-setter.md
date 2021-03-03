# Getter

    -A getter method is a method that gets a value of an instance variable.
    Without a getter method, you can not retrieve a value of an instance variable outside the class the instance variable is instantiated from.


    class Movie
        def initialize(name)
            @name = name
        end

        def name
            @name
        end
    end

    obj1 = Movie.new('Forrest Gump')
    p obj1.name #=> "Forrest Gump"

# Setter

    -A setter is a method that sets a value of an instance variable.
    Without a setter method, you can not assign a value to an instance variable outside its class.
    if you try to set a value of an instance variable outside its class, Ruby raises No Method Error just like it does when you try to retrieve a value of an instance variable outside its class without a getter method.


    class Movie
        def initialize(name)
            @name = name
        end

        def name #getter method
            @name
        end

        def name=(name) #setter method
            @name = name
        end
    end

    obj1 = Movie.new('Forrest Gump')
    p obj1.name #=> "Forrest Gump"
    obj1.name = 'Fight Club'
    p obj1.name #=> "Fight Club"

# Accessors

    -Accessors are a way to create getter and setter methods without explicitly defining them in a class.

    -three types fo accessors in Ruby:

    attr_reader
        *automatically generates a getter method for each given attribute.
    attr_writer
        *automatically generates a setter method for each given attribute.
    attr_accessor
        *automatically generates a getter and setter method for each given attribute.

    -------------------------------------------------
    class Movie
        attr_reader :name, :year
        attr_writer :name, :year

        def initialize(name, year)
            @name = name
            @year = year
        end
    end

    obj1 = Movie.new('Forrest Gump', 1994)
    obj1.name = 'Fight Club'
    obj1.year = 1999
    p obj1.name #=> "Fight Club"
    p obj1.year #=> 1999


    class Movie
        attr_accessor :name, :year

        def initialize(name, year)
            @name = name
            @year = year
        end
    end

    obj1 = Movie.new('Forrest Gump', 1994)
    obj1.name = 'Fight Club'
    obj1.year = 1999
    p obj1.name #=> "Fight Club"
    p obj1.year #=> 1999
