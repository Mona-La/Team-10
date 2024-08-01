```java

@PostMapping("/abracadabra")
    public Magician abracadabra(@RequestBody Hat hat){
        var magician = new Magician();
        magician.transformation = "Rabbit";
        return magician;
    }
```
```java
package com.datorium.Datorium.API;

public class Magician {
    public String transformation;
}
```
```java
package com.datorium.Datorium.API;

public class Hat {
    public String item;
}
```
![image](https://github.com/user-attachments/assets/5aff2f3e-ea56-42b5-9ec5-50745f6dcaa9)
