
# Inheritance

```java
class Parent {
    public void printInfo() {
        // Parent cannot directly access child class attributes
        // System.out.println(childAttribute); // This would not compile
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

        Parent pc = new Child();
        p.printInfo(); // Parent class cannot access child-specific attributes

        Child c = new Child();
        c.printChildInfo(); // Child can access its own attributes
    }
}

```


# Output:
Child's Attribute 1

# Final conclusion:

* Parent cannot directly access child class attributes but child can access its attibutes as well as parent 
