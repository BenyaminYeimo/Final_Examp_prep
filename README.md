from docx import Document

# Create a new Document
doc = Document()

# Title
doc.add_heading('C++ Cheat-Sheet for Final Exam', level=1)

# 1. C-String
doc.add_heading('1. C-String', level=2)
doc.add_paragraph('- Zero-byte terminator: C-strings end with a \\0 character to indicate the end of the string.')
doc.add_paragraph('- Find the length: Use strlen() to find the length of a C-string.')
doc.add_paragraph(
    '  ```cpp\n'
    '  char str[] = "Hello";\n'
    '  int length = strlen(str); // length is 5\n'
    '  ```'
)
doc.add_paragraph('- Copying C-strings: Use strcpy() to copy a C-string to another memory location.')
doc.add_paragraph(
    '  ```cpp\n'
    '  char source[] = "Hello";\n'
    '  char destination[6];\n'
    '  strcpy(destination, source); // destination now contains "Hello"\n'
    '  ```'
)
doc.add_paragraph('- String vs. C-string:')
doc.add_paragraph('  - C-strings are arrays of characters ending with \\0.')
doc.add_paragraph('  - std::string is a C++ standard library class with more functionality and ease of use.')

# 2. Pointers
doc.add_heading('2. Pointers', level=2)
doc.add_paragraph('- Definition: A pointer stores the memory address of another variable.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int var = 10;\n'
    '  int* ptr = &var; // ptr holds the address of var\n'
    '  ```'
)
doc.add_paragraph('- Pointer types: Examples: int*, char*, float*, etc.')
doc.add_paragraph('- Assigning values: int* ptr = &variable;')
doc.add_paragraph('- Dereferencing: Use *ptr to access the value at the pointer\'s address.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int value = *ptr; // value is 10\n'
    '  ```'
)
doc.add_paragraph('- Loops with pointers: Use * and ++ to iterate over arrays.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int arr[] = {1, 2, 3, 4, 5};\n'
    '  for (int* ptr = arr; ptr < arr + 5; ++ptr) {\n'
    '      // *ptr gives the value of the current element\n'
    '  }\n'
    '  ```'
)

# 3. Dynamic Allocation: new, delete
doc.add_heading('3. Dynamic Allocation: new, delete', level=2)
doc.add_paragraph('- Dynamically allocating an array: Allocates memory for an array at runtime.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int* arr = new int[10]; // allocates an array of 10 integers\n'
    '  ```'
)
doc.add_paragraph('- The delete[] operator: Deallocates the memory allocated for an array.')
doc.add_paragraph(
    '  ```cpp\n'
    '  delete[] arr; // deallocates the array\n'
    '  ```'
)

# 4. Arrays of Arrays (2D Arrays)
doc.add_heading('4. Arrays of Arrays (2D Arrays)', level=2)
doc.add_paragraph('- Declaration of 2D Arrays: Define a matrix-like structure with rows and columns.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int arr[3][4]; // 2D array with 3 rows and 4 columns\n'
    '  ```'
)
doc.add_paragraph('- Find element in a 2D Array: Access a specific element using row and column indices.')
doc.add_paragraph(
    '  ```cpp\n'
    '  int value = arr[1][2]; // accesses the element at row 1, column 2\n'
    '  ```'
)

# 5. Class Concept
doc.add_heading('5. Class Concept', level=2)
doc.add_paragraph('- Simple class declaration: Define a class with members and methods.')
doc.add_paragraph(
    '  ```cpp\n'
    '  class MyClass {\n'
    '  public:\n'
    '      int myVar;\n'
    '      void myMethod();\n'
    '  };\n'
    '  ```'
)
doc.add_paragraph('- Class objects declaration: Create an instance of a class.')
doc.add_paragraph(
    '  ```cpp\n'
    '  MyClass obj; // obj is an instance of MyClass\n'
    '  ```'
)
doc.add_paragraph('- Class getters, setters, return string representation: Methods to access, modify, and represent class data.')
doc.add_paragraph(
    '  ```cpp\n'
    '  class MyClass {\n'
    '  private:\n'
    '      int myVar;\n'
    '  public:\n'
    '      void setMyVar(int v) { myVar = v; }\n'
    '      int getMyVar() { return myVar; }\n'
    '      std::string toString() { return "Value: " + std::to_string(myVar); }\n'
    '  };\n'
    '  ```'
)
doc.add_paragraph('- Class methods declaration and implementation: Define functions inside and outside the class definition.')
doc.add_paragraph(
    '  ```cpp\n'
    '  void MyClass::myMethod() {\n'
    '      // method implementation\n'
    '  }\n'
    '  ```'
)
doc.add_paragraph('- Access modifiers:')
doc.add_paragraph('  - public: accessible from outside the class.')
doc.add_paragraph('  - private: accessible only within the class.')
doc.add_paragraph('- Basic constructors: Special methods to initialize objects.')
doc.add_paragraph(
    '  ```cpp\n'
    '  MyClass() { myVar = 0; } // default constructor\n'
    '  MyClass(int v) { myVar = v; } // parameterized constructor\n'
    '  ```'
)
doc.add_paragraph('- Destructor: Cleans up when an object is destroyed.')
doc.add_paragraph(
    '  ```cpp\n'
    '  ~MyClass() { // cleanup code }\n'
    '  ```'
)
doc.add_paragraph('- Deep vs. Shallow copies, Rule of 3: Implement copy constructor, assignment operator, and destructor to manage dynamic memory.')
doc.add_paragraph('- Inheritance: Derive a class from a base class.')
doc.add_paragraph(
    '  ```cpp\n'
    '  class Derived : public Base {\n'
    '      // derived class code\n'
    '  };\n'
    '  ```'
)
doc.add_paragraph('- Polymorphism: Use virtual functions for polymorphic behavior.')
doc.add_paragraph(
    '  ```cpp\n'
    '  class Base {\n'
    '  public:\n'
    '      virtual void show() { /*...*/ }\n'
    '  };\n'
    '  class Derived : public Base {\n'
    '  public:\n'
    '      void show() override { /*...*/ }\n'
    '  };\n'
    '  ```'
)
doc.add_paragraph('- Abstract classes: Classes with at least one pure virtual function.')
doc.add_paragraph(
    '  ```cpp\n'
    '  class Abstract {\n'
    '  public:\n'
    '      virtual void pureVirtual() = 0; // pure virtual function\n'
    '  };\n'
    '  ```'
)
doc.add_paragraph('- Dynamic cast: Safely cast pointers to a derived class.')
doc.add_paragraph(
    '  ```cpp\n'
    '  Base* b = new Derived();\n'
    '  Derived* d = dynamic_cast<Derived*>(b);\n'
    '  ```'
)

# 6. Contents from CSC1230
doc.add_heading('6. Contents from CSC1230', level=2)
doc.add_paragraph('Review the basics from your CSC1230 course to ensure you understand foundational concepts such as basic syntax, control structures, functions, and basic data structures.')

# Save the document
file_path = "/mnt/data/C++_Cheat_Sheet_Final_Exam.docx"
doc.save(file_path)

file_path
