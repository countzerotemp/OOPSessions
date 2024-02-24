# Titles

- [Inheritance & Inheritance-Modes](#Inheritance-&-Inheritance-Modes)
- [Multi-level inheritance](#Multi-level-inheritance)
- [Multiple inheritance](#Multiple-inheritance)
- [Overriding Polymorphism](#Overriding-Polymorphism)
- [Abstraction](#Abstraction)
- [Pure virtual Concept](#Pure-virtual-Concept)

---





### *<u>Inheritance & Inheritance-Modes</u>*

- inheriting (properties & operations) from a class to another

- parent & child concepts

  

  `ex`

  ```c++
  // Inhertance Tree
  class parent 
  {
  private:
      /*
         	.. code portion ..
  
      */
  
  protected: 
      /*
      	.. code portion ..
      */
      
  public:
      /*
         	.. code portion ..
      */
  };
  
  class child : (public, protected, or private) parent
  {
      /*
      	.. code portion ..
      */
  };
  ```



- Inheritance Modes => (but, Respect The Parent Privacy!)

|      -      |                       public                        |                   protected                   |                  private                   |
| :---------: | :-------------------------------------------------: | :-------------------------------------------: | :----------------------------------------: |
| mode action | public is public<br>protected is protected in child | public & protected<br/>are protected in child | public & protected<br>are private in child |



`ex`

```c++
class employee									// Parent
{
private:
    string first_name;
    string last_name;
    string e_mail;
    string phone;
    float salary;
    
protected:
    /*
        .. code portion ..
    */
    
public:
    employee()
    {
        /*
        	.. code portion ..
        */
    }
};

class part_time_employee : public employee			// Child
{
private:
    string online_pay_account;
    
protected:
    /*
    	.. code portion ..
   	*/

public:
    // protected & public portions in (employee) are public in (part_time_employee)
    void set_online_account(string account)
    {
        online_pay_account = account;
    }
    
    string get_pay_account()
    {
        return online_pay_account;
    }
};
```





### *<u>Multi-level inheritance</u>*

- If Parent can have a Child, So It can have a Descendant
- Here, Child have become a Parent

`ex`

```c++
class retired_part_time_employee : private part_time_employee			// Descendant
{
private:
    string Indemnity;

protected:
    /*
    	.. code portion ..
    */
    
public:
    /*
    	.. code portion ..
    */
};
```





### *<u>Multiple inheritance</u>*

- Inheritance from more than 1 Parent

  `ex`

  ```c++
  class full_time_employee : public employee					// Parent
  {
  private:
      string company_pay_account;
   
  	/*
  		.. code portion ..
  	*/
  };
  
  class part_time_employee : public employee			// Parent
  {
  private:
      string online_pay_account;
      
  	/*
  		.. code portion ..
  	*/
  };
  
  class both_type_employee : public part_time_employee, public full_time_employee    // Child
  {
  	/*
  		.. code portion ..
  	*/
  };
  ```

  

- diamond-shaped inheritance (runtime error)

- comparison with other programming languages





### *<u>Overriding Polymorphism</u>*

- no overloading on the compiler
- parent-operation reimplementation
- runtime polymorphism or dynamic polymorphism

`ex`

```c++
class full_time_employee : public employee									  //parent
{
    private:
        string company_pay_account;

    public:
        virtual void pay_money()					// Operation
        {
            cout << "give full employee money\n";
        }
 
};

class both_type_employee : public part_time_employee, public full_time_employee //child
{
    public:
    void pay_money () override				// Overriden Operation, best practise
    {
        cout << "give both employee money\n";
    }
};

int main()
{
    full_time_employee *full;						// Pointer to Object
    both_type_employee both;						// Object

    full = &both;									// Child is a Parent Principle
    full -> pay_money();							// invoking child operation
}
```





### *<u>Abstraction</u>*

- focus declaration, ignore implementation

- abstract class is a strong template form
- mandatory override process for all children
- providing code reuse, and modularity
- class can be design-abstracted or explicit-abstracted
- explicit-abstracted good for you & compiler
- abstract class can't be instantiated directly
- comparison with (interface concept) in other programming languages

|     -     |   abstraction    |           interface           |
| :-------: | :--------------: | :---------------------------: |
| operation | only declaration | declaration or implementation |
| variables |   no variables   |         can contains          |





### *<u>Pure virtual Concept</u>*

- existing pure virtual, then abstraction is explicit
- at least pure virtual operation

`ex`

```c++
class employee
{
    /*
    	.. code portion ..
    */
    
public:
    virtual void employee_state() = 0;    // pure virtual operation
};

class full_time_employee : public employee
{
    public:
        void employee_state () override   // 1st child overriden
        {
            cout << "I am full time\n";
        }
};

class part_time_employee : public employee			
{    
    public:
        void employee_state () override	  // 2nd child overriden
        {
            cout << "I am part time\n";
        }
};

class both_type_employee : public part_time_employee, public full_time_employee
{
    public:
    // optional here to override the pure virtual operatoin or not (further-child)
};
```

