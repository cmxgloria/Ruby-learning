# OBJECT-ORIENTED PROGRAMMING I

## Why Classes?
Ruby is an object-oriented programming language, which means it manipulates programming constructs called objects. (Almost) everything in Ruby is an object! You’ve been using them all along, so they should be very familiar. Objects have methods, which you’ve seen before, and attributes, which are just data. For instance, in

"Matz".length
# ==> 4

```
class Language
  def initialize(name, creator)
    @name = name
    @creator = creator
  end
	
  def description
    puts "I'm #{@name} and I was created by #{@creator}!"
  end
end

ruby = Language.new("Ruby", "Yukihiro Matsumoto")
python = Language.new("Python", "Guido van Rossum")
javascript = Language.new("JavaScript", "Brendan Eich")

ruby.description
python.description
javascript.description
```
#I'm Ruby and I was created by Yukihiro Matsumoto!
I'm Python and I was created by Guido van Rossum!
I'm JavaScript and I was created by Brendan Eich!

What's in a @name?
In Ruby, we use @ before a variable to signify that it’s an instance variable. This means that the variable is attached to the instance of the class.
```
class Car
  def initialize(make, model) 
    @make = make
    @model = model
  end
end

kitt = Car.new("Pontiac", "Trans Am")
```

Instant your first object
```
class Person
	def initialize(name)
    @name = name
  end
end

matz = Person.new("Yukihiro")
```

Scope it Out
When dealing with classes, you can have variables that are available everywhere (global variables), ones that are only available inside certain methods (local variables), others that are members of a certain class (class variables), and variables that are only available to particular instances of a class (instance variables).

Check out the code in the editor. See how some variables start with $, @, or @@? This helps mark them as global, instance, and class variables (respectively). We’ll explain these in the next section. Run the code to see how these different variables work!


```
class Computer
  $manufacturer = "Mango Computer, Inc."
  @@files = {hello: "Hello, world!"}
  
  def initialize(username, password)
    @username = username
    @password = password
  end
  
  def current_user
    @username
  end
  
  def self.display_files
    @@files
  end
end

# Make a new Computer instance:
hal = Computer.new("Dave", 12345)

puts "Current user: #{hal.current_user}"
# @username belongs to the hal instance.

puts "Manufacturer: #{$manufacturer}"
# $manufacturer is global! We can get it directly.

puts "Files: #{Computer.display_files}"
# @@files belongs to the Computer class.
```
#Current user: Dave
Manufacturer: Mango Computer, Inc.
Files: {:hello=>"Hello, world!"}


Naming Your Variables
Recall that instance variables begin with an @. This isn’t just a Ruby convention—it’s part of the syntax! Always start your instance variables with @.

Class variables are like instance variables, but instead of belonging to an instance of a class, they belong to the class itself. Class variables always start with two @s, like so: @@files.

Global variables can be declared in two ways. The first is one that’s already familiar to you: you just define the variable outside of any method or class, and voilà! It’s global. If you want to make a variable global from inside a method or class, just start it with a $, like so: $matz.
```
class MyClass
  $my_variable = "Hello!"
end

puts $my_variable
```

Twice the @, Twice as Classy
We can create class variables by starting a variable name with two @ symbols. Class variables are attached to entire classes, not just instances of classes, like so:

class MyClass
  @@class_variable
end
Because there’s only one copy of a class variable shared by all instances of a class, we can use them to pull off some cool Ruby tricks. For example, we can use a class variable to keep track of the number of instances of that class we’ve created. 

```
class Person
  # Set your class variable to 0 on line 3
  @@people_count = 0
  
  def initialize(name)
    @name = name
    # Increment your class variable on line 8
    @@people_count += 1
  end
  
  def self.number_of_instances
    # Return your class variable on line 13
    return @@people_count
  end
end

matz = Person.new("Yukihiro")
dhh = Person.new("David")

puts "Number of Person instances: #{Person.number_of_instances}"
```
#Number of Person instances: 2

Classes Are Serious Business
 Here we have a snippet of the Rails source code. See how they’ve created an instance of the RecordInvalid class?

Instructions
Most of the syntax should look familiar to you; the raise bit (which we’ll cover in future lessons) generates a new RecordInvalid error if the user tries to create or save an invalid record.
```
def create_record(attributes, raise_error = false)
  record = build_record(attributes)
  yield(record) if block_given?
  saved = record.save
  set_new_record(record)
  raise RecordInvalid.new(record) if !saved && raise_error
  record
end
```
Watch Your Step
Inheritance is a tricky concept, so let’s go through it step by step.

Inheritance is the process by which one class takes on the attributes and methods of another, and it’s used to express an is-a relationship. For example, a cartoon fox is a cartoon mammal, so a CartoonFox class could inherit from a CartoonMammal class.

