---------------------------
    OS MODULE
---------------------------

|      Method    |   Given     |  Return     |
|----------------|-------------|-------------|
| os.getcwd()      |    |     return current  working dir   (string)|
|os.chdir(path)|   path(string)    |   it change the current working dir   |
|os.listdir()| | return a list of file in cwd |
| os.mkdir(name) | name(string) | create a dir by the name |
|os.makedirs(name)| name(string)| create a few intermediate level dir |
| os.removedirs(name) | name(string) | remove dirs recursively |
|os.rename(src, dst)| src(string) , dst(string)| rename the src to dst |
|os.stat(name)| name(string) | return an stat_result object that has many property|
|os.walk(path)| path(string total path) | return tuple (dirpath(folder path), dirname(folder), filename)|
|os.environ| | return an dictionary|


----------------------------------------
    os.path module
----------------------------------------

|   Method    |    Given      |   Return      |
|-------------|---------------|---------------|
| os.path.join(path, *paths) | path(str), *paths(many str) | return the str name of the join path|
|os.path.basename(path)| path(string)| return last file name in the path|
|os.path.dirname(path)| path(str) | return the dirname where last file exist in the path|
|os.path.split(path)| path(str)| return (head, tail) where tail is the last pathname component and head is the everything leading up to that|
|os.path.exists(path)| path(str)| return boolean if path is exist or not|
|os.path.isdir(path)| path(str)| return true if the path is a dir|
|os.path.isfile(path)| path(str)| return true if the path is a file|
|os.path.splitext(path)| path(str) | return a pair (root, ext) such that root + ext = path|
| `__file__` | | return the current runable file path|
|os.path.abspath( path )| path(str) | return the normalized absolute pathname of the path|


-----------------------------------------
## First class function
-----------------------------------------

* function return a function

1. function assign to a variable, 

2. function pass through an argument, 

3. function return by a function.

```python
def get_start(tag):
    link = None;

    def get_link(msg):
        link = f'<{tag}>{msg}</{tag}>'
        return link;

    return get_link;


g = get_start('h2')
c = g('hi Rahul')

print(c)
```



![](https://sebastianraschka.com/images/blog/2014/scope_resolution_legb_rule/scope_resolution_1.png)



----------------------------
         Decorators 
----------------------------

* LEGB rule in python

* if we define a variable in local scope like in function we can not get it back after
the function call. But using Decorator we can get back the variable. 

```python

def message():
    # this is the local variable
    msg = 'Ha ha ha :)'

    def myfun():
        print(msg);

    return myfun;


m = message();

print('hi rahul')

m()
```

```python

def decorator_function(original_function):
    def wrapper_function():
        return original_function()

    return wrapper_function;


def cal():
    return 3 * 3;


decorator_fun = decorator_function(cal);

print(decorator_fun())
```
