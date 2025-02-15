
# GENERICS
---

Yes, you can use wildcards in the above code, but there are some limitations.

Using Wildcards (?):
Wildcards (?) in generics are typically used for unknown types, particularly in method parameters where you don't need to modify the collection. However, wildcards cannot be used in generic method declarations, so the following will not work:

```java

public void printArray(?[] array) { // ❌ This is not valid syntax
    for (? element : array) {
        System.out.print(element + " ");
    }
    System.out.println();
}
```

Alternative with Bounded Wildcards (? extends Object):
You can use an unbounded wildcard (?) or bounded wildcard (? extends Object) if you change the method signature to accept a generic array:

```java

public class Util {
    public void printArray(Object[] array) { // Works, but not generic
        for (Object element : array) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
}

```
However, this loses the benefit of generic typing, since it forces all elements to be treated as Object.

Using Generics Properly:
A better approach is to retain the generic type parameter <E> while ensuring flexibility:

```java

public class Util {
    public void printArray(E[] array) { // ✅ Correct way with generics
        for (E element : array) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
}

```

When to Use Wildcards (? extends T or ? super T)?
Wildcards are mainly used with collections, like List<?>, rather than arrays, because arrays are covariant (i.e., String[] is a subtype of Object[]), while generics are invariant.

For example, the following is valid with List:

```java
public class Util {
    public void printList(List<?> list) { // Wildcards work with Lists
        for (Object element : list) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
}

```
## Final Conclusion:
* Wildcards (?) cannot be used in generic method type parameters.
* Wildcards are useful with List<?>, List<? extends T>, and List<? super T>, but not with arrays.
* For arrays, use explicit generics (<E>) instead of wildcards.




