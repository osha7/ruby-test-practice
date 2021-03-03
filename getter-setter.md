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
