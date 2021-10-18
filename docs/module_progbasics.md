# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
> #### A list is used to store data in a sequence and modify it anytime you want. Some of the more known list methods are `list.append()`, `list.remove()`, `list.index()` and `list.sort()`.
#### What is the difference between a list/array and a set?
> #### A set is unordered(doesn't have indexed elements), unlike a list.
#### What is the purpose and methods of a dictionary/map data structure?
> #### Dictionaries are used to store data as a set "key: value" pairs where only the keys must be immutable. Some common dictionary methods are `dict.update()`, `dict.get()`, `dict.pop()`, `dict.keys()`, `dict.values()`, `dict.items()`.

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
```py
i = 0
j = 1
while j > 0:
    print(i)
    i, j = j, j + i
    input()
```
#### How do you find a max value in a list/array if you can’t use any built-in functions?
```py
def max(num_list):
    largest = num_list[0]
    for num in num_list:
        if num > largest:
            largest = num
    return largest
```
#### How do you find the average of values in a list/array if you can’t use any built-in functions?
```py
def average(num_list):
    length = 0
    for num in num_list:
        sum += num
        length += 1
    average = sum / length
```
#### What do we call an *in-place* sort?
#### Any sort that sorts the original list and not a copy of said list. For example:
```py
In [9]: a_list = [1, 200, 58, -17, 23]

In [10]: a_list.sort()

In [11]: a_list
Out[11]: [-17, 1, 23, 58, 200]
```
#### Explain an algorithm which sorts a list!
> #### An insertion sort compares values in a list, and if a value is smaller than the value on its left, the value is moved further left until it's bigger than the values to its left.

### Programming paradigms - procedural

#### What is the call stack?
> #### It's a data structure which stores information about the functions that have been called and waiting to be finished in the program.
#### What is “Stack overflow”?
> #### It refers to the program running out of memory to allocate for another function call on top of the call stack.
#### What are the main parts of a function?
> #### Definition, parameters and function name

### Programming languages - Python  
#### How do you use a dictionary in Python?
> #### Dictionaries are used to store data as a set "key: value" pairs where only the keys must be immutable. Some common dictionary methods are `dict.update()`, `dict.get()`, `dict.pop()`, `dict.keys()`, `dict.values()`, `dict.items()`.
#### What does it mean that an object is immutable in Python?
> #### An immutable object can be modified.
#### What is a conditional expression in Python?
> #### It is an expression that checks whether a condition is `True` or `False`, only computing if the condition is `True`.
#### What are different types of arguments in Python?
> #### Positional arguments and keyword arguments.
#### What is variable shadowing? (context: variable scope)
> #### Variable shadowing occurs when a variable declared within a certain scope has the same name as a variable declared in an outer scope.
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
> #### The iterated list will be modified as many times as it is iterated over.
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
> #### Variable scoping is done in the following order: Built-in, Global, Enclosing, Local. Local variables are always declared last, built-in variables are predefined. The lifetime of variables is the same as the lifetime of their respective scopes.
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
```py
for num in range(10):
    print(num)
itr = iter(range(10)) # iterator variable
```
#### What type of elements can a list contain in Python?
> #### A list can contain any type of elements
#### What is the slice operator in Python and how to use?
> #### The slice operator copies a sequence beginning at the index before `:` and ending just before the index specified after `:`. If you want to specify the step used to iterate over the sequence you can add a second `:` and specify the step.
> #### Examples:
```py
In [16]: colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']

In [17]: colors[1:7]
Out[17]: ['orange', 'yellow', 'green', 'blue', 'indigo', 'violet']

In [21]: colors[::-1]
Out[21]: ['violet', 'indigo', 'blue', 'green', 'yellow', 'orange', 'red']

In [22]: colors[::2]
Out[22]: ['red', 'yellow', 'blue', 'violet']
```
#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
> #### Only + and * can be used on lists. The + operator concatenates two lists, and the * operator concatenates a list to itself a given number of times.
#### What is the purpose of the in and not in membership operators in Python?
> #### The `in` operator checks if an object is part of an iterable, while `not in` checks if an object isn't part of an iterable. They both return boolean values.
#### What does the + operator mean when used with strings in Python?
> #### It concatenates strings together.
#### Explain f strings in Python?
> #### F strings are string literals that are prefixed with 'f' or 'F'. To convert a variable to a string, you can use replacement fields, which are expressions delimited by curly braces `{}`.
#### Name 4 iterable types in Python!
> #### Lists, sets, dictionaries, and files.
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
> #### Generators only return the individual elements, while list/set/dictionary comprehensions return objects of the respective comprehension type(i.e.: list, set, dictionary)
#### Does the order of the function definitions matter in Python? Why?
> #### The order of function definitions does not matter in python as long as all functions are called after they are defined. That's because they are used in the order they are called, not in the order they are defined.
#### What does unpacking mean in Python?
> #### Unpacking is the process of iterating over a sequence and using its elements as the arguments of a function instead of the whole sequence.
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
> #### You end up assigning a `None` value.

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
> #### You can also use Continue/Pause, Step Into, Step Over, Step out, Restart and Stop while debugging.
#### What does step over, step into and step out mean while using the debugger?
> #### Step over executes a function while skipping how it was executed, step into executes the program line by line, and step out executes the rest of the function while skipping how it was executed if the debugger is paused inside the function.
#### How can you start to debug a program from a certain line using the debugger?
> #### You can use breakpoints to tell the program where to pause and to start debugging from there.

