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

import java.util.List;

public class UserService {
    private UserRepo userRepo;
    public UserService() {
        userRepo  = new UserRepo();
    }
    public int add(User user){
        return userRepo.add(user);
    }

    public List<User> getUsers() {
        return userRepo.getUsers();
    }
}

```
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Services.UserService;
import org.springframework.web.bind.annotation.*;

import java.util.List;

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

    @GetMapping("/getusers")
    public List<User> getUsers() {
        return userService.getUsers();
    }
}

```
<img width="823" alt="image" src="https://github.com/user-attachments/assets/d079d080-b41c-4f42-a84c-fb8c92ce7c64">
