arguments and decorators            Write all your code in a single file named homework.py and upload it to Grader Than. 

Hint:
Here is the general syntax for a decorator that accepts no arguments:

def decorator(decorated_function:callable):
    def wrapper_function(*args, **kwargs):
        #this is where we make modifications to the arguments before invoking the decorated function
        return_value = decorated_function(*args, **kwargs)
        #this is where we make modifications to the returned value after invoking the decorated function
        return return_value
    return wrapper_function
 

def reverse_decorator(function:callable):
This question is meant to test your knowledge of creating a decorator to decorate a function that accepts no arguments and alters the decorated function's output. This decorator will decorate a function that only returns strings and has no arguments. This decorator should reverse the string value returned by the decorated function and return the reversed string. In other words, if a function is decorated by this decorator all of the functional output should be the reverse of its normal output. 

def shorten_args_decorator(function:callable):
This question is meant to test your knowledge of creating a decorator to decorate a function that accepts an arbitrary number of positional and keyword arguments and alters the arguments before passing them to the decorated function. This decorator will truncate the number of positional arguments to 3 if the total number of positional arguments is greater then 3. The order of the positional arguments must be maintained. It will then pass the truncated form of the positional arguments to the decorated function upon invocation. This decorator will not make any modifications to the keyword arguments.  

def time_out_decorator(time_out:int):
This question is meant to test your knowledge of creating a decorator that accepts arguments, to decorate a function that accepts an arbitrary number of positional and keyword arguments, and to execute code before and after the decorated function's invocation. This decorator will time the execution time of the decorated function. The decorator will be constructed with an argument known as time_out. If the total execution time of the decorated function is greater than the time_out time the decorator should raise a TimeoutError, otherwise it should return the value returned from the decorated function. time_out will be an int denoting milliseconds.     

def kwargs_to_args_decorator(*args, **kwargs):
This question is meant to test your knowledge of creating a decorator that accepts an arbitrary number of positional and keyword arguments, to decorate a function that accepts an arbitrary number of positional and keyword arguments, and alters the arguments before passing them to the decorated function. When the decorated function is invoked, this decorator should modify the arguments the decorated function receives. This decorator should filter out all positional arguments passed to the decorated function, which are found in the positional arguments passed to the decorator when the decorator was initialized. It should also filter out all keyword arguments with keys that are found in the keyword arguments given to the decorator when the decorator was initialized. After performing the modifications to the arguments, the decorator should invoke the decorated function with the modified arguments and return the value of the decorated function.   

def function(*args, **kwargs):
This question is meant to test your understanding of how to work with an arbitrary number of positional arguments and keyword arguments. The main goal of this function is to assure that the types and values of the arguments meet a set of criteria. This is not a decorator, this is a traditional function. The argument criteria are as follows:

There is no guarantee the function will recieve positional arguments. If it does have positional arguments the function should follow these rules:
If the function is invoked with positional arguments, the first positional argument must be a string less than 11 characters long. If the first argument is not a string, the function should raise a TypeErrror. If the first argument has more then 10 characters it should raise a ValueError. 
If the function is invoked with more than one positional argument, all arguments after the first positional argument must be an int, greater then or equal to 0. If any positional argument after the first value is not of type int the function should raise a TypeError. If any positional argument after the first value is less then 0, the function should raise a ValueError.
The function expects there to be a keyword argument associated with the keys 'taco' and 'potato'. If one or both of those keys are not found in the keyword arguments then the function should raise a KeyError.
The function expects there to be a keyword argument associated with a key equal to the value of the first positional argument. If the key does not exist in the keyword arguments, the function should raise a KeyError. If the value associated with that key is not a string the function should raise a TypeErrror. If the value associated with that key has more then 10 characters is should raise a ValueError. If there are no positional arguments then the function should skip this test.   
Examples:

args = (96, 6, 34) kwargs = {'taco': 'showman', 'potato': 'walkway', '96': '5'}

This should raise a type error because the first positional argument is not a str.

args = ('TRZJRE6MLCDN', 10, 88, 49) kwargs = {'taco': 'Juneau', 'potato': 'conservative', 'TRZJRE6MLCDN': 'V'}

This should raise a value error because the first positional argument is greater then 10 charactures.

args = ('3I7', 'dean', 48, 'bream', 62, 'cryostat', 31, 'Bruegel', 16, 'delicatessen', 6, 'Millie', 12, 'loss', 70) kwargs = {'taco': 'Heidegger', 'potato': 'grim', '3I7': 'P'}

This should raise a type error because the positional arguments after the first value are not of type int.

args = ('BPW', -77, -71, -81, -31, -21) kwargs = {'taco': 'feeble', 'potato': 'geyser', 'BPW': 'U'}

This should raise a value error because the positional arguments after the first value are less than zero.

args = ('V', 83, 91, 17, 1, 59, 49, 86, 62, 63) kwargs = {'potato': 'virulent', 'V': 'J'}

This should raise a key error because the key 'taco' is missing in the key word arguments.

args = ('Z', 23, 20, 82, 11) kwargs = {'taco': 'Permian', 'Z': 'H'}

This should raise a key error because the key 'potato' is missing in the key word arguments.

args = ('J', 90, 83, 61, 27) kwargs = {'taco': 'imputation', 'potato': 'indolent'}

This should raise a key error because a key equal to the first positional argument, is missing in the key word arguments.

args = ('88', 56, 69, 29, 97, 79) kwargs = {'taco': 'Conant', 'potato': 'strung', '88': 90}

This should raise a key error because the value associated with the key equal to the first positional argument is not a str.

args = ('FMF', 47) kwargs = {'taco': 'gazpacho', 'potato': 'bunkmate', 'FMF': 'JYMQEC37LSLX'}

This should raise a key error because the value associated with the key equal to the first positional argument is more then 10 charactures.

args = () kwargs = {'taco': 'smuggle', 'potato': 'committeemen'}

This is valid input

args = ('BYJT', 36, 29) kwargs = {'taco': 'phosgene', 'potato': 'pastel', 'BYJT': 'C'}

This is valid input

args = ('018J',) kwargs = {'taco': 'Marx', 'potato': 'tetrafluoride', '018J': 'D'}

This is valid input
