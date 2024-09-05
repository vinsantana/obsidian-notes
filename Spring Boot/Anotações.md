Spring Professional Certification - 6 full Tests (2V0-72.22)
Start
Practice Test 1: Test 1
Start
Practice Test 2: Test 2
Start
Practice Test 3: Test 3
Start
Practice Test 4: Test 4
Start
Practice Test 5: Test 5
Start
Practice Test 6: Test 6
Practice Test 2: Test 2
Test 2 - Results
New
Attempt 1





Question 1
Correct
What are the benefits of using Dependency Injection? (select 2)

Your selection is correct
better code reusability

Your selection is correct
improved testability

increased performance

tight coupling

Overall explanation
Dependency Injection (DI) is a design pattern widely used in Spring applications. Its primary benefits include:

Loose Coupling: Dependency Injection helps to promote loose coupling between different components in the application. Instead of each component instantiating its dependencies, the dependencies are injected into the component by an external entity. This approach makes it easy to change or swap dependencies without affecting the component.

Testability: With Dependency Injection, it becomes easy to test each component in isolation by replacing its dependencies with mock objects. This allows for better unit testing of the codebase.

Maintainability: Using DI makes the application codebase more maintainable by reducing the amount of boilerplate code that would otherwise be required for instantiation and management of dependencies.

Scalability: Applications that use Dependency Injection can be more scalable as they can be more easily divided into smaller components that can be developed and tested independently.

Some possible incorrect answers to this question could include:

Increased performance: While Dependency Injection can help to improve the design of an application, it is unlikely to have a direct impact on performance.

Reduced security risks: While Dependency Injection can help to make an application more maintainable, it is unlikely to have any direct impact on security. However, it can indirectly improve security by making it easier to update and patch the application.

Domain
Spring core
Question 2
Incorrect
Which of the following statements is accurate regarding the @RequestMapping annotation? Please select all that apply. (select 2)

Correct selection
It possesses a method attribute that allows customization of the request methods to which this method will be mapped.

By default, it’s assumed all incoming requests to URLs are of the HTTP POST kind.

Your selection is correct
It is applicable to classes that have the @Controller annotation.

Your selection is incorrect
We can define the request parameters for the method by utilizing the requestParams attribute.

Overall explanation
This annotation can be used both at the class and at the method level.

It can be used in classes with @Controller annotation.



By default, it’s assumed all incoming requests to URLs are of the HTTP GET kind.

See: https://stackoverflow.com/questions/41534933/difference-between-use-requestmapping-with-and-without-method#41545471



Optional method Element

RequestMethod[] method

The HTTP request methods to map to, narrowing the primary mapping: GET, POST, HEAD, OPTIONS, PUT, PATCH, DELETE, TRACE.

Supported at the type level as well as at the method level! When used at the type level, all method-level mappings inherit this HTTP method restriction.

See: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#method()



Optional params Element AND NOT requestParams

String[] params

The parameters of the mapped request, narrowing the primary mapping.

See: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#params()



Example:

@RequestMapping allows easy mapping of URL parameters with the @RequestParam annotation.

We are now mapping a request to a URI:

http://localhost:8080/ex/bars?id=100

@RequestMapping(value = "/ex/bars", params = "id", method = GET)
@ResponseBody
public String getBarBySimplePathWithExplicitRequestParam(
  @RequestParam("id") long id) {
    return "Get a specific Bar with id=" + id;
}
Domain
Spring MVC
Question 3
Incorrect
Which is a valid way to inject 'daily.limit' with @Value annotation? (select 2)

Correct selection
@Value("#{environment['daily.limit']}") 
int maxTransfersPerDay;
Your selection is correct
@Value("${daily.limit}")
 int maxTransfersPerDay;
@Value("#{daily.limit}") 
int maxTransfersPerDay;
Your selection is incorrect
@Value("${environment['daily.limit']}") 
int maxTransfersPerDay;
Overall explanation
Answer:

@Value("${daily.limit}") 
int maxTransfersPerDay;
and

@Value("#{environment['daily.limit']}") 
int maxTransfersPerDay;


${...} is the property placeholder syntax. It can only be used to dereference properties.

#{...} is SpEL syntax, which is far more capable and complex. It can also handle property placeholders, and a lot more besides.



You can use either ${daily.limit} or #{environment['daily.limit']} to retrieve the same value of the property, of course the latter is longer but it is based about SpEL, therefore you are able to do some operations



When accessing properties, you have to be aware, that these properties are always treated as Strings.

If you take a look at the @Value("${daily.limit}"), well, this will be evaluated as a String and there will be an implicit conversion to whatever type you require.

In that example, we expect an integer so there will be an extra conversion between a string and a integer.

So you get an integer in your class, so this applies when you use an expression.

Notice that on the right-hand side, the @Value annotation uses expression "#{environment [daily.limit']}" to inject something from the environment and there will be an implicit conversion from a String into an integer.



https://stackoverflow.com/questions/5322632/spring-expression-language-spel-with-value-dollar-vs-hash-vs



https://www.baeldung.com/spring-value-annotation

Domain
Spring core
Question 4
Correct
What is the proper syntax to enable the shutdown endpoint in a .properties file?

management.endpoint.enabled.shutdown=true

endpoint.shutdown.disabled=false

Your answer is correct
management.endpoint.shutdown.enabled=true

endpoint.shutdown.enable=true

Overall explanation
The correct answer is :
management.endpoint.metrics.enabled=true



Spring doc: https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html#actuator.endpoints.enabling

2.1. Enabling Endpoints

By default, all endpoints except for shutdown are enabled. To configure the enablement of an endpoint, use its management.endpoint.<id>.enabled property. The following example enables the shutdown endpoint:

management.endpoint.shutdown.enabled=true
If you prefer endpoint enablement to be opt-in rather than opt-out, set the management.endpoints.enabled-by-default property to false and use individual endpoint enabled properties to opt back in. The following example enables the info endpoint and disables all other endpoints:

management.endpoints.enabled-by-default=false
management.endpoint.info.enabled=true


More on endpoints: https://docs.spring.io/spring-boot/docs/current/actuator-api/htmlsingle/

Domain
Spring Actuator
Question 5
Correct
What technology is commonly used in Spring to implement security at the method level?

Multithreading is commonly used in Spring to implement security at the method level.

Spring Security is commonly used in Spring to implement security at the method level.

Your answer is correct
Aspect-oriented programming (AOP) is commonly used in Spring to implement security at the method level.

Object-oriented programming (OOP) is commonly used in Spring to implement security at the method level.

Overall explanation
The most common technology used in Spring to implement security at the method level is Aspect-Oriented Programming (AOP). AOP allows developers to separate cross-cutting concerns, such as security, from the core business logic of the application. Spring Security provides AOP-based security through the use of annotations like @PreAuthorize and @PostAuthorize.



@PreAuthorize and @PostAuthorize allow developers to define authorization rules directly in the code, making it easy to secure specific methods or parts of the application. For example, the @PreAuthorize annotation can be used to specify that a user must have a certain role or permission to access a method. The @PostAuthorize annotation can be used to filter the results of a method based on the user's roles or permissions.



Other technologies that can be used for method-level security in Spring include Spring AOP and the Spring Security Method Security Interceptor. However, AOP-based security through the use of annotations is the most commonly used approach.

Domain
Spring AOP
Question 6
Correct
Which annotations can be applied to Spring MVC controller method parameters? (select 2)

Your selection is correct
@RequestBody

@Autowired

Your selection is correct
@RequestParam

@Value

Overall explanation
@RequestParam is an annotation used to map web request parameters to a method parameter in a Spring MVC controller. It allows for the extraction of query parameters, form data, and parts of the request path. For example, @RequestParam("id") int id would map the id parameter in the request URL to the integer variable id.

https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html



@RequestBody is an annotation used to bind the request body to a method parameter. It is commonly used when the incoming request is in JSON or XML format. When the incoming request is processed, Spring will automatically deserialize the request body into the specified Java object type.

https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html



@Autowired is an annotation used to inject a Spring bean dependency into another bean. It can be applied to fields, constructors, and methods. Spring will automatically search the application context for a bean that matches the type of the field or parameter and inject it.



@Value is an annotation used to inject values into a Spring bean from properties files or environment variables. It can be applied to fields, constructors, and methods. Spring will search for a matching property in the specified property file or environment variable and inject the value into the annotated field or parameter.



Note: It's important to be aware of the potential security risks associated with using @Value to inject sensitive information, such as passwords or API keys, into Spring beans. It's generally recommended

Domain
Spring MVC
Question 7
Incorrect
What is CSRF when securing an application with Spring Boot?

CSRF is a feature for controlling access based on user roles and permissions in Spring Boot.

Your answer is incorrect
CSRF is an authentication mechanism in Spring Boot.

CSRF is a protocol for encrypting sensitive information in Spring Boot.

Correct answer
CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Overall explanation
Answer:

Cross-Site Request Forgery (CSRF)

CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Spring Boot provides built-in CSRF protection to prevent such attacks by generating and validating unique tokens.



CSRF represents a particular attack vector that Spring Security guards against, by default.

(Spring Security guards against many attack methods, but most don’t require a policy decision).

It’s a bit technical, but CSRF involves tricking already-authenticated users into clicking on rogue links.

The rogue link asks the user to authorize a request, essentially granting the malicious attacker inside access.

The best way to guard against this is to embed a nonce into secured assets and refuse requests that lack them.

A nonce is a semi-random number generated on the server that marks proper resources.

The nonce is embedded as a CSRF token and must be embedded in any state-changing bits of HTML, typically forms.



To enable CSRF protection in a Spring Boot application, you can follow these steps:



1. By default, Spring Security automatically enables CSRF protection.

So, if you have the Spring Security dependency in your project, CSRF protection is already enabled.



2. By default, Spring Security protects all HTTP methods with CSRF, except GET, HEAD, OPTIONS, and TRACE.

You can customize this behavior if needed.

For example, if you want to disable CSRF protection for a specific endpoint, you can use the csrf().ignoringAntMatchers("/your-endpoint") configuration in your Spring Security configuration class:



import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
 
public class SecurityConfig extends WebSecurityConfigurerAdapter {
 
    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .csrf()
                .ignoringAntMatchers("/your-endpoint")
            .and()
                .authorizeRequests()
                .anyRequest().authenticated()
            .and()
                .formLogin()
                .loginPage("/login")
                .permitAll();
    }
}
In this example, the CSRF protection is disabled for the /your-endpoint URL pattern.

