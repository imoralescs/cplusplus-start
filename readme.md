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

```
/*#include <iostream>

using namespace std;

int main() 
{
    short num;

    num = 113;

    cout << "Short data type: " << num << "\n";
    
    return 0;
}
*/
//-> Short data type: 113

/*
#include <iostream>

using namespace std;

int main() 
{
    int num;

    num = 1024;

    cout << "Integer data type: " << num << "\n";
    
    return 0;
}
*/
//-> Integer data type: 1024

/*
#include <iostream>

using namespace std;

int main() 
{
    long num;

    num = -12332252626L;

    cout << "Long data type: " << num << "\n";
    
    return 0;
}
*/
//-> Long data type: -12332252626

/*
#include <iostream>

using namespace std;

int main() 
{
    double num;

    num = -42937737;

    cout << "Double data type: " << num << "\n";
    
    return 0;
}
*/
//-> Double data type: -4.29377e+07

/*
#include <iostream>

using namespace std;

int main() 
{
    float num;

    num = 19.98f;

    cout << "Float data type: " << num << "\n";
    
    return 0;
}
*/
//-> Float data type: 19.98

/*
#include <iostream>

using namespace std;

int main() 
{
    bool a, b;

    a = false;

    b = true;

    cout << "Boolean data type: " << a << " and " << b << "\n";
    
    return 0;
}
*/
//-> Boolean data type: 0 and 1

/*
#include <iostream>

using namespace std;

int main() 
{
    char ch = 'Z';

    cout << "Character data type: " << ch << "\n";
    
    return 0;
}
*/
//-> Character data type: Z

```

#### Constant

* Literal

Can be many type.

```
#include <iostream>

using namespace std;

int main() 
{
    cout << "Hello World!\n" << endl;
    
    return 0;
}
```

* Declaring variable as constant using `const`

```
#include <iostream>

using namespace std;

int main() 
{
    const double pi = 22.0 / 7;

    cout << "The value of constant pi is: " << pi << "\n" << endl;
    
    return 0;
}

//-> The value of constant pi is: 3.14286
```

### Operation

```
/*
#include <iostream>

using namespace std;

int main() 
{
    int x = 10;

    int y = 20;

    cout << "X equal to: " << x << "\n" << endl;

    cout << "Y equal to: " << y << "\n" << endl;
    
    return 0;
}
//-> X equal to: 10
//-> Y equal to: 20
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int x = 7;

    int result = x * 2;

    cout << "Result: " << result << "\n" << endl;
    
    return 0;
}
//-> Result: 14
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int x = 1;

    cout << "Result: " << ++x << "\n" << endl;
    
    return 0;
}
// Result: 2
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int x = 1;

    int y = ++x;

    cout << "Result: " << x << "\n" << endl;

    cout << "Result: " << y << "\n" << endl;
    
    return 0;
}
//-> Result: 2
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int x = 1;

    int y = ++x;

    cout << "Result: " << x << "\n" << endl;

    cout << "Result: " << y << "\n" << endl;
    
    int z = y++ + x;

    cout << "Result: " << x << "\n" << endl;

    cout << "Result: " << y << "\n" << endl;

    cout << "Result: " << z << "\n" << endl;
    
    return 0;
}
*/
```

### Conditional

```
/*
#include <iostream>

using namespace std;

int main() 
{
    int data_01 = (true) ? 5 : 2;

    cout << data_01 << "\n" << endl;
    //-> 5

    int data_02 = (false) ? 5 : 2;

    cout << data_02 << "\n" << endl;
    //-> 2

    int age_01 = 11;
    bool result_01 = (age_01 > 8) ? true : false;

    cout << result_01 << "\n" << endl;
    //-> 1

    return 0;
}
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int year = 2010;

    if(year != 2011) {
        cout << "year is 2011...\n" << endl;
    }

    return 0;
}
//-> year is 2011...
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    int data = 6;

    if(data < 5) {
        cout << "Block code 1\n" << endl;
    }
    else {
        cout << "Block code 2\n" << endl;
    }

    return 0;
}
//-> Block code 2
*/

/*
#include <iostream>

using namespace std;

int main() 
{
    string login = "Jack";

    if(login == "John") {
        cout << "Hello " << login << endl;
    }
    else if(login == "Jack") {
        cout << "Hello " << login << endl;
    }
    else if(login == "") {
        cout << "Please type login!\n" << endl;
    }
    else {
        cout << "Hmmm!\n" << endl;
    }

    return 0;
}
*/

// Switch
/*
The reason why has to do with the type system. C/C++ doesn't really support strings as a type. It does support the idea of a constant char array but it doesn't really fully understand the notion of a string.

In order to generate the code for a switch statement the compiler must understand what it means for two values to be equal. For items like ints and enums, this is a trivial bit comparison. But how should the compiler compare 2 string values? Case sensitive, insensitive, culture aware, etc ... Without a full awareness of a string this cannot be accurately answered.

Additionally, C/C++ switch statements are typically generated as branch tables. It's not nearly as easy to generate a branch table for a string style switch.
*/
```