Check out the code in the editor. We’ve defined a class, ApplicationError, as well as a SuperBadError class that inherits from ApplicationError. Note that we don’t define the display_error method in the body of SuperBadError, but it will still have access to that method via inheritance. Click Run to see for yourself!

```
class ApplicationError
  def display_error
    puts "Error! Error!"
  end
end

class SuperBadError < ApplicationError
end

err = SuperBadError.new
err.display_error
```
#Error! Error!

Inheritance Syntax
In Ruby, inheritance works like this:

class DerivedClass < BaseClass
  # Some stuff!
end

sample
```
class Application
  def initialize(name)
    @name = name
  end
end
class MyApp < Application
end
```

Override!
.
Let’s try a more entertaining (if less realistic) example. Create a new class, Dragon, that inherits from Creature. Give your derived class a fight method that overrides Creature‘s; instead of returning “Punch to the chops!”, it should return “Breathes fire!”.

```
class Creature
  def initialize(name)
    @name = name
  end
  
  def fight
    return "Punch to the chops!"
  end
end

class Dragon < Creature
  def fight
    return "Breathes fire!"
  end
end

```
When Good isn't Good Enough
The syntax looks like this:

class DerivedClass < Base
  def some_method
    super(optional args)
      # Some stuff
    end
  end
end
When you call super from inside a method, that tells Ruby to look in the superclass of the current class and find a method with the same name as the one from which super is called. If it finds it, Ruby will use the superclass’ version of the method.
```
class Creature
  def initialize(name)
    @name = name
  end
  def fight
    return "Punch to the chops!"
  end
end
class Dragon < Creature
  def fight
    puts "Instead of breathing fire. . . "
    super
  end
end
```

There Can Be Only One!
Any given Ruby class can have only one superclass. Some languages allow a class to have more than one parent, which is a model called multiple inheritance. This can get really ugly really fast, which is why Ruby disallows it.
```
class Creature
  def initialize(name)
    @name = name
  end
end

class Person
  def initialize(name)
    @name = name
  end
end

class Dragon < Creature; end
class Dragon < Person; end
```
#superclass mismatch for class Dragon

Class Basics

```
class Message
  def initialize(from, to)
    @from = from
    @to = to
  end
end

```

Getting Classier
```
class Message 
  @@messages_sent = 0
  def initialize(from, to)
    @from = from 
    @to = to 
    @@messages_sent +=1 
  end
end
```

Forge an Object in the Fires of Mount Ruby
```
class Message 
  @@messages_sent = 0
  def initialize(from, to)
    @from = from 
    @to = to 
    @@messages_sent +=1 
  end
end

my_message = Message.new("Ian", "Alex")
```

Inheriting a Fortune
```
class Message 
  @@messages_sent = 0
  def initialize(from, to)
    @from = from 
    @to = to 
    @@messages_sent +=1 
  end
end

class Email < Message
  def initialize(subject)
    @subject = subject
  end
end

my_message = Message.new("Ian", "Alex")

```

Up, Up, and Away!
```
class Message 
  @@messages_sent = 0
  def initialize(from, to)
    @from = from 
    @to = to 
    @@messages_sent +=1 
  end
end

class Email < Message
  def initialize(from, to)
    super
  end
end

my_message = Message.new("Ian", "Alex")

```


# VIRTUAL COMPUTER

What You'll Be Building
Now that you’ve learned all about classes and objects in Ruby, you can create any kind of Ruby object your heart desires. In this project, we’ll use our newfound knowledge to create a class, Machine, and generate instances of that class that can manipulate imaginary files for us.
```
class Machine
  @@users = {}
  
  def initialize(username, password)
    @username = username
    @password = password
    @@users[username] = password
    @files = {}
  end
  
  def create(filename)
    time = Time.now
    @files[filename] = time
    puts "#{filename} was created by #{@username} at #{time}."
  end
  
  def Machine.get_users
    @@users
  end
end

my_machine = Machine.new("eric", 01234)
your_machine = Machine.new("you", 56789)

my_machine.create("groceries.txt")
your_machine.create("todo.txt")

puts "Users: #{Machine.get_users}"
```
#groceries.txt was created by eric at 2019-07-22 04:34:57 +0000.
todo.txt was created by you at 2019-07-22 04:34:57 +0000.
Users: {"eric"=>668, "you"=>56789}

Have a little class
Add a class variable called @@users to your Computer class. Set it equal to an empty hash.

In your initialize method, set @@users[username] = password so that your @@users hash keeps usernames as keys with each username’s password as the associated value.
```
class Computer
  @@users = {}
  def initialize(username, password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
  end
end
```

Getting More Creative
Inside your Computer class, define a method called create with a single parameter, filename.

Inside create, declare a variable called time and set it equal to the current time (using Time.now).

