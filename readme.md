### Sun microsystem
- Open JDK is the main one

JDK - tools & library

JRE - gives env to run java program

JVM - place where actual java program runs

![Image description](/public/1.png)

- Everything in Java should be inside the class

![Image description](/public/2.png)

![Image description](/public/3.png)


### quick learn
```java

class Test{
    public static void main(String[] args){
        System.out.println("Hello World!");
        System.out.println(args[0]);
        System.out.println(args[1]);
    }
}

/*
ekanshgupta@Ekanshs-Air Java % java Test one two
Hello World!
one
two
*/
```

## Data Types
```java
class Test{
    public static void main(String[] args){
        // Whole Numbers
            // byte     - 1
            // short    - 2
            // int      - 4
            // long     - 8

        byte a = 128;
        /*
        Test.java:9: error: incompatible types: possible lossy conversion from int to byte
            byte a = 128;
                 ^
        1 error
        */

        // -2^(n-1) -> +2^(n-1) - 1

        System.out.println(Byte.MIN_VALUE);     // -128
        System.out.println(Byte.MAX_VALUE);     // 127

        long a1 = 53453342342342;
        /*
        Test.java:22: error: integer number too large
            long a1 = 53453342342342;
                  ^
        1 error
        */
        long a1 = 53453342342342l; // 'l' is required if value is outside int range becz bydefault it consider as int

        // Decimal
            // float - 7 digit of precision
            // double
        
        float a = 323.43434423f;     // required 'f' to represent in float
        double b = 332.3423432;
        System.out.println(a);
        System.out.println(b);

        System.out.println(Float.MIN_VALUE);
        System.out.println(Float.MAX_VALUE);
        /*
        323.43436
        332.3423432
        1.4E-45
        3.4028235E38
        */

       // Character
            // char

        char c = 'a';
        System.out.println(c);
        System.out.println((int) c);
        System.out.println((int) Character.MIN_VALUE);
        System.out.println((int) Character.MAX_VALUE);
        /*
        a
        97
        0
        65535
        */

       // boolean
        boolean d = true;
        System.out.println(d);   // true

        long a = Long.MAX_VALUE;    // 01111111 11111111 11111111 11111111 11111111 11111111 11111111 11111111
        System.out.println(a);      // 9223372036854775807
        int b = (int) a;    // 11111111 11111111 11111111 11111111
        System.out.println(b);      // -1 becz of 2's complement

        System.out.println(Integer.toBinaryString(5));  // 101

        int a = 438347634;
        int b = a * 24223;
        System.out.println(b);  // 935582670
        // expected actual response is 10618094738382

        long d = a * 24223;
        System.out.println(d);  // 935582670

        long e = 438347634;
        long f = e * 24223;
        System.out.println(f);  // 10618094738382
       
        byte g = 5;
        g = g + 10;
        System.out.println(g);
        
        /*
        Test.java:4: error: incompatible types: possible lossy conversion from int to byte
            g = g + 10;
                ^
        1 error
        */

    }
}
```

## Operators
```java
class Test{
    public static void main(String[] args){
        /*
        and operator &
        or operator |
        xor ^
        not ~
        left shift <<
        right shift >>
        unsigned right shift >>>
        */

       int a = 5;
       int b = ~a;
       System.out.println(b);   // -6 becz 2's complliment
       System.out.println(Integer.toBinaryString(b));   // 11111111111111111111111111111010
       System.out.println(b>>2);    // -2
       System.out.println(b>>>2);   // 1073741822
    }
}
```

## print statement
```java
class Test{
    public static void main(String[] args){
    //    System.out.println(System.getenv());
       System.out.println("Sum" + 1 + 2);   // Sum12
       System.out.printf("%s of %d & %d = %d\n", "Sum", 1, 2, (1+2));   // Sum of 1 & 2 = 3
       System.out.printf("%s of %d & %.3f = %.2f\n", "Sum", 1, 2.3f, 1+2.3f);   // Sum of 1 & 2.300 = 3.30
    }
}
```

## String
- Immutable
```java
class Test{
    public static void main(String[] args){
        String name = "Ekansh Gupta";
        System.out.println(name);   // Ekansh Gupta
        String str1 = new String("Ekansh Gupta");
        System.out.println(str1);    // Ekansh Gupta
        String str2 = new String("Ekansh Gupta");
        System.out.println(str2);    // Ekansh Gupta

        System.out.println(str1 == str2);   // false

        String name2 = "Ekansh Gupta";

        System.out.println(name == name2);  // true

        Student std1 = new Student();
        std1.name = "Ekansh";
        std1.rollno = 1;
        std1.address = "Bewar";

        System.out.println(std1.name);  // Ekansh
    }
}
```

