# C++

## g++

G++ ss a Gnu C++ compiler, usually operated via the command line. You can invoke g++ on a source code file simply by typing `g++ filename.cpp`. Let do ours first C++ program.

* main.cpp

```
#include <iostream>

int main()
{
    std::cout << "Hello World!" << std::endl;
    return 0;
}
```

To compile our C++ code we run `g++ main.cpp`. By default ours executable output will be `a.out`, we can also specify a name for the exacutable file by using the following sintax command, `-o outputfile`, in this case example will do `g++ main.cpp -o main`. To run ours application we type the following command `./main`

Base on our code example, `iostream` is what you call the header file, using the `#include` command. `iostream` is a standard C++ input/output library file. `#include` import into the program values and make ensures that you able to use the operation for example input from user or display output on the screen. 

Namespace make easier to reference operations included in that namespace. If we hadn't used the namespace we have to write `std::cout` instead `cout`.

```
#include <iostream>

using namespace std;

int main() 
{
    cout << "Hello World!\n" << endl;
    return 0;
}
```

### Type of main funtion

* Basic form

The `main()` function in C++ is a special function as it is the starting point of the program execution. Execution of every C++ program begins with the `main()` function, no matter where the function is located in the program. So, every C++ program must have a `main()` function. Braces define scope and blocks.

* Extended form

In this case, the `main()` function have the same description of the basic form but in adddition is used to capture the program argument, pass from the runtime enviroment and may available for the application.

* main.cpp 

```
#include <iostream>

using namespace std;

int main(int argc, char* argv[]) 
{
    cout << "Total arguments: " << argc << endl;

    for(int i = 0; i < argc; i++)
    {
        cout << "arg[" << i << "] = " << argv[i] << endl;
    }

    return 0;
}
```

```
$ ./main "Israel"

Total arguments: 2
arg[0] = ./main
arg[1] = Israel
```

## Variable

### Declaring variables

```
VariableType VariableName;

VariableType VariableName = InitialValue;
```

### Scope of a variable

* Local Variable
Variables defined within a function or block are said to be local to those functions, anything between block, local variable do not exist outside the block in which they are declared.

```
#include <iostream>

using namespace std;

void age()
{
    int age = 18;
    cout << age << "\n";
}

int main() 
{
    cout << "Age is: ";
    age();
    return 0;
}

//-> Age is: 18
```

* Global variables

Can be accessed from any part of the program.

```
#include <iostream>

using namespace std;

int global = 5;

void display()
{
    cout << global << "\n" << endl;
}

int main() 
{
    display();

    // Changing value of global
    global = 10;
    display();

    return 0;
}

//-> 5
//-> 10
```