Next, inside create, add a new key/value pair to the @files hash. Use the filename key to store the value time.

For the final step in create, please puts a message telling the user that a new file was created. Feel free to put in any information you like; the one we used in exercise 1 printed the filename, the username, and the time.
```
class Computer
  @@users = {}
  def initialize(username, password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
  end
  
  def create(filename)
    time = Time.now
    @files[filename] = time
    puts "#{filename} was created at #{time} by #{@username}. "
  end
end
```

Who are the users?
```
class Computer
  @@users = {}
  def initialize(username, password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
  end
  
  def create(filename)
    time = Time.now
    @files[filename] = time
    puts "#{filename} was created at #{time} by #{@username}. "
  end
  
  def Computer.get_users
    @@users
  end
end
```

Instantiation Nation
Excellent! Last step: let’s create an instance of our Computer class.

You’ve done this before, but here’s a refresher.
```
class Person
  def initialize(name)
    @name = name
  end
end

emma = Person.new("emma")
```

In the example above, we first define a Person class with an initialize method.
Then, we create a new instance of Person and store it in a new variable called emma.

```
class Computer
  @@users = {}
  def initialize(username, password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
  end
  
  def create(filename)
    time = Time.now
    @files[filename] = time
    puts "#{filename} was created at #{time} by #{@username}. "
  end
  
  def Computer.get_users
    @@users
  end
end

my_computer = Computer.new("superUser", "12345")
```
You did it.
```
class Computer
  @@users = {}
  def initialize(username, password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
  end
  
  def create(filename)
    time = Time.now
    @files[filename] = time
    puts "#{filename} was created at #{time} by #{@username}. "
  end
  
  def Computer.get_users
    @@users
  end
end

my_computer = Computer.new("superUser", "12345")
my_computer.create('grocery')
```

# BANKING ON RUBY
What You'll Be Building
```
class Account
  attr_reader :name, :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
  
  def display_balance(pin_number)
    puts pin_number == pin ? "Balance: $#{@balance}." : pin_error
  end
  
  def withdraw(pin_number, amount)
    if pin_number == pin
      @balance -= amount
      puts "Withdrew #{amount}. New balance: $#{@balance}."
    else
      puts pin_error
    end
  end
  
  private
  
  def pin
    @pin = 1234
  end 
  
  def pin_error
    "Access denied: incorrect PIN."
  end
end

my_account = Account.new("Eric", 1_000_000)
my_account.withdraw(11, 500_000)
my_account.display_balance(1234)
my_account.withdraw(1234, 500_000)
my_account.display_balance(1234)
```

Create an account class
```
class Account
  attr_reader :name, :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
end
```

Private Affairs
```
class Account
  attr_reader :name
  attr_reader :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end

  private
  def pin
    @pin = 1234
  end
  def pin_error
    return "Access denied: incorrect PIN."
  end 
end
```

Displaying the Balance
Something important to note: you can explicitly declare your public methods public, or you can omit public and your methods will be public by default. However! If you don’t use public, you need to put your public methods before the private keyword, since private affects every method after it appears. If you put your public methods below private and don’t label them public, they’ll be private, too!
```
class Account
  attr_reader :name
  attr_reader :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
   def display_balance(pin_number)
    puts pin_number == pin ? "Balance: $#{@balance}" : "pin_error"
   end

  private
  def pin
    @pin = 1234
  end
  def pin_error
    return "Access denied: incorrect PIN."
  end 
 
end
```

Making a Withdrawal
Now let’s add in our second public method, which will allow us to withdraw money from our account.

The trick to this one is to realize that since @balance can only be accessed from inside the class, we’ll want to use @balance -= amount to decrease the balance by a certain amount.

``
class Account
  attr_reader :name
  attr_reader :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
  
  public
  def display_balance(pin_number)
    if pin_number == @pin
      puts "Balance: $#{@balance}."
    else
      puts pin_error
    end
  end
  
  def withdraw(pin_number,amount)
    if pin_number == @pin
      @balance -= amount
      puts "Withdrew #{amount}."
    else
      puts pin_error
    end
  end

  private
  def pin
    @pin = 1234
  end
  def pin_error
    return "Access denied: incorrect PIN."
  end 
end
```

Opening an Account
```
class Account
  attr_reader :name
  attr_reader :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
  
  public
  def display_balance(pin_number)
    if pin_number == @pin
      puts "Balance: $#{@balance}."
    else
      puts pin_error
    end
  end
  
  def withdraw(pin_number,amount)
    if pin_number == @pin
      @balance -= amount
      puts "Withdrew #{amount}."
    else
      puts pin_error
    end
  end

  private
  def pin
    @pin = 1234
  end
  def pin_error
    return "Access denied: incorrect PIN."
  end 
end

checking_account = Account.new("Eric", 1_000_000)
```