### Version control

#### What are the advantages of using a version control system?
> #### A version control system(VCS) is a way to save your progress developing a project at different points in time. The advantages of using a VCS are that you can "go back in time" and start modifying the project at startiing at a certain point in time.
#### What is the difference between the working directory, the staging area and the repository in git?
> #### The working directory is the directory in which the .git folder resides. The staging area is the area in which files staged to commit are saved. The git repository is the area in which commit files are saved.
#### What are remote repositories in git?
> #### Remote repositories are versions of the git repositories saved on the internet.
#### Why does a merge conflict occur?
> #### Merge conflicts occur when different branches modified the same file differently.
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
```sh
git add <file>
git commit -m 'Commit Message'
git push -u origin <branch>
```
#### What do atomic commits and descriptive commit messages mean?
> #### Atomic commits are commits that commit only individual changes in a project. Descriptive commit messages are commit messages that do a good job describing the changes made in a commit.
#### What’s the difference between git and GitHub?
> #### Git is a version control system, while Github is a hosting service for Git repositories

## Software design

### Clean code

#### What does clean code mean?
> #### Clean code is code that is easy to read and understand.
#### What steps do we usually do during a clean code refactoring?
> #### We check whether or not variable and function names are descriptive and modify them accordingly. We also check whether or not there is dead code, there are unnecessary comments, or we are repeating ourselves in the code.

### Error handling

#### What is exception handling?
> #### It is the process of catching exceptions occuring in a code block and responding to it with a certain code block.
#### What are the basics of exception handling in Python?
> #### Exception handling is done using the `try` statement which takes a code block and tries it for exceptions occuring in it, and catching a certain exception with the `except` statement.
#### In which case should we catch an exception? Why?
> #### We should catch an exception only when we know what exception we're trying to catch because it is a good practice to catch specific exceptions.
#### What can/should we do with an exception in the ‘except’ block?
> #### We should try catching that exception.
#### What does the else and finally statement do in a try-except block in Python?
> #### The `else` statement executes a code after the `except` if there was no exception to be caught. The `finally` statement executes its code at all times after the `try`, `except` and/or `else` statement.

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
> #### The goal of a retrospective meeting is finding the faults in your code and finding ways to make it work better.

## Programming environment

### Unix

#### What is UNIX and what is Linux?
> #### UNIX is an operating system, while Linux is a family of open-source Unix-like operating systems based on the Linux kernel.
#### What do we call the shell in Linux?
> #### We call it the terminal.
#### What does root means in a Linux environment?
> #### Root is the superuser. The superuser is the user who installed the Linux environment.
#### How do you access your personal files in Linux?
> #### You can either look for them in the Files application, and double-click or right-click and click "Open", or you can open them from the terminal in the terminal text editor of your choice(i.e.: nano, pico, vim, etc.)
#### How can you install an application in Linux?
> #### It depends on the package manager you have. You usually have to login as root(by running `sudo`) to install anything, unless you disable this feature manually. Fedora uses `dnf install PACKAGE`, OpenSUSE uses `zypper in PKG`, Debian and Ubuntu use `apt install PACKAGE`, Arch uses `pacman -S PACKAGE`, and Gentoo Linux, Chrome OS, Calculate, Sabayon, and Funtoo Linux use `emerge PACKAGE`.
#### What is package management in Linux, what are repositories?
> #### Packages in Linux downloaded in either a .tar or .tar.gz file. .tar compresses files into one archive file, while .gz decompresses the archive file.
#### How do you navigate in the filesystem with the command line?
> #### You use the `cd <PATH>` command to change directories to a specific path, you can use ls to list the contents of the folder you're in or you can use `ls <PATH>` to list the contents of another directory located at PATH without changing directories.
#### What does the following commands do: mkdir, rm, cat, cp, touch?
> #### mkdir creates a directory, rm removes/deletes a file, cat reads data from a file and gives its content as output, but it can also create and edit a new file, cp copies a file, and touch creates a file.
#### How can you look up what a command does in Linux if you have no internet connection?
> #### You can enter `info <command>`, `man <command>` or `help <command>` to output a command guide.
#### What does the following commands do: head, tail, more, less?
> #### 'head' prints the first part (10 lines by default) of each FILE; it reads from standard input if no files are given. 'tail' prints the last part (10 lines by default) of each FILE; it reads from standard input if no files are given. more is  a filter for paging through text one screenful at a time. Less  is  a  program similar to more, but it has many more features.  Less does not have to read the entire input file before starting, so with large input files it starts up faster than text editors like vi.
#### How do you download a file from internet using the terminal?
> #### To download a file from the internet you can use the `wget <URL>`
