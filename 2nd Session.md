# Titles

- [Constructors](#constructors)
- [Encapsulation](#encapsulation)
- [Access-Modifiers](#access-modifiers)
- [Destructor](#destructor)
- [Overloading-Polymorphism](#overloading-polymorphism)
- [Static-Class-Members](#static-class-members)

---



### <u>Constructors</u>

- A special Operatoin of a class

- it is & object or together

  `ex`

  ```c++
  class employee
  {
  private:
      string first_name;
      string last_name;
      string e_mail;
      string phone;
      float salary;
   
  public:
      employee()
      {
          first_name = "empty";
          last_name = "empty";
          e_mail = "empay";
          phone = "empty";
          salary = 0.0;      
          
          cout << "employee is created successfully!\n";
      }
  };
  ```

  `ex`

  ```c++
  // another way for building a constructor operation
  {
  public:
  	employee() : 
      first_name("empty"), last_name("empty"), e_mail("empty"), phone("empty"),  salary(0.0)
      {
          cout << "employee is created successfully!\n";
      }
  };
  ```



### <u>Encapsulation</u>

- access-limitation process on (properities or operations)

  `ex`

  ```c++
  int main()
  {
      employee employee1;
      
      employee1.first_name = "Ali"; // false
  }
  ```

  ```c++
  // to access (first_name) we should use what called [Encapsulated Operatoins]
  class employee
  {
  public:
     	void set_name(string input) // setter operation
      {
          first_name = input; // assigns the value
      }
      
      string get_name() // getter operation
      {
          return first_name; // gets the value
      }
  };
  
  int main()
  {
      /*
      ...
      */
      
      employee1.set_name("Ali");  // assign operation
      std::cout << get_name() << '\n'; // get operation
  }
  ```

  

### <u>Access Modifiers</u>

|     -     |             public              |             protected              |       private       |
| :-------: | :-----------------------------: | :--------------------------------: | :-----------------: |
| accessing |    any where<br>in your code    | . class itslef<br/>. child classes | . class itself only |
| inherting | inhertable to<br/>child classes |  inheritable to<br/>child classes  |   not inheritable   |



### <u>Destructor</u>

- A special operatoin of a class

- it is reversal of the structure

  `ex`

  ```c++
  class employee
  {
      ~employee()
      {
          cout << "employee is destroyed and died, successfully!\n";
      }
  };
  ```

  

### <u>Overloading Polymorphism</u>

- overlaoding on compiler

- many forms

- compile-time polymorphism or static polymorphism

  `ex`

  ```c++
  class employee
  {
  public:
      // the same name, but not the same declaration
  
      float increase_salary()
      {
          salary += 50;  
          return salary;
      }
      
     	float increase_salary(float the_increase)
      {
          salary += the_increase;
          return salary;
  	}
  };
  ```

  

### <u>Static Class Members</u>

- specialized-class variables or operations

- calling best practice => (class_name :: a_variable or an_operation)

- static variables allocated in the static data area<img src="Images\1.png" alt="missed image" width="300" height="350" style="margin:0">

  `ex`

  ```c++
  class employee
  {
  private:
     static int employees_number = 0; // initializing during declaration (best practice)
      
  public:
      
     employee()
     {
         employees_number++;      // sensitive counter for each employee
     }
      
     static int get_employees_number()
     {
         return employees_number;    // returns number of company employees, now
     }
  };
  
  int main()
  {
      employee employee1, employee2;
      
      std::cout << employee::get_employees_number() << '\n'; // employees number
  }
  ```

  