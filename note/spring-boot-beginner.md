## 1, install idea 

## 2, new `maven` project

## 3, create package by your self.

## 4, pom.xml add spring boot.

### spring framework boot Parent.
version you can find it from `https://search.maven.org/`
```
<parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.6.0</version>
</parent>
```

### spring boot lib the project dependency

```
<dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>
```
Same group use the same version. The `scope` indicate this lib only for `test`.

### donwload and import `maven` lib.


but may be you can't donwload the spring framework since it also need to configure the `Repository`.
```
<pluginRepositories>
        <pluginRepository>
            <id>repository.spring.release</id>
            <name>Spring GA Repository</name>
            <url>https://repo.spring.io/plugins-release/</url>
        </pluginRepository>
    </pluginRepositories>
```
## 5, run or debug this project.

### add a `Application` for this spring boot project. you should create a java class with a annotation `@SpringBootApplication`. ex:

```
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class App {
    public static void main(String[] args) {
        SpringApplication.run(App.class, args);
    }
}

```

This class will import the package automatic, but you also can add it by manual.


### add a `Controller` for `Bean`. ex:

```
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class TestService1Controller {
    @RequestMapping(path = "/index")
    @ResponseBody
    public String index() {
        return "test";
    }

    @RequestMapping(path = "/")
    @ResponseBody
    public String root() {
        return "hello.";
    }
}
```

## 6, run or debug this project.

You `MUST` set the configuration with this project. 
so just add a `application`.

In fact, if the `spring boot` framework download and import success, seems it add a `sprint boot` configuration automatic. anyway, you can run it now.

The default `spring server` will listen on port `8080`, you can access you web sit by `127.0.0.1:8080/`.


## 7, package your project.
If your project running no problem, may be you want to deploy it.
I use the `maven` window to package it, there have so many method to package it, you can find it in network.

### 1 click the `maven` window.
### 2 right clikc `pakcage`
### 3 `compile`.

you can find your package in your poject `target` directory. find it. run it.
` java -jar .war`.

if you just find a `jar` not a `war` package, you should configure your `pom.xml` in your project. ex:
```
<packaging>war</packaging>
```

After that, please re-try complile.

There has a bad news that you may be get a error `no main manifest attribute`. you should configure `build plugin` in `pom.xml`...

```
<build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>${project.parent.version}</version>
            </plugin>
        </plugins>
    </build>
```

and then, just do it again.

it is not easy to run a `spring boot` project for a beginer.. 


- [no mian manifest attribute](https://segmentfault.com/a/1190000022101280)

