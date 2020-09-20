Câu 4:
```java

public class MinTest {
/**
* Test of min method, of class Min.
*/
    @Test(expected = NullPointerException.class)
    public void testMin() {
        System.out.println("min");
        List list = new ArrayList();
        list.add(null);
        Object result = Min.min(list);
    }
}
```