Domain
Spring Security
Question 8
Incorrect
What should be done to enable auditing in Spring Boot Actuator?

Enable auditing by default in Spring Boot Actuator without any additional configuration.

Correct answer
Declaring a bean of type AuditEventRepository

Add the @EnableAuditing annotation in the main Spring Boot application class.

Your answer is incorrect
Install a third-party auditing library and configure it with Spring Boot Actuator.

Overall explanation
Declaring a bean of type AuditEventRepository in a Spring Boot application allows to enable auditing for Spring Boot Actuator. This is because AuditEventRepository provides the necessary storage and retrieval mechanisms for audit events generated by Actuator.



When AuditEventRepository is declared as a bean in the Spring context, Spring Boot automatically enables auditing support in Actuator. This means that audit events generated by Actuator endpoints will be stored and made available through the /auditevents endpoint.



To declare AuditEventRepository, you can create a bean of type InMemoryAuditEventRepository or configure a custom implementation that suits your needs. The bean can be defined in a configuration class using the @Bean annotation or in an XML configuration file.



Javadoc:

public interface AuditEventRepository

Repository for AuditEvents.

voidadd(AuditEvent event)

Log an event.

List<AuditEvent>find(String principal, Instant after, String type)

Find audit events of specified type relating to the specified principal that occurred after the time provided.

https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html

Domain
Spring Actuator
Question 9
Correct
How is the default property file name recognized by Spring Boot?

bootstrap.propertie

settings.properties

config.properties

Your answer is correct
application.properties

Overall explanation
Spring Boot recognizes the default property file name application.properties or application.yml in the classpath root directory as the configuration file to load properties. The name of the file is hardcoded in the Spring Boot framework, and it can be customized by setting the spring.config.name property in the application.properties file.



In addition to the default application.properties or application.yml file, Spring Boot also supports loading properties from other files, which can be specified by setting the spring.config.name and spring.config.location properties. The spring.config.name property can be set to a comma-separated list of file names without extensions, and the spring.config.location property can be set to one or more directories or file paths to search for the configuration files.



It's worth noting that Spring Boot supports a hierarchy of property files, where properties defined in files that are higher in the hierarchy (e.g., application.properties in the root directory) will override properties defined in files that are lower in the hierarchy (e.g., application.properties in a subdirectory).



See also:

SpringApplication loads properties from application.properties files in the following locations and adds them to the Spring Environment:

A /config subdirectory of the current directory

The current directory

A classpath /config package

The classpath root

The list is ordered by precedence (properties defined in locations higher in the list override those defined in lower locations).

https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-application-property-files



Domain
Spring core
Question 10
Correct
What is the logging level set by default in Spring Boot?

Your answer is correct
INFO

DEBUG

ERROR

WARN

Overall explanation
INFO



The default logging level of the Logger is preset to INFO, meaning that TRACE and DEBUG messages are not visible.

https://www.baeldung.com/spring-boot-logging#1-default-logback-logging



See also:

https://docs.spring.io/spring-boot/docs/2.1.6.RELEASE/reference/html/boot-features-logging.html

Domain
Spring core
Question 11
Incorrect
Which testing dependencies come with spring-boot-starter-test?

Your selection is correct
AssertJ

Your selection is correct
Mockito

Your selection is correct
Hamcrest

Correct selection
Spring Test & Spring Boot Test

Your selection is correct
JUnit

Correct selection
JSONassert

Correct selection
JsonPath

Overall explanation
All of above



The spring-boot-starter-test “Starter” (in the test scope) contains the following provided libraries:



JUnit 4: The de-facto standard for unit testing Java applications.

Spring Test & Spring Boot Test: Utilities and integration test support for Spring Boot applications.

AssertJ: A fluent assertion library.

Hamcrest: A library of matcher objects (also known as constraints or predicates).

Mockito: A Java mocking framework.

JSONassert: An assertion library for JSON.

JsonPath: XPath for JSON.



We generally find these common libraries to be useful when writing tests.

If these libraries do not suit your needs, you can add additional test dependencies of your own.



SpringDoc :

https://docs.spring.io/spring-boot/docs/2.1.18.RELEASE/reference/html/boot-features-testing.html#boot-features-test-scope-dependencies

Domain
Testing
Question 12
Incorrect
Which Spring bean scope is described as "Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext."?

session

Correct answer
request

prototype

Your answer is incorrect
singleton

Overall explanation
Springdoc:

The scopes supported out of the box are listed below:

singleton

(Default) Scopes a single bean definition to a single object instance for each Spring IoC container.

prototype

Scopes a single bean definition to any number of object instances.

request

Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext.

session

Scopes a single bean definition to the lifecycle of an HTTP Session. Only valid in the context of a web-aware Spring ApplicationContext.

application

Scopes a single bean definition to the lifecycle of a ServletContext. Only valid in the context of a web-aware Spring ApplicationContext.

websocket

Scopes a single bean definition to the lifecycle of a WebSocket. Only valid in the context of a web-aware Spring ApplicationContext.



https://docs.spring.io/spring-framework/reference/core/beans/factory-scoSpring Professional Certification - 6 full Tests (2V0-72.22)
Start
Practice Test 1: Test 1
Start
Practice Test 2: Test 2
Start
Practice Test 3: Test 3
Start
Practice Test 4: Test 4
Start
Practice Test 5: Test 5
Start
Practice Test 6: Test 6
Practice Test 2: Test 2
Test 2 - Results
New
Attempt 1





Question 1
Correct
What are the benefits of using Dependency Injection? (select 2)

Your selection is correct
better code reusability

Your selection is correct
improved testability

increased performance

tight coupling

Overall explanation
Dependency Injection (DI) is a design pattern widely used in Spring applications. Its primary benefits include:

Loose Coupling: Dependency Injection helps to promote loose coupling between different components in the application. Instead of each component instantiating its dependencies, the dependencies are injected into the component by an external entity. This approach makes it easy to change or swap dependencies without affecting the component.

Testability: With Dependency Injection, it becomes easy to test each component in isolation by replacing its dependencies with mock objects. This allows for better unit testing of the codebase.

Maintainability: Using DI makes the application codebase more maintainable by reducing the amount of boilerplate code that would otherwise be required for instantiation and management of dependencies.

Scalability: Applications that use Dependency Injection can be more scalable as they can be more easily divided into smaller components that can be developed and tested independently.

Some possible incorrect answers to this question could include:

Increased performance: While Dependency Injection can help to improve the design of an application, it is unlikely to have a direct impact on performance.

Reduced security risks: While Dependency Injection can help to make an application more maintainable, it is unlikely to have any direct impact on security. However, it can indirectly improve security by making it easier to update and patch the application.

Domain
Spring core
Question 2
Incorrect
Which of the following statements is accurate regarding the @RequestMapping annotation? Please select all that apply. (select 2)

Correct selection
It possesses a method attribute that allows customization of the request methods to which this method will be mapped.

By default, it’s assumed all incoming requests to URLs are of the HTTP POST kind.

Your selection is correct
It is applicable to classes that have the @Controller annotation.

Your selection is incorrect
We can define the request parameters for the method by utilizing the requestParams attribute.

Overall explanation
This annotation can be used both at the class and at the method level.

It can be used in classes with @Controller annotation.



By default, it’s assumed all incoming requests to URLs are of the HTTP GET kind.

See: https://stackoverflow.com/questions/41534933/difference-between-use-requestmapping-with-and-without-method#41545471



Optional method Element

RequestMethod[] method

The HTTP request methods to map to, narrowing the primary mapping: GET, POST, HEAD, OPTIONS, PUT, PATCH, DELETE, TRACE.

Supported at the type level as well as at the method level! When used at the type level, all method-level mappings inherit this HTTP method restriction.

See: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#method()



Optional params Element AND NOT requestParams

String[] params

The parameters of the mapped request, narrowing the primary mapping.

See: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#params()



Example:

@RequestMapping allows easy mapping of URL parameters with the @RequestParam annotation.

We are now mapping a request to a URI:

http://localhost:8080/ex/bars?id=100

@RequestMapping(value = "/ex/bars", params = "id", method = GET)
@ResponseBody
public String getBarBySimplePathWithExplicitRequestParam(
  @RequestParam("id") long id) {
    return "Get a specific Bar with id=" + id;
}
Domain
Spring MVC
Question 3
Incorrect
Which is a valid way to inject 'daily.limit' with @Value annotation? (select 2)

Correct selection
@Value("#{environment['daily.limit']}") 
int maxTransfersPerDay;
Your selection is correct
@Value("${daily.limit}")
 int maxTransfersPerDay;
@Value("#{daily.limit}") 
int maxTransfersPerDay;
Your selection is incorrect
@Value("${environment['daily.limit']}") 
int maxTransfersPerDay;
Overall explanation
Answer:

@Value("${daily.limit}") 
int maxTransfersPerDay;
and

@Value("#{environment['daily.limit']}") 
int maxTransfersPerDay;


${...} is the property placeholder syntax. It can only be used to dereference properties.

#{...} is SpEL syntax, which is far more capable and complex. It can also handle property placeholders, and a lot more besides.



You can use either ${daily.limit} or #{environment['daily.limit']} to retrieve the same value of the property, of course the latter is longer but it is based about SpEL, therefore you are able to do some operations



When accessing properties, you have to be aware, that these properties are always treated as Strings.

If you take a look at the @Value("${daily.limit}"), well, this will be evaluated as a String and there will be an implicit conversion to whatever type you require.

In that example, we expect an integer so there will be an extra conversion between a string and a integer.

So you get an integer in your class, so this applies when you use an expression.

Notice that on the right-hand side, the @Value annotation uses expression "#{environment [daily.limit']}" to inject something from the environment and there will be an implicit conversion from a String into an integer.



https://stackoverflow.com/questions/5322632/spring-expression-language-spel-with-value-dollar-vs-hash-vs



https://www.baeldung.com/spring-value-annotation

Domain
Spring core
Question 4
Correct
What is the proper syntax to enable the shutdown endpoint in a .properties file?

management.endpoint.enabled.shutdown=true

endpoint.shutdown.disabled=false

Your answer is correct
management.endpoint.shutdown.enabled=true

endpoint.shutdown.enable=true

Overall explanation
The correct answer is :
management.endpoint.metrics.enabled=true



Spring doc: https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html#actuator.endpoints.enabling

2.1. Enabling Endpoints

By default, all endpoints except for shutdown are enabled. To configure the enablement of an endpoint, use its management.endpoint.<id>.enabled property. The following example enables the shutdown endpoint:

