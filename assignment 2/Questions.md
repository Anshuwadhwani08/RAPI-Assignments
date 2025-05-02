1. Predict the output and explain:
```
class Data { public int X; }
Data d1 = new Data { X = 1 };
Data d2 = d1;
d2.X = 5;
Console.WriteLine(d1.X);
```

2. Predict the output 
   ```
    struct Point { public int X; }
    Point p1 = new Point { X = 10 };
    Point p2 = p1;
    p2.X = 20;
    Console.WriteLine(p1.X);
    ```

3. Predict the output 
   ```
    struct Point { public int X; }

    static void ChangePoint(ref Point p)
    {
        p.X = 100;
    }

    static void Main()
    {
        Point pt = new Point { X = 10 };
        ChangePoint(ref pt);
        Console.WriteLine(pt.X); 
    }
   ```

4. What will be output.
   
    ```
    static void ChangeString(string str)
    {
        str = "Changed";
    }

    static void Main()
    {
        string s = "Original";
        ChangeString(s);
        Console.WriteLine(s); 
    }
   ```

5. What will be output.
   
   ```
    struct S { public int X; }
    class C { public int X; }

    static void Main()
    {
        S s1 = new S { X = 1 };
        S s2 = s1;
        s2.X = 2;

        C c1 = new C { X = 1 };
        C c2 = c1;
        c2.X = 2;

        Console.WriteLine($"{s1.X} {c1.X}"); 
    }
    ```

6.  What will be output.
   
    ```
    int num = 100;
    object obj = num;
    num = 50;
    Console.WriteLine((int)obj);
    ```

7.  What will be output.
   
    ```
    void Add(ref int x)
        {
            x += 5;
        }

        int a;
        Add(ref a);
        
    ```

8. What will be output.
   
     ```
    class Employee { public string Name; }

    void Update(ref Employee emp)
    {
        emp = new Employee { Name = "Updated" };
    }

    Employee e = new Employee { Name = "Original" };
    Update(ref e);
    Console.WriteLine(e.Name);  
    ```

9. Give output
    ```
        string a = "OpenAI";
        string b = new string("OpenAI".ToCharArray());
        string c = string.Intern(b);

        Console.WriteLine(object.ReferenceEquals(a, b)); 
        Console.WriteLine(object.ReferenceEquals(a, c)); 
        Console.WriteLine(object.ReferenceEquals(b, c));     
    ```

10.  Give output
    ```
        object obj = 123;
        int num = (int)obj;

        obj = "Hello";
        try
        {
            int x = (int)obj;
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.GetType()); // ?
        }
    

11. What will be output

    ```
    class Sample
        {
            public int Data;
        }

        static void Modify(Sample s, int value)
        {
            s.Data = value;
            s = new Sample { Data = 999 };
        }

        static void Main()
        {
            Sample obj = new Sample { Data = 100 };
            Modify(obj, 200);
            Console.WriteLine(obj.Data); 
        }

    ```
   

12. give output

    ```
        class RefClass
        {
            public int Num;
        }

        static void Change(ref RefClass rc)
        {
            rc = new RefClass { Num = 999 };
        }

        static void Main()
        {
            RefClass obj = new RefClass { Num = 123 };
            Change(ref obj);
            Console.WriteLine(obj.Num); // ?
        }
    ```

13.  What will the following code output?

    
    struct MyStruct { public int X; }

    static void Main()
    {
        MyStruct ms = new MyStruct();
        object obj = ms;
        ms.X = 5;
        Console.WriteLine(((MyStruct)obj).X);
    }
    
    A. 5
    B. 0
    C. Compilation Error
    D. Runtime Error


14.  Give Output

        ```
        class Demo { public int X; }
        static void Modify(in Demo d) => d.X = 42;
        ```
    
    A. Compiles and modifies the object
    B. Compile-time error
    C. Runtime error
    D. Creates a new object
