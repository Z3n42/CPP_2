<div align="center">

# 🔷 C++ Piscine - Modules 05 to 09

### Advanced C++ Concepts: Exceptions, Casts, Templates, STL

<p>
  <img src="https://img.shields.io/badge/Module_05-100%2F100-success?style=for-the-badge&logo=42" alt="CPP05 Score"/>
  <img src="https://img.shields.io/badge/Module_06-100%2F100-success?style=for-the-badge&logo=42" alt="CPP06 Score"/>
  <img src="https://img.shields.io/badge/Module_07-100%2F100-success?style=for-the-badge&logo=42" alt="CPP07 Score"/>
  <img src="https://img.shields.io/badge/Module_08-100%2F100-success?style=for-the-badge&logo=42" alt="CPP08 Score"/>
  <img src="https://img.shields.io/badge/Module_09-100%2F100-success?style=for-the-badge&logo=42" alt="CPP09 Score"/>
</p>

<p>
  <img src="https://img.shields.io/badge/Language-C++98-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++98"/>
  <img src="https://img.shields.io/badge/Compiler-c++-00599C?style=for-the-badge" alt="Compiler"/>
  <img src="https://img.shields.io/badge/Standard-C++98-blue?style=for-the-badge" alt="Standard"/>
  <img src="https://img.shields.io/badge/42-Urduliz-000000?style=for-the-badge&logo=42&logoColor=white" alt="42 Urduliz"/>
</p>

*Advanced exploration of C++ mechanisms: exception handling, type casting, generic programming with templates, and the Standard Template Library.*

