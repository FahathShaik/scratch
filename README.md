#This is sample project
To use @Autowired in a Spring Boot application, you need to annotate the field with the @Autowired annotation. The field will then be automatically injected with an instance of the class that implements the interface or annotated with @Component. For example, if you have a field of type `UserRepository` in your `Application` class, you can annotate it with @Autowired like this:

```
@Autowired
private UserRepository userRepository;
```

Spring Boot will then automatically inject an instance of a `UserRepository` implementation into your `Application` class.

You can also use @Autowired to inject dependencies into constructors. For example, if you have a class that has a constructor that takes a `UserRepository` as a parameter, you can annotate the constructor with @Autowired like this:

```
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public UserService(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

}
```

Spring Boot will then automatically inject an instance of a `UserRepository` implementation into the constructor of the `UserService` class.

You can also use @Autowired to inject dependencies into properties. For example, if you have a class that has a property of type `UserRepository`, you can annotate the property with @Autowired like this:

```
public class UserService {

    private UserRepository userRepository;

    @Autowired
    public void setUserRepository(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

}
```

Spring Boot will then automatically inject an instance of a `UserRepository` implementation into the `userRepository` property of the `UserService` class.

@Autowired is a powerful annotation that can be used to inject dependencies into Spring Boot applications. By using @Autowired, you can reduce the amount of code that you need to write and make your code more reusable.