management.endpoint.shutdown.enabled=true
If you prefer endpoint enablement to be opt-in rather than opt-out, set the management.endpoints.enabled-by-default property to false and use individual endpoint enabled properties to opt back in. The following example enables the info endpoint and disables all other endpoints:

management.endpoints.enabled-by-default=false
management.endpoint.info.enabled=true


More on endpoints: https://docs.spring.io/spring-boot/docs/current/actuator-api/htmlsingle/

Domain
Spring Actuator
Question 5
Correct
What technology is commonly used in Spring to implement security at the method level?

Multithreading is commonly used in Spring to implement security at the method level.

Spring Security is commonly used in Spring to implement security at the method level.

Your answer is correct
Aspect-oriented programming (AOP) is commonly used in Spring to implement security at the method level.

Object-oriented programming (OOP) is commonly used in Spring to implement security at the method level.

Overall explanation
The most common technology used in Spring to implement security at the method level is Aspect-Oriented Programming (AOP). AOP allows developers to separate cross-cutting concerns, such as security, from the core business logic of the application. Spring Security provides AOP-based security through the use of annotations like @PreAuthorize and @PostAuthorize.



@PreAuthorize and @PostAuthorize allow developers to define authorization rules directly in the code, making it easy to secure specific methods or parts of the application. For example, the @PreAuthorize annotation can be used to specify that a user must have a certain role or permission to access a method. The @PostAuthorize annotation can be used to filter the results of a method based on the user's roles or permissions.



Other technologies that can be used for method-level security in Spring include Spring AOP and the Spring Security Method Security Interceptor. However, AOP-based security through the use of annotations is the most commonly used approach.

Domain
Spring AOP
Question 6
Correct
Which annotations can be applied to Spring MVC controller method parameters? (select 2)

Your selection is correct
@RequestBody

@Autowired

Your selection is correct
@RequestParam

@Value

Overall explanation
@RequestParam is an annotation used to map web request parameters to a method parameter in a Spring MVC controller. It allows for the extraction of query parameters, form data, and parts of the request path. For example, @RequestParam("id") int id would map the id parameter in the request URL to the integer variable id.

https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html



@RequestBody is an annotation used to bind the request body to a method parameter. It is commonly used when the incoming request is in JSON or XML format. When the incoming request is processed, Spring will automatically deserialize the request body into the specified Java object type.

https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html



@Autowired is an annotation used to inject a Spring bean dependency into another bean. It can be applied to fields, constructors, and methods. Spring will automatically search the application context for a bean that matches the type of the field or parameter and inject it.



@Value is an annotation used to inject values into a Spring bean from properties files or environment variables. It can be applied to fields, constructors, and methods. Spring will search for a matching property in the specified property file or environment variable and inject the value into the annotated field or parameter.



Note: It's important to be aware of the potential security risks associated with using @Value to inject sensitive information, such as passwords or API keys, into Spring beans. It's generally recommended

Domain
Spring MVC
Question 7
Incorrect
What is CSRF when securing an application with Spring Boot?

CSRF is a feature for controlling access based on user roles and permissions in Spring Boot.

Your answer is incorrect
CSRF is an authentication mechanism in Spring Boot.

CSRF is a protocol for encrypting sensitive information in Spring Boot.

Correct answer
CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Overall explanation
Answer:

Cross-Site Request Forgery (CSRF)

CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Spring Boot provides built-in CSRF protection to prevent such attacks by generating and validating unique tokens.



CSRF represents a particular attack vector that Spring Security guards against, by default.

(Spring Security guards against many attack methods, but most don’t require a policy decision).

It’s a bit technical, but CSRF involves tricking already-authenticated users into clicking on rogue links.

The rogue link asks the user to authorize a request, essentially granting the malicious attacker inside access.

The best way to guard against this is to embed a nonce into secured assets and refuse requests that lack them.

A nonce is a semi-random number generated on the server that marks proper resources.

The nonce is embedded as a CSRF token and must be embedded in any state-changing bits of HTML, typically forms.



To enable CSRF protection in a Spring Boot application, you can follow these steps:



1. By default, Spring Security automatically enables CSRF protection.

So, if you have the Spring Security dependency in your project, CSRF protection is already enabled.



2. By default, Spring Security protects all HTTP methods with CSRF, except GET, HEAD, OPTIONS, and TRACE.

You can customize this behavior if needed.

For example, if you want to disable CSRF protection for a specific endpoint, you can use the csrf().ignoringAntMatchers("/your-endpoint") configuration in your Spring Security configuration class:



import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
 
public class SecurityConfig extends WebSecurityConfigurerAdapter {
 
    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .csrf()
                .ignoringAntMatchers("/your-endpoint")
            .and()
                .authorizeRequests()
                .anyRequest().authenticated()
            .and()
                .formLogin()
                .loginPage("/login")
                .permitAll();
    }
}
In this example, the CSRF protection is disabled for the /your-endpoint URL pattern.

Domain
Spring Security
Question 8
Incorrect
What should be done to enable auditing in Spring Boot Actuator?

Enable auditing by default in Spring Boot Actuator without any additional configuration.

Correct answer
Declaring a bean of type AuditEventRepository

Add the @EnableAuditing annotation in the main Spring Boot application class.

Your answer is incorrect
Install a third-party auditing library and configure it with Spring Boot Actuator.

Overall explanation
Declaring a bean of type AuditEventRepository in a Spring Boot application allows to enable auditing for Spring Boot Actuator. This is because AuditEventRepository provides the necessary storage and retrieval mechanisms for audit events generated by Actuator.



When AuditEventRepository is declared as a bean in the Spring context, Spring Boot automatically enables auditing support in Actuator. This means that audit events generated by Actuator endpoints will be stored and made available through the /auditevents endpoint.



To declare AuditEventRepository, you can create a bean of type InMemoryAuditEventRepository or configure a custom implementation that suits your needs. The bean can be defined in a configuration class using the @Bean annotation or in an XML configuration file.



Javadoc:

public interface AuditEventRepository

Repository for AuditEvents.

voidadd(AuditEvent event)

Log an event.

List<AuditEvent>find(String principal, Instant after, String type)

Find audit events of specified type relating to the specified principal that occurred after the time provided.

https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html

Domain
Spring Actuator
Question 9
Correct
How is the default property file name recognized by Spring Boot?

bootstrap.propertie

settings.properties

config.properties

Your answer is correct
application.properties

Overall explanation
Spring Boot recognizes the default property file name application.properties or application.yml in the classpath root directory as the configuration file to load properties. The name of the file is hardcoded in the Spring Boot framework, and it can be customized by setting the spring.config.name property in the application.properties file.



In addition to the default application.properties or application.yml file, Spring Boot also supports loading properties from other files, which can be specified by setting the spring.config.name and spring.config.location properties. The spring.config.name property can be set to a comma-separated list of file names without extensions, and the spring.config.location property can be set to one or more directories or file paths to search for the configuration files.



It's worth noting that Spring Boot supports a hierarchy of property files, where properties defined in files that are higher in the hierarchy (e.g., application.properties in the root directory) will override properties defined in files that are lower in the hierarchy (e.g., application.properties in a subdirectory).



See also:

SpringApplication loads properties from application.properties files in the following locations and adds them to the Spring Environment:

A /config subdirectory of the current directory

The current directory

A classpath /config package

The classpath root

The list is ordered by precedence (properties defined in locations higher in the list override those defined in lower locations).

https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-application-property-files



Domain
Spring core
Question 10
Correct
What is the logging level set by default in Spring Boot?

Your answer is correct
INFO

DEBUG

ERROR

WARN

Overall explanation
INFO



The default logging level of the Logger is preset to INFO, meaning that TRACE and DEBUG messages are not visible.

https://www.baeldung.com/spring-boot-logging#1-default-logback-logging



See also:

https://docs.spring.io/spring-boot/docs/2.1.6.RELEASE/reference/html/boot-features-logging.html

Domain
Spring core
Question 11
Incorrect
Which testing dependencies come with spring-boot-starter-test?

Your selection is correct
AssertJ

Your selection is correct
Mockito

Your selection is correct
Hamcrest

Correct selection
Spring Test & Spring Boot Test

Your selection is correct
JUnit

Correct selection
JSONassert

Correct selection
JsonPath

Overall explanation
All of above



The spring-boot-starter-test “Starter” (in the test scope) contains the following provided libraries:



JUnit 4: The de-facto standard for unit testing Java applications.

Spring Test & Spring Boot Test: Utilities and integration test support for Spring Boot applications.

AssertJ: A fluent assertion library.

Hamcrest: A library of matcher objects (also known as constraints or predicates).

Mockito: A Java mocking framework.

JSONassert: An assertion library for JSON.

JsonPath: XPath for JSON.



We generally find these common libraries to be useful when writing tests.

If these libraries do not suit your needs, you can add additional test dependencies of your own.



SpringDoc :

https://docs.spring.io/spring-boot/docs/2.1.18.RELEASE/reference/html/boot-features-testing.html#boot-features-test-scope-dependencies

Domain
Testing
Question 12
Incorrect
Which Spring bean scope is described as "Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext."?

session

Correct answer
request

prototype

Your answer is incorrect
singleton

Overall explanation
Springdoc:

The scopes supported out of the box are listed below:

singleton

(Default) Scopes a single bean definition to a single object instance for each Spring IoC container.

prototype

Scopes a single bean definition to any number of object instances.

request

Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext.

session

Scopes a single bean definition to the lifecycle of an HTTP Session. Only valid in the context of a web-aware Spring ApplicationContext.

application

Scopes a single bean definition to the lifecycle of a ServletContext. Only valid in the context of a web-aware Spring ApplicationContext.

websocket

Scopes a single bean definition to the lifecycle of a WebSocket. Only valid in the context of a web-aware Spring ApplicationContext.



https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.htmlpes.html

Spring Professional Certification - 6 full Tests (2V0-72.22)

## Course content

## Overview

## Q&AQuestions and answers

## Notes

## Announcements

## Reviews

## Learning tools

### Practice tests

- Lecture completed. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 1: Test 1
    
- Lecture completed. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 2: Test 2
    
- Lecture incomplete. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 3: Test 3
    
- Lecture incomplete. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 4: Test 4
    
- Lecture incomplete. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 5: Test 5
    
- Lecture incomplete. Progress cannot be changed for this item.
    
    Start
    
    Practice Test 6: Test 6
    

## Practice Test 2: Test 2

## Test 2 - Results

Back to result overview

New

