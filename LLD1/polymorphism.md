# POLYMORPHISM 

```java
 class Parent {
    public void printInfo() {
        // Parent cannot directly access child class attributes
        // System.out.println(childAttribute); // This would not compile
        //System.out.println("parent info");
    }
     public void printChildInfo() {
         System.out.println("its parent");
     }
}

class Child extends Parent {
    private String childAttribute = "Child's Attribute 1";

    public void printChildInfo() {
        System.out.println(childAttribute); // Works here in the child class
    }
}

public class Main {
    public static void main(String[] args) {
        Parent p = new Parent();
        p.printInfo(); // Parent class cannot access child-specific attributes
        p.printChildInfo();

        Parent pc = new Child();
        p.printInfo(); // Parent class cannot access child-specific attributes
        pc.printChildInfo();

        Child c = new Child();
        c.printChildInfo(); // Child can access its own attributes
    }
}
 ```

# OUTPUT: 
its parent
Child's Attribute 1
Child's Attribute 1

# Final conclusion:
* 1-Method which has to be called is decided at rum time hence RUN TIME POLYMORPHISM
* 2-decided by the obj Which is created on R.H.S



