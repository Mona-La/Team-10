``` java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTOs.User;

import java.util.ArrayList;

public class UserRepo {

    private ArrayList<User> users = new ArrayList<>();

    public int add(User user){
        users.add(user);
        return users.size();
    }

    public ArrayList<User> getUsers() {
        return users;
    }
}
```
```java
package com.datorium.Datorium.API.Services;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Repo.UserRepo;

public class UserService {
    private UserRepo userRepo;
    public UserService() {
        userRepo  = new UserRepo();
    }
    public int add(User user){
        return userRepo.add(user);
    }

    public UserRepo getUserRepo() {
        return userRepo;
    }
}

```
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Services.UserService;
import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;

@RestController
@RequestMapping("/user")
public class UserController {
    private UserService userService;

    public UserController() {
        userService = new UserService();
        //This code runs first, when creating UserController object

    }
    //CRUD (create, read, update, delete)
    //AddUser
    //UpdateUser
    //GetUser
    //DeleteUser

    @PostMapping("/add") //http://localhost:8080/test->http://localhost:8080/user/test (if it was test)
    public int add(@RequestBody User user) {
        return userService.add(user);
    }

    @GetMapping("/getlist")
    public ArrayList<User> getList() {
        return userService.getUserRepo().getUsers();
    }
}
```
<img width="839" alt="image" src="https://github.com/user-attachments/assets/4b8f20c4-af6e-43b8-9d89-7a2ba2a0e74d">