### String Methods
```java
class Test{
    public static void main(String[] args){
        String str1 = "Ekansh Gupta";
        System.out.println(str1.length());  // 12
        System.out.println(str1.charAt(2)); // a
        System.out.println(str1.charAt(str1.length()-1));   // a
        String str2 = "Ekansh gupta";
        System.out.println(str1.equals(str2));  // false
        System.out.println(str1.equalsIgnoreCase(str2));    // true
        System.out.println(str1.compareTo(str2));   // -32
        String str3 = "  Ekansh   ";
        System.out.println(str3.trim());    // Ekansh
        System.out.println(str1.substring(2, 5));   // ans
        System.out.println(str1.toUpperCase()); // EKANSH GUPTA
        System.out.println(str1.toLowerCase()); // ekansh gupta
        System.out.println(str1.replace("up", "xx"));   // Ekansh Gxxta
        System.out.println(str1.contains("gup"));   // false
        System.out.println(str1.startsWith("Gu"));  // false
        System.out.println(str1.endsWith("ta"));    // true
        String str4 = "   ";
        System.out.println(str4.isEmpty());   // false
        System.out.println(str4.isBlank());   // true
        System.out.println(str1.indexOf("a"));  // 2
        System.out.println(str1.lastIndexOf("a"));  // 11
        System.out.println(str1.indexOf("a", 5));   // 11

        // Specail Methods
        int a1 = 45;
        String str5 = String.valueOf(a1);
        System.out.println(str5);   // 45
        String str6 = String.format("Hii %s %d", "Everyone", 100);
        System.out.println(str6);   // Hii Everyone 100
    }
}

```

## Logical operators
```java 
class Test{
    public static void main(String[] args){
        // Relational Operators
            // < > == != 
        
        // Logical Operators
            // and &&, or ||, not !

        // Conditional

        if(1<2){
            System.out.println("if block executed");
        }
        else if(1>0){
            System.out.println("else if block executed");
        }
        else{
            System.out.println("else block executed");
        }



        // Switch Case 
        // - always use the break statement to break the flow if middle becomes true
        // - Without {} backets only allow one line statement 
        int day = 7;
        switch(day){
            case 1:{
                System.out.println("Monday");
                break;
            }
            case 2:{
                System.out.println("Tuesday");
                break;
            }
            case 3:{
                System.out.println("Wednesday");
                break;
            }
            case 4:{
                System.out.println("Thursday");
                break;
            }
            case 5:{
                System.out.println("Friday");
                break;
            }
            case 6:{
                System.out.println("Saturday");
                break;
            }
            case 7:{
                System.out.println("Sunday");
                break;
            }
            default:{
                System.out.println("Incorrect day");
            }
        }
    }
}
```

## Loops

```java
class Test{
    public static void main(String[] args){
        // While loop
        int i = 0;
        while(i<10){
            System.out.println(i);
            i++;
        }

        // do while
        do{
            System.out.println(i);
            i++;
        }while(i<10);

        // for loop
        for(int j = 0; j<10; j++){
            System.out.println(j);
        }

        // Problem-1
        /*
            1
            10
            100
            1000
            10000
            100000
        */
        for(int i=1;i<=100000;i*=10){
            System.out.println(i);
        }

        /*
            *
            **
            ***
            ****
            *****
        */
        for(int i=0;i<5;i++){
            for(int j=0;j<=i;j++){
                System.out.print('*');
            }
            System.out.println();
        }

        for(int i=0;i<10;i++){
            if(i==5) break;
            System.out.println(i);
        }

        /*
            0
            1
            2
            3
            4
        */

       for(int i=0;i<10;i++){
            if(i==5) continue;
            System.out.println(i);
        }

        /*
            0
            1
            2
            3
            4
            6
            7
            8
            9
        */

    }
}
```

## Arrays
```java
class Test{
    public static void main(String[] args){
        // - bydeafult assigned with zero value
        int[] arr = new int[10];
        arr[3] = 45;
        for(int i=0;i<arr.length;i++){
            System.out.println(arr[i]);
        }
        /*
            0
            0
            0
            45
            0
            0
            0
            0
            0
            0
        */

        int[] arr1 = {1,2,3};
        System.out.println(arr1);
        // [I@7ad041f3 --> [ = array, I = Integer, @7ad041f3 = #Code
            
        for(int i:arr1){
            System.out.println(i);
        }
        
        int[][] arr2 = new int[3][3];
        int[][] arr3 = {
            {1, 2, 3},
            {1, 2, 3},
            {1, 2, 3}
        };

        for(int i=0; i<arr3.length; i++){
            for(int j=0; j<arr3[i].length; j++){
                System.out.print(arr3[i][j]);
            }
            System.out.println();
        }
        /*
            123
            123
            123
        */

        for(int[] i:arr3){
            for(int j:i){
                System.out.print(j);
            }
            System.out.println();
        }
        /*
            123
            123
            123
        */

        int[][] zarr = new int[3][];
        zarr[0] = new int[2];
        zarr[1] = new int[3];
        zarr[2] = new int[2];
            

    }
}
```