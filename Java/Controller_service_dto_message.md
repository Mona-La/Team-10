```java
package com.datorium.Datorium.API.DTOs;

public class Message {
    public String text;
}
```
```java
package com.datorium.Datorium.API.Services;

import com.datorium.Datorium.API.DTOs.Message;


public class MessageService {
    public String send(Message message){
        return "Message send!";
    }
}
```
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.Services.MessageService;
import com.datorium.Datorium.API.DTOs.Message;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/user")
public class MessageController {
        private MessageService messageService;

        public MessageController() {
            messageService = new MessageService();
        }

    @PostMapping("/send")
    public String send(@RequestBody Message message) {
        return messageService.send(message);
    }


}
```
<img width="791" alt="image" src="https://github.com/user-attachments/assets/965f1fa7-2b32-4072-9cc9-9a838d0734be">


