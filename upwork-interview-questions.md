## The four types of variables in Ruby are as follows:

    Global variables begin with $ and are accessible from anywhere within the Ruby program regardless of where they are declared—it stands to reason that they must be handled with care.

    Local variables begin with a lowercase letter or an underscore. The scope of a local variable is confined to the code construct within which it is declared.

    Class variables begin with @@ and are shared by all instances of the class that it is defined in.

    Instance variables begin with @ and are similar to class variables except that they are local to a single instance of a class in which they are instantiated.

## Name the three levels of access control for Ruby methods.

    In Ruby, methods may either be public, protected, or private.
        *Public methods can be called by anyone.
        *Protected methods are only accessible within their defining class and its subclasses.
        *Private methods can only be accessed and viewed within their defining class