[Share feedback](https://survey.alchemer.com/s3/7719142/Practice-tests-learner-csat/?user_id=31531646&course_id=5247636&quiz_id=5845184)

Attempt 1

All domains

- 60 all
- 31 correct
- 29 incorrect
- 0 skipped
- 0 marked

Collapse all questions

Question 1Correct

What are the benefits of using Dependency Injection? (select 2)

Your selection is correct

better code reusability

Your selection is correct

improved testability

increased performance

tight coupling

Overall explanation

Dependency Injection (DI) is a design pattern widely used in Spring applications. Its primary benefits include:

1. **Loose Coupling**: Dependency Injection helps to promote loose coupling between different components in the application. Instead of each component instantiating its dependencies, the dependencies are injected into the component by an external entity. This approach makes it easy to change or swap dependencies without affecting the component.
    
2. **Testability**: With Dependency Injection, it becomes easy to test each component in isolation by replacing its dependencies with mock objects. This allows for better unit testing of the codebase.
    
3. **Maintainability**: Using DI makes the application codebase more maintainable by reducing the amount of boilerplate code that would otherwise be required for instantiation and management of dependencies.
    
4. Scalability: Applications that use Dependency Injection can be more scalable as they can be more easily divided into smaller components that can be developed and tested independently.
    

Some possible incorrect answers to this question could include:

1. **Increased performance**: While Dependency Injection can help to improve the design of an application, it is unlikely to have a direct impact on performance.
    
2. Reduced security risks: While Dependency Injection can help to make an application more maintainable, it is unlikely to have any direct impact on security. However, it can indirectly improve security by making it easier to update and patch the application.
    

Domain

Spring core

Question 2Incorrect

Which of the following statements is accurate regarding the @RequestMapping annotation? Please select all that apply. (select 2)

Correct selection

It possesses a `method` attribute that allows customization of the request methods to which this method will be mapped.

By default, it’s assumed all incoming requests to URLs are of the HTTP POST kind.

Your selection is correct

It is applicable to classes that have the `@Controller` annotation.

Your selection is incorrect

We can define the request parameters for the method by utilizing the `requestParams` attribute.

Overall explanation

This annotation can be used both at the **class** and at the method level.

It **can be used in classes** with `@Controller` annotation.

  

By default, it’s assumed all incoming requests to URLs are of the HTTP **GET** kind.

See: [https://stackoverflow.com/questions/41534933/difference-between-use-requestmapping-with-and-without-method#41545471](https://stackoverflow.com/questions/41534933/difference-between-use-requestmapping-with-and-without-method#41545471)

  

**Optional** `**method**` **Element**

[RequestMethod](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMethod.html "enum class in org.springframework.web.bind.annotation")[] method

The HTTP request methods to map to, narrowing the primary mapping: GET, POST, HEAD, OPTIONS, PUT, PATCH, DELETE, TRACE.

**Supported at the type level as well as at the method level!** When used at the type level, all method-level mappings inherit this HTTP method restriction.

See: [https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#method()](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#method())

  

**Optional** `**params**` **Element AND NOT** `requestParams`

[String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html "class or interface in java.lang")[] params

The parameters of the mapped request, narrowing the primary mapping.

See[: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#params()](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html#params())

  

**Example:**

`@RequestMapping` allows easy mapping of URL parameters with the `@RequestParam` annotation.

We are now mapping a request to a URI:

`http://localhost:8080/ex/bars?id=100`

1. @RequestMapping(value = "/ex/bars", params = "id", method = GET)
2. @ResponseBody
3. public String getBarBySimplePathWithExplicitRequestParam(
4.   @RequestParam("id") long id) {
5.     return "Get a specific Bar with id=" + id;
6. }

Domain

Spring MVC

Question 3Incorrect

Which is a valid way to inject 'daily.limit' with @Value annotation? (select 2)

Correct selection

1. @Value("#{environment['daily.limit']}") 
2. int maxTransfersPerDay;

Your selection is correct

1. @Value("${daily.limit}")
2.  int maxTransfersPerDay;

1. @Value("#{daily.limit}") 
2. int maxTransfersPerDay;

Your selection is incorrect

1. @Value("${environment['daily.limit']}") 
2. int maxTransfersPerDay;

Overall explanation

Answer:

1. @Value("${daily.limit}") 
2. int maxTransfersPerDay;

and

1. @Value("#{environment['daily.limit']}") 
2. int maxTransfersPerDay;

  

`${...}` is the property placeholder syntax. It can only be used to dereference properties.

`#{...}` is SpEL syntax, which is far more capable and complex. It can also handle property placeholders, and a lot more besides.

  

You can use either `${daily.limit}` or `#{environment['daily.limit']}` to retrieve the same value of the property, of course the latter is longer but it is based about SpEL, therefore you are able to do some operations

  

When accessing properties, you have to be aware, that these properties are always treated as Strings.

If you take a look at the `@Value("${daily.limit}"`), well, this will be evaluated as a String and there will be an implicit conversion to whatever type you require.

In that example, we expect an integer so there will be an extra conversion between a string and a integer.

So you get an integer in your class, so this applies when you use an expression.

Notice that on the right-hand side, the `@Value` annotation uses expression `"#{environment [daily.limit']}`" to inject something from the environment and there will be an implicit conversion from a `String` into an `integer`.

  

[https://stackoverflow.com/questions/5322632/spring-expression-language-spel-with-value-dollar-vs-hash-vs](https://stackoverflow.com/questions/5322632/spring-expression-language-spel-with-value-dollar-vs-hash-vs)

  

[https://www.baeldung.com/spring-value-annotation](https://www.baeldung.com/spring-value-annotation)

Domain

Spring core

Question 4Correct

What is the proper syntax to enable the shutdown endpoint in a .properties file?

`management.endpoint.enabled.shutdown=true`

`endpoint.shutdown.disabled=false`

Your answer is correct

`management.endpoint.shutdown.enabled=true`

`endpoint.shutdown.enable=true`

Overall explanation

The correct answer is :  
`management.endpoint.metrics.enabled=true`

  

Spring doc: [https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html#actuator.endpoints.enabling](https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html#actuator.endpoints.enabling)

**2.1. Enabling Endpoints**

By default, all endpoints except for `shutdown` are enabled. To configure the enablement of an endpoint, use its `management.endpoint.<id>.enabled` property. The following example enables the `shutdown` endpoint:

1. management.endpoint.shutdown.enabled=true

If you prefer endpoint enablement to be opt-in rather than opt-out, set the `management.endpoints.enabled-by-default` property to `false` and use individual endpoint `enabled` properties to opt back in. The following example enables the `info` endpoint and disables all other endpoints:

1. management.endpoints.enabled-by-default=false
2. management.endpoint.info.enabled=true

  

More on endpoints: [https://docs.spring.io/spring-boot/docs/current/actuator-api/htmlsingle/](https://docs.spring.io/spring-boot/docs/current/actuator-api/htmlsingle/)

Domain

Spring Actuator

Question 5Correct

What technology is commonly used in Spring to implement security at the method level?

Multithreading is commonly used in Spring to implement security at the method level.

Spring Security is commonly used in Spring to implement security at the method level.

Your answer is correct

Aspect-oriented programming (AOP) is commonly used in Spring to implement security at the method level.

Object-oriented programming (OOP) is commonly used in Spring to implement security at the method level.

Overall explanation

The most common technology used in Spring to implement security at the method level is **Aspect-Oriented Programming (AOP).** AOP allows developers to separate cross-cutting concerns, such as security, from the core business logic of the application. Spring Security provides AOP-based security through the use of annotations like `**@PreAuthorize**` and `**@PostAuthorize**`.

  

`**@PreAuthorize**` and `**@PostAuthorize**` allow developers to define authorization rules directly in the code, making it easy to secure specific methods or parts of the application. For example, the `**@PreAuthorize**` annotation can be used to specify that a user must have a certain role or permission to access a method. The `**@PostAuthorize**` annotation can be used to filter the results of a method based on the user's roles or permissions.

  

Other technologies that can be used for method-level security in Spring include Spring AOP and the Spring Security Method Security Interceptor. However, AOP-based security through the use of annotations is the most commonly used approach.

Domain

Spring AOP

Question 6Correct

Which annotations can be applied to Spring MVC controller method parameters? (select 2)

Your selection is correct

`@RequestBody`

`@Autowired`

Your selection is correct

`@RequestParam`

`@Value`

Overall explanation

@RequestParam is an annotation used to map web request parameters **to a method parameter** in a Spring MVC controller. It allows for the extraction of query parameters, form data, and parts of the request path. For example, `**@RequestParam("id") int id**` would map the `**id**` parameter in the request URL to the integer variable `**id**`.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html)

  

@RequestBody is an annotation used to bind the request body **to a method parameter**. It is commonly used when the incoming request is in JSON or XML format. When the incoming request is processed, Spring will automatically deserialize the request body into the specified Java object type.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html)

  

@Autowired is an annotation used to inject a Spring bean dependency into another bean. It can be applied to fields, constructors, and methods. Spring will automatically search the application context for a bean that matches the type of the field or parameter and inject it.

  

@Value is an annotation used to inject values into a Spring bean from properties files or environment variables. It can be applied to fields, constructors, and methods. Spring will search for a matching property in the specified property file or environment variable and inject the value into the annotated field or parameter.

  

Note: It's important to be aware of the potential security risks associated with using @Value to inject sensitive information, such as passwords or API keys, into Spring beans. It's generally recommended

Domain

Spring MVC

Question 7Incorrect

What is CSRF when securing an application with Spring Boot?

CSRF is a feature for controlling access based on user roles and permissions in Spring Boot.

Your answer is incorrect

CSRF is an authentication mechanism in Spring Boot.

CSRF is a protocol for encrypting sensitive information in Spring Boot.

Correct answer

CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Overall explanation

Answer:

Cross-Site Request Forgery (CSRF)

CSRF is a security vulnerability where attackers trick a user's browser into performing unwanted actions.

Spring Boot provides built-in CSRF protection to prevent such attacks by generating and validating unique tokens.

  

CSRF represents a particular attack vector that Spring Security guards against, by default.

(Spring Security guards against many attack methods, but most don’t require a policy decision).

It’s a bit technical, but CSRF involves tricking already-authenticated users into clicking on rogue links.

The rogue link asks the user to authorize a request, essentially granting the malicious attacker inside access.

The best way to guard against this is to embed a nonce into secured assets and refuse requests that lack them.

A nonce is a semi-random number generated on the server that marks proper resources.

The nonce is embedded as a CSRF token and must be embedded in any state-changing bits of HTML, typically forms.

  

To enable CSRF protection in a Spring Boot application, you can follow these steps:

  

1. By default, Spring Security automatically enables CSRF protection.

So, if you have the Spring Security dependency in your project, CSRF protection is already enabled.

  

2. By default, Spring Security protects all HTTP methods with CSRF, except `GET`, `HEAD`, `OPTIONS`, and `TRACE`.

You can customize this behavior if needed.

For example, if you want to **disable** CSRF protection for a specific endpoint, you can use the `csrf().ignoringAntMatchers("/your-endpoint")` configuration in your Spring Security configuration class:

  

1. import org.springframework.security.config.annotation.web.builders.HttpSecurity;
2. import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;

4. public class SecurityConfig extends WebSecurityConfigurerAdapter {

6.     @Override
7.     protected void configure(HttpSecurity http) throws Exception {
8.         http
9.             .csrf()
10.                 .ignoringAntMatchers("/your-endpoint")
11.             .and()
12.                 .authorizeRequests()
13.                 .anyRequest().authenticated()
14.             .and()
15.                 .formLogin()
16.                 .loginPage("/login")
17.                 .permitAll();
18.     }
19. }

In this example, the CSRF protection is disabled for the `/your-endpoint` URL pattern.

Domain

Spring Security

Question 8Incorrect

What should be done to enable auditing in Spring Boot Actuator?

Enable auditing by default in Spring Boot Actuator without any additional configuration.

Correct answer

Declaring a bean of type AuditEventRepository

Add the `**@EnableAuditing**` annotation in the main Spring Boot application class.

Your answer is incorrect

Install a third-party auditing library and configure it with Spring Boot Actuator.

Overall explanation

Declaring a bean of type `**AuditEventRepository**` in a Spring Boot application allows to enable auditing for Spring Boot Actuator. This is because `**AuditEventRepository**` provides the necessary storage and retrieval mechanisms for audit events generated by Actuator.

  

When `**AuditEventRepository**` is declared as a bean in the Spring context, Spring Boot automatically enables auditing support in Actuator. This means that audit events generated by Actuator endpoints will be stored and made available through the `**/auditevents**` endpoint.

  

To declare `**AuditEventRepository**`, you can create a bean of type `**InMemoryAuditEventRepository**` or configure a custom implementation that suits your needs. The bean can be defined in a configuration class using the `**@Bean**` annotation or in an XML configuration file.

  

**Javadoc:**

public interface **AuditEventRepository**

Repository for [`AuditEvent`](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEvent.html "class in org.springframework.boot.actuate.audit")s.

`void`[`**add**`](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html#add(org.springframework.boot.actuate.audit.AuditEvent))`(`[`**AuditEvent**`](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEvent.html "class in org.springframework.boot.actuate.audit") `event)`

Log an event.

[`**List**`](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/List.html "class or interface in java.util")`<`[`**AuditEvent**`](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEvent.html "class in org.springframework.boot.actuate.audit")`>`[`**find**`](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html#find(java.lang.String,java.time.Instant,java.lang.String))`(`[`**String**`](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html "class or interface in java.lang") `principal,` [`**Instant**`](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/Instant.html "class or interface in java.time") `after,` [`**String**`](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html "class or interface in java.lang") `type)`

Find audit events of specified type relating to the specified principal that occurred [`after`](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/Instant.html#isAfter(java.time.Instant) "class or interface in java.time") the time provided.

[https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/audit/AuditEventRepository.html)

Domain

Spring Actuator

Question 9Correct

How is the default property file name recognized by Spring Boot?

`bootstrap.propertie`

`settings.properties`

`config.properties`

Your answer is correct

`application.properties`

Overall explanation

Spring Boot recognizes the default property file name `**application.properties**` or `**application.yml**` in the classpath root directory as the configuration file to load properties. The name of the file is hardcoded in the Spring Boot framework, and it can be customized by setting the `**spring.config.name**` property in the `**application.properties**` file.

  

In addition to the default `**application.properties**` or `**application.yml**` file, Spring Boot also supports loading properties from other files, which can be specified by setting the `**spring.config.name**` and `**spring.config.location**` properties. The `**spring.config.name**` property can be set to a comma-separated list of file names without extensions, and the `**spring.config.location**` property can be set to one or more directories or file paths to search for the configuration files.

  

It's worth noting that Spring Boot supports a hierarchy of property files, where properties defined in files that are higher in the hierarchy (e.g., `**application.properties**` in the root directory) will override properties defined in files that are lower in the hierarchy (e.g., `**application.properties**` in a subdirectory).

  

See also:

`SpringApplication` loads properties from `application.properties` files in the following locations and adds them to the Spring `Environment`:

1. A `/config` subdirectory of the current directory
    
2. The current directory
    
3. A classpath `/config` package
    
4. The classpath root
    

The list is ordered by precedence (properties defined in locations higher in the list override those defined in lower locations).

[https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-application-property-files](https://docs.spring.io/spring-boot/docs/2.1.9.RELEASE/reference/html/boot-features-external-config.html#boot-features-external-config-application-property-files)

  

Domain

Spring core

Question 10Correct

What is the logging level set by default in Spring Boot?

Your answer is correct

INFO

DEBUG

ERROR

WARN

Overall explanation

INFO

  

**The default logging level of the Logger is preset to INFO, meaning that _TRACE_ and _DEBUG_ messages are not visible.**

[https://www.baeldung.com/spring-boot-logging#1-default-logback-logging](https://www.baeldung.com/spring-boot-logging#1-default-logback-logging)

  

See also:

[https://docs.spring.io/spring-boot/docs/2.1.6.RELEASE/reference/html/boot-features-logging.html](https://docs.spring.io/spring-boot/docs/2.1.6.RELEASE/reference/html/boot-features-logging.html)

Domain

Spring core

Question 11Incorrect

Which testing dependencies come with **spring-boot-starter-test**?

Your selection is correct

AssertJ

Your selection is correct

Mockito

Your selection is correct

Hamcrest

Correct selection

Spring Test & Spring Boot Test

Your selection is correct

JUnit

Correct selection

JSONassert

Correct selection

JsonPath

Overall explanation

All of above

  

The spring-boot-starter-test “Starter” (in the test scope) contains the following provided libraries:

  

- **JUnit** 4: The de-facto standard for unit testing Java applications.
    
- **Spring Test & Spring Boot Test**: Utilities and integration test support for Spring Boot applications.
    
- **AssertJ**: A fluent assertion library.
    
- **Hamcrest**: A library of matcher objects (also known as constraints or predicates).
    
- **Mockito**: A Java mocking framework.
    
- **JSONassert**: An assertion library for JSON.
    
- **JsonPath**: XPath for JSON.
    

  

We generally find these common libraries to be useful when writing tests.

If these libraries do not suit your needs, you can add additional test dependencies of your own.

  

**SpringDoc :**

[https://docs.spring.io/spring-boot/docs/2.1.18.RELEASE/reference/html/boot-features-testing.html#boot-features-test-scope-dependencies](https://docs.spring.io/spring-boot/docs/2.1.18.RELEASE/reference/html/boot-features-testing.html#boot-features-test-scope-dependencies)

Domain

Testing

Question 12Incorrect

Which Spring bean scope is described as "Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring `ApplicationContext`."?

session

Correct answer

request

prototype

Your answer is incorrect

singleton

Overall explanation

**Springdoc:**

The scopes supported out of the box are listed below:

[singleton](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-singleton)

(Default) Scopes a single bean definition to a single object instance for each Spring IoC container.

[prototype](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-prototype)

Scopes a single bean definition to any number of object instances.

[**request**](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-request)

**Scopes a single bean definition to the lifecycle of a single HTTP request. That is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring** `**ApplicationContext**`**.**

[session](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-session)

Scopes a single bean definition to the lifecycle of an HTTP `Session`. Only valid in the context of a web-aware Spring `ApplicationContext`.

[application](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html#beans-factory-scopes-application)

Scopes a single bean definition to the lifecycle of a `ServletContext`. Only valid in the context of a web-aware Spring `ApplicationContext`.

[websocket](https://docs.spring.io/spring-framework/reference/web/websocket/stomp/scope.html)

Scopes a single bean definition to the lifecycle of a `WebSocket`. Only valid in the context of a web-aware Spring `ApplicationContext`.

  

[https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html)

Domain

Spring core

Question 13Correct

Which annotation can be used in Spring to give priority to a specific bean?

`**@Autowired**`

`**@Component**`

Your answer is correct

`**@Primary**`

`**@Order**`

Overall explanation

Good answer: The `**@Primary**` annotation can be used to indicate that a bean should be given higher precedence over other beans of the same type.

  

**Javadoc:**

public @interface **Primary**

Indicates that a bean should be given preference when multiple candidates are qualified to autowire a single-valued dependency. If exactly one 'primary' bean exists among the candidates, it will be the autowired value.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Primary.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Primary.html)

  

Bad answers:

1. The `**@Order**` annotation can be used to give priority to a bean, but it only works when multiple beans of the same type are present in the application context.
    
2. The `**@Autowired**` annotation can be used to give precedence to a bean, but only when used in conjunction with the `**@Qualifier**` annotation to specify a specific bean to be injected.
    
3. The `**@Component**` annotation can be used to give precedence to a bean, but only if the bean has a specific name assigned to it and is referred to using that name in other parts of the application.
    

Domain

Spring core

Question 14Incorrect

Can you identify the recommended method for UPDATE or INSERT operations in JdbcTemplate from the given options?

`query`

Correct answer

`update`

`process`

Your answer is incorrect

`execute`

Overall explanation

**Javadoc:**

public int update([String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html "class or interface in java.lang") sql) throws [DataAccessException](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/dao/DataAccessException.html "class in org.springframework.dao")

**Description copied from interface:** [`**JdbcOperations**`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/JdbcOperations.html#update(java.lang.String))

Issue a single SQL **update** operation (such as an **insert, update** or delete statement).

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/JdbcTemplate.html#update(java.lang.String)](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/JdbcTemplate.html#update(java.lang.String))

  

  

Here's an example of using the `**update**` method in `**JdbcTemplate**` to execute an SQL `**UPDATE**` statement:

1. @Autowired
2. private JdbcTemplate jdbcTemplate;

4. public void updateEmployee(int employeeId, String newEmail) {
5.     String sql = "UPDATE employees SET email = ? WHERE id = ?";
6.     int rowsAffected = jdbcTemplate.update(sql, newEmail, employeeId);
7.     System.out.println("Number of rows affected: " + rowsAffected);
8. }

In this example, we first inject an instance of `**JdbcTemplate**` using the `**@Autowired**` annotation. Then we define a method `**updateEmployee**` that takes two parameters: the `**employeeId**` to be updated, and the new email address (`**newEmail**`) that will replace the old email.

  

We create a SQL `**UPDATE**` statement and pass it as the first argument to the `**update**` method. The second argument to `**update**` is a vararg of values to be bound to any placeholders in the SQL statement. In this case, we have two placeholders: `**?**` for the new email address and `**?**` for the employee ID, and we pass `**newEmail**` and `**employeeId**` respectively as the values to be bound.

  

The `**update**` method returns an integer representing the number of rows affected by the SQL statement. Finally, we print out the number of rows affected to the console.

  

  

Domain

Data Management

Question 15Incorrect

Which of the following are valid Spring Data annotations? (select 3)

Your selection is incorrect

`@Entity`

Correct selection

`@NodeEntity`

Your selection is correct

`@Document`

Your selection is correct

`@Region`

Overall explanation

Answer:

**Valid:**

`@Document`: This annotation is used in the context of Spring Data MongoDB to mark a class as a document that can be stored in a MongoDB collection.

  

`@NodeEntity`: This annotation is used in the context of Spring Data Neo4j to mark a class as a node entity that can be stored in a Neo4j graph database.

  

`@Region`: This annotation is used in the context of Spring Data GemFire to mark a class as a data region in a GemFire cache, allowing objects of that class to be stored and managed within that region.

  

**Not specific to Spring Data:**  
`@Entity`: This annotation is typically used in the context of JPA (Java Persistence API) to mark a class as a persistent entity, allowing it to be stored in a relational database.

1. @Import({Dummy1.class, Dummy2.class})
2. public class MyConfig {
3.    // configuration code
4. }

This will import the `**Dummy1**` and `**Dummy2**` configuration classes, allowing their beans to be used in the `**MyConfig**` configuration class.

  

**Javadoc:**

public @interface **Import**

Indicates one or more _component classes_ to import — typically [`@Configuration`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Configuration.html "annotation interface in org.springframework.context.annotation") classes.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Import.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Import.html)
1. import org.springframework.boot.autoconfigure.SpringBootApplication;

3. @SpringBootApplication // same as @Configuration @EnableAutoConfiguration @ComponentScan
4. public class Application {

6. 	public static void main(String[] args) {
7. 		SpringApplication.run(Application.class, args);
8. 	}

10. }

[https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/using-boot-using-springbootapplication-annotation.html#using-boot-using-springbootapplication-annotation](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/using-boot-using-springbootapplication-annotation.html#using-boot-using-springbootapplication-annotation)


Spring doc 👉https://docs.spring.io/spring-framework/reference/core/beans/annotation-config/postconstruct-and-predestroy-annotations.html

Src.: https://www.baeldung.com/spring-transactional-propagation-isolation

file or module. This makes code maintenance and comprehension more difficult. It involves mixing various concerns, such as security, transactions, and error handling, with the core business logic. As a result, the code becomes multifunctional and harder to test.

  

2. 𝗖𝗼𝗱𝗲 𝗦𝗰𝗮𝘁𝘁𝗲𝗿𝗶𝗻𝗴 (𝗙𝘂𝗻𝗰𝘁𝗶𝗼𝗻𝗮𝗹𝗶𝘁𝘆 𝗦𝗽𝗿𝗲𝗮𝗱): Code scattering is observed when a single functionality is distributed across multiple files or modules, making it challenging to locate and fully understand that functionality. This leads to repetitive behaviors across different modules, often resulting in copy-and-paste practices to replicate the same behavior.

  

It's worth noting that code obfuscation and code injection are intentional techniques in software development:

  

- 𝗖𝗼𝗱𝗲 𝗢𝗯𝗳𝘂𝘀𝗰𝗮𝘁𝗶𝗼𝗻: Code obfuscation intentionally makes software code more intricate and less comprehensible. This approach aims to safeguard intellectual property and deter unauthorized access or reverse engineering. Techniques like renaming variables, introducing redundant code, and altering control flow create confusion in the code's interpretation.

  

- 𝐂𝐨𝐝𝐞 𝐈𝐧𝐣𝐞𝐜𝐭𝐢𝐨𝐧 (𝐃𝐞𝐩𝐞𝐧𝐝𝐞𝐧𝐜𝐲 𝐈𝐧𝐣𝐞𝐜𝐭𝐢𝐨𝐧): Code injection, in the context of Spring and software development, refers to dependency injection. This technique enhances modularity and maintainability by allowing the framework to provide and manage the components that a class requires. It simplifies code organization and relationships among components, unlike malicious code injection attacks which involve injecting harmful code into a system.


  

**ComponentScan Spring doc:**

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/ComponentScan.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/ComponentScan.html)

Configures component scanning directives for use with @[`Configuration`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Configuration.html "annotation interface in org.springframework.context.annotation") classes.

Domain

Spring Boot

Question 45Correct

`_____` is a Spring annotation used to map a web request to a specific method or class.

@PathVariable

@RequestParam

Your answer is correct

@RequestMapping

@RequestBody

Overall explanation

The `**@RequestMapping**` annotation is a versatile Spring MVC annotation used to map web requests to handler methods. It can be applied at the class or method level to specify the request URI, HTTP method, parameters, headers, and media types that the handler method should be mapped to. By using this annotation, developers can easily create RESTful web services with customizable URI mappings, request handling, and response types. The `**@RequestMapping**` annotation also supports the use of path variables, regular expressions, and content negotiation to further refine the request-mapping process.

  

@interface **RequestMapping**

Annotation for mapping web requests onto methods in request-handling classes with flexible method signatures.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html)

  

  

@interface **RequestBody**

Annotation indicating a method parameter should be bound to the body of the web request. The body of the request is passed through an [`HttpMessageConverter`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/http/converter/HttpMessageConverter.html "interface in org.springframework.http.converter") to resolve the method argument depending on the content type of the request.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestBody.html)

  

  

@interface **RequestParam**

Annotation which indicates that a method parameter should be bound to a web request parameter.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestParam.html)

  

  

@interface **PathVariable**

Annotation which indicates that a method parameter should be bound to a URI template variable.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/PathVariable.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/PathVariable.html)

Domain

Spring MVC

Question 46Incorrect

How many profiles can be active simultaneously in Spring?

Your answer is incorrect

1

One for dev and one for prod

Correct answer

Unlimited

The same as the number of contexts

Overall explanation

In Spring, there is no specific limit on the maximum number of profiles that can be active at the same time. Multiple profiles can be activated simultaneously in different ways, such as through command-line arguments, system properties, or environment variables.

  

By default, Spring comes with two profiles, i.e., "default" and "production". However, **additional profiles can be created and activated** based on different conditions or requirements. For example, profiles can be created based on environment, deployment location, or application version.

  

It's important to note that multiple active profiles can cause complexity and conflicts in the configuration. Therefore, it's recommended to use profiles judiciously and keep the configuration as simple and manageable as possible.

  

**Javadoc:**

public @interface **Profile**

Indicates that a component is eligible for registration when one or more [specified profiles](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Profile.html#value()) are active.

A _profile_ is a named logical grouping that may be activated programmatically via [`ConfigurableEnvironment.setActiveProfiles(java.lang.String...)`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/env/ConfigurableEnvironment.html#setActiveProfiles(java.lang.String...)) or declaratively by setting the [`spring.profiles.active`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/env/AbstractEnvironment.html#ACTIVE_PROFILES_PROPERTY_NAME) property as a JVM system property, as an environment variable, or as a Servlet context parameter in `web.xml` for web applications. Profiles may also be activated declaratively in integration tests via the `@ActiveProfiles` annotation.

The `@Profile` annotation may be used in any of the following ways:

- as a type-level annotation on any class directly or indirectly annotated with `@Component`, including [`@Configuration`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Configuration.html "annotation interface in org.springframework.context.annotation") classes
    
- as a meta-annotation, for the purpose of composing custom stereotype annotations
    
- as a method-level annotation on any [`@Bean`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Bean.html "annotation interface in org.springframework.context.annotation") method
    

If a `@Configuration` class is marked with `@Profile`, all of the `@Bean` methods and [`@Import`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Import.html "annotation interface in org.springframework.context.annotation") annotations associated with that class will be bypassed unless one or more of the specified profiles are active. A profile string may contain a simple profile name (for example `"p1"`) or a profile expression. A profile expression allows for more complicated profile logic to be expressed, for example `"p1 & p2"`. See [`Profiles.of(String...)`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/env/Profiles.html#of(java.lang.String...)) for more details about supported formats.

This is analogous to the behavior in Spring XML: if the `profile` attribute of the `beans` element is supplied e.g., `<beans profile="p1,p2">`, the `beans` element will not be parsed unless at least profile 'p1' or 'p2' has been activated. Likewise, if a `@Component` or `@Configuration` class is marked with `@Profile({"p1", "p2"})`, that class will not be registered or processed unless at least profile 'p1' or 'p2' has been activated.

If a given profile is prefixed with the NOT operator (`!`), the annotated component will be registered if the profile is _not_ active — for example, given `@Profile({"p1", "!p2"})`, registration will occur if profile 'p1' is active or if profile 'p2' is _not_ active.

If the `@Profile` annotation is omitted, registration will occur regardless of which (if any) profiles are active.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Profile.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Profile.html)

Domain

Spring core

Question 47Incorrect

What are the possible methods to define metadata for Spring Beans? (select 3)

Your selection is correct

XML files

Correct selection

Java-based configuration.

YAML Files

Your selection is correct

Java annotations

Overall explanation

In Spring, bean metadata refers to the configuration information of a bean that is used by the container to manage the bean's lifecycle, dependencies, and other settings. It includes information such as the bean's class, scope, initialization, and destruction methods, and dependency injection requirements. Bean metadata can be defined using various methods such as XML configuration files, Java annotations, and Java code.

  

[https://www.tutorialspoint.com/spring/spring_bean_definition.htm](https://www.tutorialspoint.com/spring/spring_bean_definition.htm)

Domain

Spring core

Question 48Incorrect

Which one is **NOT** a callback interface that works with JdbcTemplate?

Correct answer

ResultSetMapper

RowCallbackHandler

RowMapper

Your answer is incorrect

ResultSetExtractor

Overall explanation

The correct answer to the question is:

``ResultSetMapper`` is not a callback interface that works with `JdbcTemplate`.

While:

``RowCallbackHandler``, ``ResultSetExtractor``, and ``RowMapper`` are callback interfaces that work with ``JdbcTemplate`` in Spring Framework.

Here's a brief explanation of the other callback interfaces:

  

1. ``RowCallbackHandler``: This interface is used to process each row of the result set returned by a query.

It is used when you want to perform some custom processing for each row but don't need to return a result object.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/RowCallbackHandler.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/RowCallbackHandler.html)

  

2. ``ResultSetExtractor``: This interface is used to extract a result object from a ResultSet.

It is typically used when you want to return a single result object (e.g., a domain object) from a query.

Best choice when multiple rows of a ResultSet map to a single object.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/ResultSetExtractor.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/ResultSetExtractor.html)

  

3. ``RowMapper``: This interface is used to map a row of the ResultSet to an object.

It's commonly used when you want to map each row of the result set to a separate object, such as when executing a query that returns a list of objects.

Best choice when each row of a ResultSet maps to a domain object.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/RowMapper.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/RowMapper.html)

  

These callback interfaces provide flexibility and control when working with the `JdbcTemplate` in Spring by allowing you to customize the processing of query results.

Domain

Data Management

Question 49Incorrect

Which is true about Spring `RestTemplate`?

It is deprecated

It is reactive

Correct answer

It won't evolve in the future

Your answer is incorrect

It is non-blocking

Overall explanation

Answer:  It won't evolve in the future

  

**1. It is not reactive:**

Spring RestTemplate is not a reactive framework.

It is a synchronous HTTP client for making HTTP requests and receiving responses.

If you need to work with reactive programming, you should consider using Spring WebFlux and WebClient.

  

**2. It is blocking:**

RestTemplate operates in a blocking manner, which means when you make a request using RestTemplate, it will block the current thread until it receives a response.

This contrasts reactive frameworks like Spring WebFlux, which offer non-blocking alternatives.

  

**3. It won't evolve in the future:**

The Spring ecosystem is continuously evolving, and while RestTemplate was widely used in the past for making HTTP requests,

Spring has been encouraging WebClient (a part of Spring WebFlux) to make HTTP requests in modern applications.

RestTemplate may not receive as much attention and improvement in future Spring releases as WebClient.

  

**4. Not Deprecated:**

Still, in Spring 6.0.11, RestTemplate was in maintenance mode but not deprecated, and developers were encouraged to use WebClient for new projects.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/client/RestTemplate.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/client/RestTemplate.html)

  

Check also the next step for RestTemplate: RestClient ([https://youtu.be/1VhH3GNAM1k](https://youtu.be/1VhH3GNAM1k))

Domain

Spring MVC

Question 50Incorrect

**How to activate a Spring profile in production?** (select 2)

Your selection is correct

pass this system property: '`-Dspring.profiles.active=embedded,jpa`'

Your selection is incorrect

use `@ActiveProfiles`

Correct selection

do  '`System.setProperty("spring.profiles.active", "embedded,jpa");`' before creating the application context

do  '`System.setProperty("spring.profiles.active", "embedded,jpa");`' after creating the application context

Overall explanation

Ways to Activate Profiles

* Profiles must be activated at runtime:

    - System property via command line:

           `-Dspring.profiles.active=embedded,jpa`

    - System property programmatically

1.             System.setProperty("spring.profiles.active", "embedded,jpa");
2.             SpringApplication.run(AppConfig.class);

    - Integration Test only: `@ActiveProfiles`

  

**How can we activate a profile?**

We have to do it at runtime.

One way to do it is by using a system property.

We could pass this `-Dspring.profile.active` and pass one or more than one profile.

In that case, we are activating the `embedded` and `jpa` profile.

  

If you want to do it programmatically, you'll have to do it **before** creating the application context.

That's before calling the spring application run method, we set the `profile spring.profiles.active`.

We define the profiles we want to activate and then we start the application context.

  

Another way to activate a profile, that's going to be **valid for the test environment** is by using the `@ActiveProfiles`.

**So this cannot be used in production for instance.**

This is only used in a test environment, in a JUnit test for instance where we want to create the application context.

We'll focus on this annotation in a later module, but don't get confused: this is not an annotation to activate a profile in your application.

It is just for the test environment.

Domain

Spring core

Question 51Correct

Which testing web environment modes make the embedded server get started? (select 2)

Your selection is correct

`RANDOM_PORT`

`NONE`

`MOCK`

Your selection is correct

`DEFINED_PORT`

Overall explanation

**The embedded server gets started by the testing framework when** `**RANDOM_PORT**`**,** `**DEFINED_PORT**` **are used.**

  

When working with a web application in Spring Boot, it's important to note that it typically comes with an embedded servlet container, which is Tomcat by default.

  

However, when it comes to your testing environment, you have some choices to make regarding Tomcat's behavior.

This is where the concept of the 'web environment' comes into play.

  

You can specify whether you want a web environment, and if so, whether you want to 'mock' it.

When you choose to mock the web environment, Tomcat won't actually start, but you'll still have the ability to access web components for testing purposes.

  

Alternatively, you can decide not to use a web environment at all.

If you do want Tomcat to start, you can further specify whether it should start on a randomly assigned port that won't conflict with any other ports in use on your local machine, or on a specific port that you define.

  

Java Doc:

`DEFINED_PORT`

Creates a (reactive) web application context without defining any server.port=0 Environment property.

`MOCK`

Creates a WebApplicationContext with a mock servlet environment if servlet APIs are on the classpath, a ReactiveWebApplicationContext if Spring WebFlux is on the classpath, or a regular ApplicationContext otherwise.

`NONE`

Creates an ApplicationContext and sets SpringApplication.setWebApplicationType(WebApplicationType) to WebApplicationType.NONE.

`RANDOM_PORT`

Creates a web application context (reactive or servlet-based) and sets a server.port=0 Environment property (which usually triggers listening on a random port).

[https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/context/SpringBootTest.WebEnvironment.html](https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/context/SpringBootTest.WebEnvironment.html)

Domain

Testing

Question 52Incorrect

What is the propagation behavior of the `Propagation.REQUIRES_NEW` annotation in Spring?

Correct answer

The `Propagation.REQUIRES_NEW` annotation creates a new transaction if one already exists. If a transaction is already in progress, it is suspended until the new transaction is completed.

`Propagation.REQUIRES_NEW` suspends the current transaction and continues with the new transaction without committing the changes made to the previous transaction.

Your answer is incorrect

`Propagation.REQUIRES_NEW` prevents the current transaction from being committed until the new transaction has been completed.

`Propagation.REQUIRES_NEW` commits the current transaction and creates a new transaction to continue with the next operation.

Overall explanation

From Spring Javadoc: h[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/transaction/annotation/Propagation.html#REQUIRES_NEW](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/transaction/annotation/Propagation.html#REQUIRES_NEW)

  

- REQUIRES_NEW
    
    public static final [Propagation](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/transaction/annotation/Propagation.html "enum class in org.springframework.transaction.annotation") REQUIRES_NEW
    
    Create a new transaction, and suspend the current transaction if one exists. Analogous to the EJB transaction attribute of the same name.
    
    **NOTE:** Actual transaction suspension will not work out-of-the-box on all transaction managers. This in particular applies to [`JtaTransactionManager`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/transaction/jta/JtaTransactionManager.html "class in org.springframework.transaction.jta"), which requires the `jakarta.transaction.TransactionManager` to be made available to it (which is server-specific in standard Jakarta EE).
    
    **See Also:**
    
    - [`JtaTransactionManager.setTransactionManager(jakarta.transaction.TransactionManager)`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/transaction/jta/JtaTransactionManager.html#setTransactionManager(jakarta.transaction.TransactionManager))
        

Domain

Data Management

Question 53Correct

How can you use the @Lazy annotation in Spring to control bean instantiation? (select 2)

Your selection is correct

On a bean method declaration to make only that method lazy.

Your selection is correct

On a bean class declaration to make all bean methods lazy.

In the application.properties file.

On the CommandLineRunner.run() method.

Overall explanation

The `**@Lazy**` annotation can be placed on a Spring bean declaration to indicate that the bean should be instantiated lazily, i.e., only when it is actually needed. The following are valid options to place the `**@Lazy**` annotation:

  

1. On a bean declaration at the class level, before the `**@Component**` or `**@Service**` annotation, for example: `**@Component @Lazy**`.
    
2. On a constructor parameter in a `**@Bean**` method, for example: `**@Bean @Lazy public MyBean myBean(MyDependency myDependency)**`.
    
3. On a `**@Configuration**` class level, indicating that all beans declared in the class should be lazily initialized, for example: `**@Configuration @Lazy**`.
    

  

**Javadoc:**

Indicates whether a bean is to be lazily initialized.

May be used on any class directly or indirectly annotated with [`@Component`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/stereotype/Component.html "annotation interface in org.springframework.stereotype") or on methods annotated with [`@Bean`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Bean.html "annotation interface in org.springframework.context.annotation").

If this annotation is not present on a `@Component` or `@Bean` definition, eager initialization will occur. If present and set to `true`, the `@Bean` or `@Component` will not be initialized until referenced by another bean or explicitly retrieved from the enclosing [`BeanFactory`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/beans/factory/BeanFactory.html "interface in org.springframework.beans.factory"). If present and set to `false`, the bean will be instantiated on startup by bean factories that perform eager initialization of singletons.

If Lazy is present on a [`@Configuration`](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Configuration.html "annotation interface in org.springframework.context.annotation") class, this indicates that all `@Bean` methods within that `@Configuration` should be lazily initialized. If `@Lazy` is present and `false` on a `@Bean` method within a `@Lazy`-annotated `@Configuration` class, this indicates overriding the 'default lazy' behavior and that the bean should be eagerly initialized.

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Lazy.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/context/annotation/Lazy.html)

  

See also:

[https://www.baeldung.com/spring-lazy-annotation](https://www.baeldung.com/spring-lazy-annotation)

Domain

Spring core

Question 54Correct

Which method in JdbcTemplate is suitable for read-only operations?

execute()

batchUpdate()

update()

Your answer is correct

query()

Overall explanation

In JdbcTemplate, the `**query**` methods (such as `**query**`, `**queryForObject**`, `**queryForList**`) are recommended for read-only operations. These methods do not modify the data source and return a list or single object based on the query. The `**update**` methods (such as `**update**`, `**batchUpdate**`) are suitable for modifying the data source. The `**execute**` method is for executing any SQL statement. It is recommended to use the appropriate method based on the type of operation you want to perform to ensure that the data source is not accidentally modified.

Domain

Data Management

Question 55Correct

_____ is a convenience annotation that is itself annotated with `@Controller` and `@ResponseBody`.

@ControllerBody

Your answer is correct

@RestController

@ResponseBodyController

@RestControllerBody

Overall explanation

The `**@RestController**` annotation is a convenience annotation in Spring that combines the functionality of `**@Controller**` and `**@ResponseBody**`. It is used to mark a class as a controller that handles RESTful web requests.

  

When a class is annotated with `**@RestController**`, Spring considers it as a RESTful web service and automatically serializes any method return values to JSON/XML responses. Therefore, there is no need to annotate each method with `**@ResponseBody**`.

  

In addition, `**@RestController**` can also handle other HTTP request methods besides GET and POST, which is a limitation of `**@Controller**`. Overall, `**@RestController**` simplifies the process of developing RESTful web services in Spring.

  

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RestController.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RestController.html)

Domain

Spring MVC

Question 56Incorrect

What features are included in Spring Boot's Spring MVC Auto-configuration? (select 2)

Your selection is correct

HttpMessageConverters support

automatic configuration for database connection

Correct selection

support for serving static resources

Your selection is incorrect

built-in web server

Overall explanation

Spring Boot's Spring MVC auto-configuration provides the following features:

- HttpMessageConverters support
    
- Content Negotiating View Resolver bean
    
- Support for serving static resources
    
- RestController testing pages
    

These features help developers quickly set up a Spring MVC application with sensible defaults and reduce the amount of boilerplate code needed to configure the application.

  

**Springdoc:  
**Spring Boot provides auto-configuration for Spring MVC which works well with most applications.

The auto-configuration adds the following features on top of Spring’s defaults:

- Inclusion of `ContentNegotiatingViewResolver` and `BeanNameViewResolver` beans.
    
- **Support for serving static resources, including support for WebJars** (covered [later in this document](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-static-content "28.1.5 Static Content"))).
    
- Automatic registration of `Converter`, `GenericConverter`, and `Formatter` beans.
    
- **Support for** `HttpMessageConverters` (covered [later in this document](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-message-converters "28.1.2 HttpMessageConverters")).
    
- Automatic registration of `MessageCodesResolver` (covered [later in this document](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-message-codes "28.1.4 MessageCodesResolver")).
    
- Static `index.html` support.
    
- Custom `Favicon` support (covered [later in this document](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-favicon "28.1.7 Custom Favicon")).
    
- Automatic use of a `ConfigurableWebBindingInitializer` bean (covered [later in this document](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-web-binding-initializer "28.1.9 ConfigurableWebBindingInitializer")).
    

If you want to keep Spring Boot MVC features and you want to add additional [MVC configuration](https://docs.spring.io/spring/docs/5.0.13.RELEASE/spring-framework-reference/web.html#mvc) (interceptors, formatters, view controllers, and other features), you can add your own `@Configuration` class of type `WebMvcConfigurer` but **without** `@EnableWebMvc`. If you wish to provide custom instances of `RequestMappingHandlerMapping`, `RequestMappingHandlerAdapter`, or `ExceptionHandlerExceptionResolver`, you can declare a `WebMvcRegistrationsAdapter` instance to provide such components.

If you want to take complete control of Spring MVC, you can add your own `@Configuration` annotated with `@EnableWebMvc`.

[https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-auto-configuration](https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-developing-web-applications.html#boot-features-spring-mvc-auto-configuration)

Domain

Spring core

Question 57Incorrect

Which is **NOT**  a valid way to activate the profiles: '`cloud`', and '`jpa`'?

Correct answer

Using '`web.xml`' 'spring-profiles' tag:

1. <spring-profiles>
2.     <active>cloud</active>
3.     <active>jpa</active>
4. <spring-profiles>

Your answer is incorrect

Using a system property programmatically:

1. System.setProperty("spring.profiles.active", "cloud,jpa");
2. SpringApplication.run(MyConfig.class); 

Using a system property via command-line:

`-Dspring.profiles.active=cloud,jpa`

Using `@ActiveProfiles` annotation (in integration tests only)

Overall explanation

1) We can use:

JVM System Parameter

The profile names can also be passed in via a JVM system parameter. These profiles will be activated during application startup:

`-Dspring.profiles.active=dev`

  

2) We can set the system property:

1. System.setProperty("spring.profiles.active", "cloud,jpa");
2. SpringApplication.run(MyConfig.class);

  

3) We can use:

`@ActiveProfiles` in Tests

Tests make it very easy to specify what profiles are active using the @ActiveProfile annotation to enable specific profiles:

  

`@ActiveProfiles("dev")`

So far, we've looked at multiple ways of activating profiles. Let's now see which one has priority over the other and what happens if we use more than one, from highest to lowest priority:

1. Context parameter in web.xml
    
2. WebApplicationInitializer
    
3. JVM System parameter
    
4. Environment variable
    
5. Maven profile
    

  

4) We can use:

Similarly, we can define the active profiles in the web.xml file of the web application using a context parameter:

1. <context-param>
2.      <param-name>contextConfigLocation</param-name>
3.      <param-value>/WEB-INF/app-config.xml</param-value>
4. </context-param>
5. <context-param>
6.      <param-name>spring.profiles.active</param-name>
7.      <param-value>cloud,jpa</param-value>
8. </context-param>

**but** `**<spring-profiles>**` **element does not exist in the web.xml file.**

  

[https://www.baeldung.com/spring-profiles](https://www.baeldung.com/spring-profiles)  

Domain

Spring core

Question 58Correct

Which classes' methods are intercepted by the pointcut expression "within(com.xyz.example..*)" in Spring AOP? (select 3)

Your selection is correct

com.xyz.example.rest.controller.DummyController

Your selection is correct

com.xyz.example.service.DummyService

Your selection is correct

com.xyz.example.DummyApplication

com.xyz.util.DummyUtils

Overall explanation

**Spring Doc:**

**Combining pointcut expressions**

Pointcut expressions can be combined using '&&', '||' and '!'. It is also possible to refer to pointcut expressions by name. The following example shows three pointcut expressions: anyPublicOperation (which matches if a method execution join point represents the execution of any public method); inTrading (which matches if a method execution is in the trading module), and tradingOperation (which matches if a method execution represents any public method in the trading module).

1.     @Pointcut("execution(public * *(..))")
2.     private void anyPublicOperation() {}

4.     @Pointcut("within(com.xyz.someapp.trading..*")
5.     private void inTrading() {}

7.     @Pointcut("anyPublicOperation() && inTrading()")
8.     private void tradingOperation() {}

It is a best practice to build more complex pointcut expressions out of smaller named components as shown above. When referring to pointcuts by name, normal Java visibility rules apply (you can see private pointcuts in the same type, protected pointcuts in the hierarchy, public pointcuts anywhere and so on). Visibility does not affect pointcut _matching_.

[https://docs.spring.io/spring-framework/docs/2.0.x/reference/aop.html#aop-pointcuts-combining](https://docs.spring.io/spring-framework/docs/2.0.x/reference/aop.html#aop-pointcuts-combining)

  

See also:  
[https://www.baeldung.com/spring-aop-pointcut-tutorial](https://www.baeldung.com/spring-aop-pointcut-tutorial)

Domain

Spring AOP

Question 59Correct

A _______ is **a sequence of actions that are treated as a single unit of work**. These actions should either be completed entirely or take no effect at all.

Reconciliation

Callback

Your answer is correct

Transaction

Dispatch

Overall explanation

A **transaction** is a sequence of actions that are treated as a single unit of work. These actions should either be completed entirely or take no effect at all.

  

More:

[https://docs.spring.io/spring-framework/docs/4.2.x/spring-framework-reference/html/transaction.html](https://docs.spring.io/spring-framework/docs/4.2.x/spring-framework-reference/html/transaction.html)

Domain

Data Management

Question 60Correct

______ is an annotation that indicates that a method parameter should be bound to a URI template variable

`@RequestParam`

`@RequestHeader`

`@RequestMapping`

Your answer is correct

`@PathVariable`

Overall explanation

The `**@PathVariable**` annotation is used in Spring to map parts of a request URL to handler method arguments. When a request is made to a Spring MVC application, the `**@PathVariable**` annotation can be used to capture a specific part of the URL and use it as an input parameter to a controller method.

  

For example, if the URL `**/products/123**` is requested, where `**123**` is the id of a product, the `**@PathVariable**` annotation can be used to capture this value and pass it as a parameter to a controller method. The syntax for using `**@PathVariable**` is as follows:

1. @GetMapping("/products/{id}")
2. public String getProductById(@PathVariable Long id) {
3.     // method logic
4. }

This allows the controller method to retrieve the product with the given `**id**` and perform the necessary logic on it. The `**@PathVariable**` annotation can also be used with regular expressions to further specify the format of the captured value.

  

[https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/PathVariable.html](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/PathVariable.html)

  

**Bad answers**

1. @RequestParam:
    

The @RequestParam annotation in Spring is used to extract query parameters or form data from the incoming HTTP request. It binds the value of a request parameter to a method parameter in a controller. This annotation has a few optional attributes, such as "value", "required", and "defaultValue". The "value" attribute specifies the name of the request parameter to bind to, while the "required" attribute indicates whether the parameter is mandatory or not. The "defaultValue" attribute sets a default value for the parameter if it is not present in the request.

Example usage:

1. @RequestMapping("/user")
2. public String getUserById(@RequestParam("id") int id) {
3.     // method body
4. }

1. @RequestMapping:
    

The @RequestMapping annotation is used to map HTTP requests to a specific controller method. It can be applied at both the class level and the method level. This annotation has a wide range of attributes, such as "value", "method", "headers", "params", and more, to define the various conditions under which the method will be executed.

Example usage:

1. @Controller
2. @RequestMapping("/user")
3. public class UserController {

5.     @RequestMapping(method = RequestMethod.GET, path = "/{id}")
6.     public ResponseEntity<User> getUserById(@PathVariable("id") Long id) {
7.         // method body
8.     }
9. }

1. @RequestHeader:
    

The @RequestHeader annotation is used to extract values from HTTP request headers. It binds the value of a request header to a method parameter in a controller. This annotation also has a few optional attributes, such as "value", "required", and "defaultValue". The "value" attribute specifies the name of the request header to bind to, while the "required" attribute indicates whether the header is mandatory or not. The "defaultValue" attribute sets a default value for the header if it is not present in the request.

Example usage:

1. @RequestMapping("/user")
2. public String getUserByEmail(@RequestHeader("X-User-Email") String email) {
3.     // method body
4. }





Baeldung 👉 https://www.baeldung.com/spring-postconstruct-predestroy