[Overview](#-overview) • [Modules](#-modules-breakdown) • [Concepts](#-key-c-concepts) • [Compilation](#-compilation)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Modules Breakdown](#-modules-breakdown)
- [Key C++ Concepts](#-key-c-concepts)
- [Project Structure](#-project-structure)
- [Compilation](#-compilation)
- [What I Learned](#-what-i-learned)
- [Resources](#-resources)

---

## 🎯 Overview

This series of **advanced C++ modules** builds upon the foundational OOP knowledge from Modules 00-04, diving into sophisticated C++98 features including exception handling, type casting mechanisms, template programming, and the Standard Template Library (STL). Each module progressively introduces more complex programming paradigms essential for modern C++ development.

### Summary Statistics

<table>
<tr>
<th>Module</th>
<th>Score</th>
<th>Exercises</th>
<th>Focus Area</th>
</tr>
<tr>
<td><b>CPP Module 05</b></td>
<td>100/100</td>
<td>4</td>
<td>Exceptions, Try-Catch, Custom Exceptions</td>
</tr>
<tr>
<td><b>CPP Module 06</b></td>
<td>100/100</td>
<td>3</td>
<td>C++ Casts, Type Conversion, RTTI</td>
</tr>
<tr>
<td><b>CPP Module 07</b></td>
<td>100/100</td>
<td>3</td>
<td>Function Templates, Generic Programming</td>
</tr>
<tr>
<td><b>CPP Module 08</b></td>
<td>100/100</td>
<td>3</td>
<td>Templated Containers, Iterators, Algorithms</td>
</tr>
<tr>
<td><b>CPP Module 09</b></td>
<td>100/100</td>
<td>3</td>
<td>STL Containers, Algorithms, Performance</td>
</tr>
</table>

**Total**: 16 exercises covering advanced C++ mechanisms

### Core Learning Areas

<table>
<tr>
<td width="50%" valign="top">

### ⚠️ Exception Handling
- **Try-catch blocks** and exception propagation
- Custom exception classes with context
- Nested exceptions within class hierarchies
- Exception safety guarantees
- Resource management with RAII

</td>
<td width="50%" valign="top">

### 🔄 Type Casting
- **static_cast** for compile-time conversions
- dynamic_cast for runtime type checking
- reinterpret_cast for low-level conversions
- const_cast for const manipulation
- Scalar type conversions (char/int/float/double)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📐 Template Programming
- **Function templates** with type parameters
- Class templates and specialization
- Template instantiation mechanisms
- Type deduction rules
- Generic algorithm design

</td>
<td width="50%" valign="top">

### 📚 Standard Template Library
- **STL containers** (vector, list, map, stack, deque)
- Iterators and iterator categories
- STL algorithms (find, sort, min/max_element)
- Performance analysis and complexity
- Container adapters

</td>
</tr>
</table>

---

## 📦 Modules Breakdown

### CPP Module 05 - Repetition and Exceptions (Score: 100/100)

**Topics**: Exception handling, try-catch blocks, nested exceptions, custom exception classes

<table>
<tr>
<th>Exercise</th>
<th>Files</th>
<th>Concept</th>
</tr>
<tr>
<td><b>ex00: Bureaucrat</b></td>
<td>Bureaucrat.hpp/cpp, main.cpp, main_v.cpp, Makefile</td>
<td>Basic exception classes, throw/catch</td>
</tr>
<tr>
<td><b>ex01: Form up, maggots!</b></td>
<td>Form.hpp/cpp, Bureaucrat files, main.cpp, main_v.cpp, Makefile</td>
<td>Forms with sign requirements</td>
</tr>
<tr>
<td><b>ex02: No, you need form 28B</b></td>
<td>AForm.hpp/cpp, 3 concrete forms, main.cpp, main_v.cpp, Makefile</td>
<td>Abstract forms, execution logic</td>
</tr>
<tr>
<td><b>ex03: At least this beats coffee-making</b></td>
<td>Intern.hpp/cpp, all previous files, main.cpp, main_v.cpp, Makefile</td>
<td>Factory pattern for form creation</td>
</tr>
</table>

**Key Implementation**: Bureaucratic hierarchy system where Bureaucrats (grades 1-150) can sign and execute Forms. Lower grade numbers represent higher authority (1 is highest, 150 is lowest).

**Bureaucrat Class**:
- Constant name attribute (`std::string const _name`)
- Grade range: 1 (highest) to 150 (lowest)
- Methods: `GradeUp()`, `GradeDown()`, `getName()`, `getGrade()`
- Custom exceptions: `GradeTooHighException`, `GradeTooLowException`

**Form/AForm Hierarchy**:
- **Form (ex01)** / **AForm (ex02+)**: Name, sign grade (`_Wgrade`), execute grade (`_Xgrade`), signed status (`_sign`)
- **ShrubberyCreationForm** (sign: 145, exec: 137): Creates ASCII tree file
- **RobotomyRequestForm** (sign: 72, exec: 45): 50% success rate, drilling noises
- **PresidentialPardonForm** (sign: 25, exec: 5): Presidential pardon by Zaphod Beeblebrox

**Intern Factory** (ex03):
- Method: `AForm* makeForm(std::string formName, std::string target)`
- Form names: "shrubbery creation", "robotomy request", "presidential pardon"
- Returns `NULL` if form name doesn't match

<details>
<summary><b>Exception Handling Implementation Details</b></summary>

```cpp
class Bureaucrat {
private:
    std::string const _name;
    int _grade;

public:
    // Nested exception classes with contextual information
    class GradeTooHighException : public std::exception {
    private:
        const char* _HighError;
        int _grade;
        std::string const _who;
    public:
        GradeTooHighException(const char* error, int lvl, std::string const &name);
        virtual const char* what() const throw();
        virtual ~GradeTooHighException() throw();
    };

    class GradeTooLowException : public std::exception {
    private:
        const char* _LowError;
        int _grade;
        std::string const _who;
    public:
        GradeTooLowException(const char* error, int lvl, std::string const &name);
        virtual const char* what() const throw();
        virtual ~GradeTooLowException() throw();
    };

    void GradeUp(void);   // Throws exception if grade < 1
    void GradeDown(void); // Throws exception if grade > 150
};

// Usage pattern:
try {
    Bureaucrat bob("Bob", 1);
    bob.GradeUp();  // Will throw GradeTooHighException
}
catch (std::exception & e) {
    std::cerr << e.what() << std::endl;
}
```

**Why nested exceptions?**: Encapsulates exception logic within the class, provides context-specific error messages with bureaucrat name, grade, and error type.

</details>

---

### CPP Module 06 - C++ Casts (Score: 100/100)

**Topics**: static_cast, dynamic_cast, reinterpret_cast, const_cast, type conversion

<table>
<tr>
<th>Exercise</th>
<th>Files</th>
<th>Concept</th>
</tr>
<tr>
<td><b>ex00: Scalar Converter</b></td>
<td>ScalarConverter class, convert.hpp/cpp, main.cpp, Makefile</td>
<td>Conversion between char, int, float, double</td>
</tr>
<tr>
<td><b>ex01: Serialization</b></td>
<td>Serializer class, serialize.hpp/cpp, main.cpp, Makefile</td>
<td>Pointer to uintptr_t serialization</td>
</tr>
<tr>
<td><b>ex02: Identify real type</b></td>
<td>Base/A/B/C classes, serialization.hpp/cpp, main.cpp, Makefile</td>
<td>Runtime type identification without typeinfo</td>
</tr>
</table>

**ScalarConverter** (ex00):
- Static method: `void convert(std::string toConvert)`
- Detects input type: char, int, float, double
- Converts to all four scalar types
- Handles special values: `nan`, `nanf`, `±inf`, `±inff`
- Displays: "impossible" or "Non displayable" when appropriate

**Serializer** (ex01):
- Static methods: `uintptr_t serialize(Data* ptr)` and `Data* deserialize(uintptr_t raw)`
- Uses **reinterpret_cast** for pointer ↔ integer conversion
- Data struct: `int num` and `char chars`

**Type Identification** (ex02):
- Base class (polymorphic) with three derived classes: A, B, C
- `Base* generate()` - randomly instantiates A, B, or C
- `void identify(Base* p)` - identifies by pointer (dynamic_cast returns NULL on failure)
- `void identify(Base& p)` - identifies by reference (dynamic_cast throws on failure)

<details>
<summary><b>Cast Types Implementation</b></summary>

**Cast Comparison Table**:

| Cast Type | Use Case | Safety Check | Example |
|-----------|----------|--------------|---------|
| **static_cast** | Numeric conversions | Compile-time | `static_cast<float>(42)` |
| **dynamic_cast** | Polymorphic downcast | Runtime (RTTI) | `dynamic_cast<Derived*>(base)` |
| **reinterpret_cast** | Pointer ↔ integer | None | `reinterpret_cast<uintptr_t>(ptr)` |
| **const_cast** | Add/remove const | None | `const_cast<char*>(str)` |

**Serialization with reinterpret_cast**:
```cpp
// Low-level pointer-to-integer conversion
uintptr_t Serializer::serialize(Data* ptr) {
    return reinterpret_cast<uintptr_t>(ptr);
}

Data* Serializer::deserialize(uintptr_t raw) {
    return reinterpret_cast<Data*>(raw);
}
```

**Type Identification with dynamic_cast**:
```cpp
// Pointer version - returns NULL on failure
void identify(Base* p) {
    if (dynamic_cast<A*>(p))
        std::cout << "A";
    else if (dynamic_cast<B*>(p))
        std::cout << "B";
    else
        std::cout << "C";
}

// Reference version - throws std::bad_cast on failure
void identify(Base& p) {
    try {
        (void)dynamic_cast<A&>(p);
        std::cout << "A";
        return;
    } catch (std::exception &e) {}
    // ... try B, then default to C
}
```

</details>

---

### CPP Module 07 - C++ Templates (Score: 100/100)

**Topics**: Function templates, template specialization, generic programming

<table>
<tr>
<th>Exercise</th>
<th>Files</th>
<th>Concept</th>
</tr>
<tr>
<td><b>ex00: Start with a few functions</b></td>
<td>whatever.hpp, main.cpp, Makefile</td>
<td>Basic function templates (swap, min, max)</td>
</tr>
<tr>
<td><b>ex01: Iter</b></td>
<td>iter.hpp, main.cpp, Makefile</td>
<td>Template function for array iteration</td>
</tr>
<tr>
<td><b>ex02: Array</b></td>
<td>Array.hpp, main.cpp, Makefile</td>
<td>Template class for dynamic arrays</td>
</tr>
</table>

**Function Templates** (ex00):
- `template<typename T> void swap(T &x, T &y)` - Swaps two values
- `template<typename T> T const & max(T const &x, T const &y)` - Returns larger (y if equal)
- `template<typename T> T const & min(T const &x, T const &y)` - Returns smaller (y if equal)

**Iter Template** (ex01):
- `template<typename T> void iter(T *array, size_t size, void (*f)(T const &))`
- Applies function to every array element
- Works with any type T and compatible function pointer

**Array Template Class** (ex02):
- Constructors: `Array()` (empty), `Array(unsigned int n)` (n elements)
- Deep copy in copy constructor and assignment operator
- Subscript operator with bounds checking: `T& operator[](unsigned int i)`
- Throws `NotAllowed` exception if index out of bounds
- `unsigned int size() const` - returns array size

<details>
<summary><b>Template Implementation Details</b></summary>

**Why templates in headers?**: Templates are instantiated at compile time. The compiler needs full definition to generate code for each type.

**Function Templates (whatever.hpp)**:
```cpp
template<typename T>
void swap(T &x, T &y) {
    T t = x;
    x = y;
    y = t;
}

template<typename T>
T const & max(T const &x, T const &y) {
    return (y >= x ? y : x);
}

template<typename T>
T const & min(T const &x, T const &y) {
    return (y <= x ? y : x);
}
```

**Iter Template (iter.hpp)**:
```cpp
template<typename T>
void iter(T *array, size_t size, void function(T const &ref)) {
    for(size_t i = 0; i < size; i++)
        function(array[i]);
}

// Example function to use with iter
template<typename T>
void colorize(T const &ref) {
    if (static_cast<int>(ref) % 2 == 0)
        std::cout << GREEN << ref << RESET << std::endl;
    else
        std::cout << RED << " " << ref << RESET << std::endl;
}
```

**Array Template Class (Array.hpp)**:
```cpp
template<typename T>
class Array {
private:
    unsigned int _n;
    T *_t;

public:
    Array() {
        this->_t = new T[1];
        this->_t[0] = 0;
    }

    Array(unsigned int n) : _n(n) {
        this->_t = new T[n];
    }

    Array(Array const &src) : _n(src.size()) {
        this->_t = new T[this->_n];
        for (unsigned int i = 0; i < this->_n; i++)
            this->_t[i] = src[i];
    }

    ~Array() {
        delete [] this->_t;
    }

    Array & operator=(Array const &rhs) {
        this->_n = rhs.size();
        delete [] this->_t;
        this->_t = new T[_n];
        for (unsigned int i = 0; i < _n; i++)
            this->_t[i] = rhs[i];
        return *this;
    }

    T & operator[](unsigned int i) {
        if (i >= this->size())
            throw NotAllowed();
        return this->_t[i];
    }

    unsigned int size() const { return _n; }

    class NotAllowed : public std::exception {
    public:
        virtual const char* what() const throw() {
            return "Not Allowed";
        }
    };
};
```

**Key points**: Deep copy, bounds checking, RAII (memory managed in constructor/destructor).

</details>

---

### CPP Module 08 - Templated Containers, Iterators, Algorithms (Score: 100/100)

**Topics**: STL introduction, containers, iterators, algorithms, custom containers

<table>
<tr>
<th>Exercise</th>
<th>Files</th>
<th>Concept</th>
</tr>
<tr>
<td><b>ex00: Easy find</b></td>
<td>easyfind.hpp, main.cpp, Makefile</td>
<td>Template function with STL algorithm</td>
</tr>
<tr>
<td><b>ex01: Span</b></td>
<td>Span.hpp/cpp, main.cpp, Makefile</td>
<td>Container class with range operations</td>
</tr>
<tr>
<td><b>ex02: Mutated abomination</b></td>
<td>MutantStack.hpp, main.cpp, Makefile</td>
<td>Iterable stack container adapter</td>
</tr>
</table>

**easyfind** (ex00):
- `template<typename T> int easyfind(std::vector<T> vec, int x)`
- Uses `std::find()` algorithm
- Returns position (1-indexed) if found
- Throws `std::runtime_error` if not found

**Span Class** (ex01):
- Constructor: `Span(unsigned int N)` - max capacity N
- `void addNumber(int n)` - adds single number
- `int shortestSpan()` - minimum distance between any two numbers
- `int longestSpan()` - maximum distance (max - min)
- `void generator()` - fills with random numbers
- Must handle at least 10,000 numbers

**MutantStack** (ex02):
- Inherits from `std::stack<T>`, adds iterator support
- Implements: `begin()`, `end()`, `rbegin()`, `rend()`
- Also const versions
- Accesses underlying container via protected `c` member

<details>
<summary><b>STL Container Usage Details</b></summary>

**easyfind Implementation**:
```cpp
template<typename T>
int easyfind(std::vector<T> vec, int x) {
    typename std::vector<T>::iterator it;
    it = std::find(vec.begin(), vec.end(), x);

    if (it != vec.end()) {
        std::cout << "Element " << x << " found at position: "
                  << it - vec.begin() + 1 << std::endl;
        return 1;
    }
    throw std::runtime_error("Value not found in container");
}
```

**Span Key Methods**:
```cpp
void Span::addNumber(int n) {
    if (this->_vec->size() >= this->_N)
        throw std::runtime_error("Span is full");
    this->_vec->push_back(n);
}

int Span::shortestSpan() {
    if (this->_vec->size() < 2)
        throw std::runtime_error("Not enough elements");

    std::vector<int> sorted = *this->_vec;
    std::sort(sorted.begin(), sorted.end());

    int minSpan = sorted[1] - sorted[0];
    for (size_t i = 2; i < sorted.size(); i++) {
        int span = sorted[i] - sorted[i-1];
        if (span < minSpan)
            minSpan = span;
    }
    return minSpan;
}

int Span::longestSpan() {
    if (this->_vec->size() < 2)
        throw std::runtime_error("Not enough elements");

    int min = *std::min_element(this->_vec->begin(), this->_vec->end());
    int max = *std::max_element(this->_vec->begin(), this->_vec->end());
    return (max - min);
}
```

**MutantStack Implementation**:
```cpp
template<typename T>
class MutantStack : public std::stack<T> {
public:
    MutantStack() {}
    MutantStack(MutantStack const &src) { *this = src; }
    ~MutantStack() {}

    MutantStack & operator=(MutantStack const &rhs) {
        if (rhs != *this)
            this->c = rhs.c;  // Access protected container
        return *this;
    }

    // Iterator typedefs
    typedef typename std::stack<T>::container_type::iterator iterator;
    typedef typename std::stack<T>::container_type::const_iterator const_iterator;
    typedef typename std::stack<T>::container_type::reverse_iterator reverse_iterator;
    typedef typename std::stack<T>::container_type::const_reverse_iterator const_reverse_iterator;

    // Iterator methods
    iterator begin() { return this->c.begin(); }
    iterator end() { return this->c.end(); }
    reverse_iterator rbegin() { return this->c.rbegin(); }
    reverse_iterator rend() { return this->c.rend(); }

    const_iterator begin() const { return this->c.begin(); }
    const_iterator end() const { return this->c.end(); }
    const_reverse_iterator rbegin() const { return this->c.rbegin(); }
    const_reverse_iterator rend() const { return this->c.rend(); }
};
```

**Why `this->c`?**: `std::stack` stores underlying container (default: `std::deque`) in protected member `c`. MutantStack exposes it for iteration.

</details>

---

### CPP Module 09 - STL (Score: 100/100)

**Topics**: STL containers, algorithms, performance comparison, Ford-Johnson algorithm

**Module-Specific Rule**: Each exercise must use a **different** STL container.

<table>
<tr>
<th>Exercise</th>
<th>Files</th>
<th>Concept</th>
</tr>
<tr>
<td><b>ex00: Bitcoin Exchange</b></td>
<td>BitcoinExchange.hpp/cpp, main.cpp, Makefile</td>
<td>CSV parsing, std::map, date-based lookup</td>
</tr>
<tr>
<td><b>ex01: Reverse Polish Notation</b></td>
<td>RPN.hpp/cpp, main.cpp, Makefile</td>
<td>RPN calculator with std::stack</td>
</tr>
<tr>
<td><b>ex02: PmergeMe</b></td>
<td>PmergeMe.hpp/cpp, main.cpp, Makefile</td>
<td>Ford-Johnson sort, performance comparison</td>
</tr>
</table>

**BitcoinExchange** (ex00):
- Reads CSV database: `data.csv` (date,rate format)
- Input: `date | value` (e.g., `2011-01-03 | 3`)
- Uses **std::map<std::string, float>** for date-rate pairs
- Finds closest lower date using `lower_bound`
- Validates: date format, value range (0-1000)

**RPN Calculator** (ex01):
- Evaluates Reverse Polish Notation: `"8 9 * 9 - 9 - 9 - 4 - 1 +"` → `42`
- Uses **std::stack<int>** for operand storage
- Operators: `+`, `-`, `*`, `/`
- Numbers: single digits (0-9)

**PmergeMe** (ex02):
- Implements **Ford-Johnson merge-insert sort**
- Uses two containers: **std::vector<int>** and **std::deque<int>**
- Compares execution time in microseconds
- Must handle 3000+ integers

<details>
<summary><b>Algorithm Implementations</b></summary>

**BitcoinExchange - Map Lookup**:
```cpp
class BitcoinExchange {
private:
    std::map<std::string, float> _database;

public:
    void loadDatabase(std::string filename);
    void processLine(std::string line);

    float getRate(std::string date) {
        std::map<std::string, float>::iterator it = _database.lower_bound(date);

        if (it == _database.begin() && it->first != date) {
            throw std::runtime_error("Error: date too early");
        }

        if (it->first != date && it != _database.begin())
            --it;  // Use previous date (closest lower)

        return it->second;
    }
};
```

**RPN - Stack Evaluation**:
```cpp
int RPN::calculate(std::string input) {
    std::stack<int> operands;

    for (size_t i = 0; i < input.length(); i++) {
        if (isdigit(input[i])) {
            operands.push(input[i] - '0');
        }
        else if (isOperator(input[i])) {
            if (operands.size() < 2)
                throw std::runtime_error("Error");

            int b = operands.top(); operands.pop();
            int a = operands.top(); operands.pop();

            switch (input[i]) {
                case '+': operands.push(a + b); break;
                case '-': operands.push(a - b); break;
                case '*': operands.push(a * b); break;
                case '/':
                    if (b == 0) throw std::runtime_error("Error");
                    operands.push(a / b);
                    break;
            }
        }
    }

    if (operands.size() != 1)
        throw std::runtime_error("Error");

    return operands.top();
}
```

**Performance Comparison**:
```
Before: 3 5 9 7 4
After:  3 4 5 7 9
Time to process with std::vector: 0.00031 us
Time to process with std::deque: 0.00041 us
```

**Why vector is faster**: Contiguous memory → better cache locality than deque's segmented storage.

</details>

---

## 🔑 Key C++ Concepts

### Exception Handling Mechanism

**Try-Catch-Throw Pattern**:
```cpp
try {
    if (error_condition)
        throw CustomException("Error message");
}
catch (CustomException &e) {
    std::cerr << e.what() << std::endl;
}
catch (std::exception &e) {
    std::cerr << e.what() << std::endl;
}
```

**Exception Safety Guarantees**:
1. **No-throw**: Never throws (destructors)
2. **Strong**: Succeeds completely or no effect
3. **Basic**: No leaks, valid state
4. **No guarantee**: Undefined behavior

**Best Practices**:
- Catch by reference to avoid slicing
- Never throw from destructors
- Use RAII for cleanup
- Inherit from `std::exception`

### C++ Cast Operators

| Cast Type | Use Case | Example |
|-----------|----------|---------|
| `static_cast` | Numeric conversions | `static_cast<float>(42)` |
| `dynamic_cast` | Polymorphic downcast (RTTI) | `dynamic_cast<Derived*>(base)` |
| `reinterpret_cast` | Pointer ↔ integer | `reinterpret_cast<uintptr_t>(ptr)` |
| `const_cast` | Remove const | `const_cast<char*>(str)` |

<details>
<summary><b>Cast Usage Details</b></summary>

**dynamic_cast Behavior**:
- Returns `NULL` for pointers on failure
- Throws `std::bad_cast` for references on failure
- Requires virtual function (RTTI enabled)
- Runtime overhead

**When to use each**:
- **static_cast**: Safe, checked conversions (int→float, base→derived upcast)
- **dynamic_cast**: Runtime type checking for polymorphic downcasts
- **reinterpret_cast**: Low-level bit manipulation (pointer serialization)
- **const_cast**: Legacy API compatibility (use sparingly)

</details>

### Template Programming

**Why templates in headers?**: Instantiated at compile time. Compiler needs full definition (inclusion model).

**Template Instantiation**:
```cpp
template<typename T>
T max(T a, T b) { return a > b ? a : b; }

int x = max(3, 5);         // Instantiates max<int>
double y = max(3.14, 2.71); // Instantiates max<double>
```

### STL Container Characteristics

**Time Complexity**:

| Operation | vector | deque | list | map | stack |
|-----------|--------|-------|------|-----|-------|
| Random access | O(1) | O(1) | O(n) | O(log n) | - |
| Insert at end | O(1)* | O(1) | O(1) | - | O(1) |
| Insert anywhere | O(n) | O(n) | O(1) | O(log n) | - |
| Find element | O(n) | O(n) | O(n) | O(log n) | - |

*amortized

**Iterator Categories**:
1. Input/Output: Single-pass
2. Forward: Multi-pass
3. Bidirectional: ++ and --
4. Random Access: Jump to position

---

## 📁 Project Structure

```
cpp_module_05-09/
│
├── cpp05_pass/                    # Module 05 (100/100)
│   ├── ex00/                      # Bureaucrat
│   │   ├── inc/Bureaucrat.hpp
│   │   ├── src/Bureaucrat.cpp
│   │   ├── main.cpp
│   │   ├── main_v.cpp
│   │   └── Makefile
│   ├── ex01/                      # Form
│   │   ├── inc/
│   │   │   ├── Bureaucrat.hpp
│   │   │   └── Form.hpp
│   │   ├── src/
│   │   │   ├── Bureaucrat.cpp
│   │   │   └── Form.cpp
│   │   ├── main.cpp
│   │   ├── main_v.cpp
│   │   └── Makefile
│   ├── ex02/                      # Concrete forms
│   │   ├── inc/
│   │   │   ├── AForm.hpp
│   │   │   ├── ShrubberyCreationForm.hpp
│   │   │   ├── RobotomyRequestForm.hpp
│   │   │   └── PresidentialPardonForm.hpp
│   │   ├── src/
│   │   │   ├── AForm.cpp
│   │   │   ├── ShrubberyCreationForm.cpp
│   │   │   ├── RobotomyRequestForm.cpp
│   │   │   └── PresidentialPardonForm.cpp
│   │   ├── main.cpp
│   │   └── Makefile
│   └── ex03/                      # Intern factory
│       ├── inc/
│       │   ├── Intern.hpp
│       │   └── [all form headers]
│       ├── src/
│       │   ├── Intern.cpp
│       │   └── [all form implementations]
│       ├── main.cpp
│       └── Makefile
│
├── cpp06_pass/                    # Module 06 (100/100)
│   ├── ex00/                      # Scalar Converter
│   │   ├── inc/convert.hpp
│   │   ├── src/convert.cpp
│   │   ├── main.cpp
│   │   └── Makefile
│   ├── ex01/                      # Serialization
│   │   ├── inc/serialize.hpp
│   │   ├── src/serialize.cpp
│   │   ├── main.cpp
│   │   └── Makefile
│   └── ex02/                      # Type identification
│       ├── inc/serialization.hpp
│       ├── src/serialization.cpp
│       ├── main.cpp
│       └── Makefile
│
├── cpp07_pass/                    # Module 07 (100/100)
│   ├── ex00/                      # Function templates
│   │   ├── inc/whatever.hpp
│   │   ├── main.cpp
│   │   └── Makefile
│   ├── ex01/                      # Iter template
│   │   ├── inc/iter.hpp
│   │   ├── main.cpp
│   │   └── Makefile
│   └── ex02/                      # Array template
│       ├── inc/Array.hpp
│       ├── main.cpp
│       └── Makefile
│
├── cpp08_pass/                    # Module 08 (100/100)
│   ├── ex00/                      # easyfind
│   │   ├── inc/easyfind.hpp
│   │   ├── main.cpp
│   │   └── Makefile
│   ├── ex01/                      # Span
│   │   ├── inc/Span.hpp
│   │   ├── src/Span.cpp
│   │   ├── main.cpp
│   │   └── Makefile
│   └── ex02/                      # MutantStack
│       ├── inc/MutantStack.hpp
│       ├── main.cpp
│       └── Makefile
│
└── cpp09_pass/                    # Module 09 (100/100)
    ├── ex00/                      # Bitcoin Exchange
    │   ├── inc/BitcoinExchange.hpp
    │   ├── src/BitcoinExchange.cpp
    │   ├── main.cpp
    │   ├── data.csv
    │   └── Makefile
    ├── ex01/                      # RPN
    │   ├── inc/RPN.hpp
    │   ├── src/RPN.cpp
    │   ├── main.cpp
    │   └── Makefile
    └── ex02/                      # PmergeMe
        ├── inc/PmergeMe.hpp
        ├── src/PmergeMe.cpp
        ├── main.cpp
        └── Makefile
```

**Total**: 5 modules, 16 exercises, ~50+ source files

---

## ⚙️ Compilation

Standard Makefile structure:

```makefile
NAME = exercise_name
CXX = c++
CXXFLAGS = -Wall -Wextra -Werror -std=c++98

SRCDIR = src
INCDIR = inc

SRCS = main.cpp $(SRCDIR)/ClassName.cpp
OBJS = $(SRCS:.cpp=.o)

all: $(NAME)

$(NAME): $(OBJS)
	$(CXX) $(CXXFLAGS) $(OBJS) -o $(NAME)

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -I$(INCDIR) -c $< -o $@

clean:
	rm -f $(OBJS)

fclean: clean
	rm -f $(NAME)

re: fclean all

.PHONY: all clean fclean re
```

**Compilation Flags**:
- `-Wall -Wextra -Werror`: All warnings as errors
- `-std=c++98`: Enforce C++98 (no C++11+)
- `-I$(INCDIR)`: Include directory

**Forbidden in C++98**:
- `auto`, `nullptr`, `std::unique_ptr`, `std::shared_ptr`
- Range-based for loops, lambda functions
- `std::array`, `std::unordered_map`, `std::unordered_set`
- Move semantics (`&&`, `std::move`)

---

## 💡 What I Learned

**Exception Handling**:
- ✅ Custom exception classes with contextual information
- ✅ Exception hierarchies from `std::exception`
- ✅ Exception safety (basic/strong/no-throw guarantees)
- ✅ RAII for automatic cleanup
- ✅ Never throw from destructors

**Type Casting**:
- ✅ When to use each cast operator
- ✅ `static_cast` for safe conversions
- ✅ `dynamic_cast` for polymorphic type checking (RTTI)
- ✅ `reinterpret_cast` for serialization
- ✅ Dangers of `const_cast`

**Templates**:
- ✅ Function and class template design
- ✅ Template instantiation model (inclusion)
- ✅ Why templates must be in headers
- ✅ Generic algorithm design
- ✅ Type deduction rules

**STL**:
- ✅ Container selection (vector/deque/list/map/stack)
- ✅ Iterator categories and capabilities
- ✅ STL algorithms (`find`, `sort`, `min_element`, `max_element`)
- ✅ Performance characteristics (cache locality)
- ✅ Container adapters

**Algorithms**:
- ✅ Time/space complexity analysis
- ✅ Ford-Johnson merge-insert sort
- ✅ RPN evaluation with stacks
- ✅ Performance benchmarking
- ✅ Iterator invalidation awareness

**Design Patterns**:
- ✅ Factory pattern (Intern)
- ✅ Strategy pattern (function pointers)
- ✅ Adapter pattern (MutantStack)
- ✅ RAII resource management

**Best Practices**:
- ✅ Catch exceptions by reference
- ✅ Use specific cast for the job
- ✅ Prefer `const_iterator` when not modifying
- ✅ Reserve capacity in vectors
- ✅ Deep copy for dynamic memory
- ✅ Check iterator validity after modifications

---

## 📚 Resources

**Official Documentation**:
- [cppreference.com - Exceptions](https://en.cppreference.com/w/cpp/language/exceptions)
- [cppreference.com - Casts](https://en.cppreference.com/w/cpp/language/explicit_cast)
- [cppreference.com - Templates](https://en.cppreference.com/w/cpp/language/templates)
- [cppreference.com - STL Containers](https://en.cppreference.com/w/cpp/container)

**Key Topics**:
- **Exception Safety**: Basic, strong, no-throw guarantees
- **RTTI**: Runtime Type Information (`dynamic_cast`)
- **Template Instantiation**: Inclusion model, ODR
- **Iterator Invalidation**: When operations invalidate iterators
- **Ford-Johnson Algorithm**: Optimal comparison sort

**Books**:
- *Effective C++* by Scott Meyers
- *The C++ Standard Library* by Nicolai Josuttis
- *C++ Templates: The Complete Guide* by Vandevoorde & Josuttis

**C++98 vs Modern C++**:

| Feature | C++98 | C++11+ |
|---------|-------|--------|
| Smart pointers | Manual `new`/`delete` | `unique_ptr`, `shared_ptr` |
| Type inference | Manual | `auto`, `decltype` |
| Null pointer | `NULL` / `0` | `nullptr` |
| Loops | Manual iterators | Range-based for |
| Hash tables | - | `unordered_map` |

---

## 🔗 Related Projects

**Prepares for**:
- **webserv**: HTTP server (uses STL)
- **ft_containers**: Reimplementing STL containers
- **ft_irc**: IRC server with advanced networking

**Skills apply to**:
- Production C++ (C++11/14/17/20)
- High-performance computing
- Generic library design
- Systems programming
- Algorithm implementation

---

<div align="center">

**Made with ☕ by [Iñigo Gonzalez](https://github.com/Z3n42)**

*42 Urduliz | C++ Piscine*

[![42 Profile](https://img.shields.io/badge/42_Intra-ingonzal-000000?style=flat&logo=42&logoColor=white)](https://profile.intra.42.fr/users/ingonzal)

</div>
