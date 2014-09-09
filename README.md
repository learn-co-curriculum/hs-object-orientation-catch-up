# Object Orientation Refresher


### Classes and Instances

A class is a sort of 'blueprint' or 'template' for making standardized versions of items. Any object in the real world can be modeled as an object in code. For example, here's a model for a coffee cup.

```ruby
class CoffeeCup

end
```
To create an individual version (known as an *instance* or *object*) of our class, we use the `.new` method on the class to create the instance:
```
first_cup = CoffeeCup.new
```
### Attributes

All objects can be described. For example, a coffee cup has a width, a height, a color, etc. We can add descriptors (known as *attributes*) to our model by using writer and reader methods. A writer is like a statement telling your object “You are this tall” or “Your color is blue”. A reader is more like a question asking the instance: “How tall are you?” or “What is your color?” A reader is usually a method that somehow describes the attribute, while a method uses the `=` with an argument to set or change the attribute.

A writer that takes in a color as an argument and sets it to the @color variable:
```
def color=(color)
  @color = color
end
```

A reader that returns the @color variable:
```
def color
  @color
end
```

Note: We use `@variables` because they allow for variables to be accessed from different methods, as opposed to `variables` (without the @ sign) that are local in scope and can't be read between methods.

### Initialize

We can add an `initialize` method to run code whenever a new object is created using `.new` - It's like automatic code that gets run without being called explicitly.

```RUBY
class CoffeeCup
  def initialize
    @color = "white"
  end

  def color=(color)
    @color = color
  end

  def color
    @color
  end
end
```
In the example above, when a new instance of CoffeeCup is created, it *automatically* has its color attribute set to white, because we set it in the initialize method. (This makes sense, because coffee cups are always white until they get painted!)

You can also set your initialize method to take in arguments. For example, when a new cup is created, it has a size from the start. We want to be able to create an instance of a large cup by running `CoffeeCup.new("Large")`. TO do this, we add an argument to the initialize method:

```
def initialize(size)
  @size = size
  @color = "white"
end  
```

### Object Actions

Not only do objects have attributes (descriptors), they also have *actions*. For example, you can have an action called `spill` on the coffee cup class that changes an attribute called `current_volume` to "empty" or 0. Actions are methods that change the object itself or other objects that it interacts with.

```
class CoffeeCup

  def current_volume=(volume)
    @volume = volume
  end

  def current_volume
    @volume
  end

  def spill
    @volume = "empty"
  end

  def fill
    @volume = "full"
  end

end

```

Let's Put it all together:

class CoffeeCup
  def initialize(size)
    @size = size
    @color = "white"
  end

  def color=(color)
    @color = color
  end

  def color
    @color
  end

  def size=(size)
    @size
  end

  def size
    @size
  end
  
  def current_volume=(volume)
    @volume = volume
  end

  def current_volume
    @volume
  end

  def spill
    @volume = "empty"
  end

  def fill
    @volume = "full"
  end

end

```

Now we can create a new coffee cup instance:

```
 my_cup = CoffeeCup.new("Medium")
 my_cup.color #=> returns "white" becuase it is set in initialize
 my_cup.size #=> returns "medium"
 my_cup.color="red"
 my_cup.color #=> returns "red"
 my_cup.fill
 my_cup.current_volume #=> Returns "full"
 my_cup.spill
 my_cup.current_volume #=> Returns "empty"
```

Check out the resources section for more on Object Orientation!
