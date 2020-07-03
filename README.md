<p  align="center"><img src="logo.png" width="100"></p>
<h1 align="center">Cappuccino</h1>

<h4 align="center"><i>A mostly reasonable approach and non-boring guide for Junior Developers to write professional Oriented-Object code.</i></h4>

<hr>

<h6 align="center"><a href="https://github.com/MenaiAla/Cappuccino/pulls">Contribute</a>&nbsp &nbsp|&nbsp &nbsp <a  href="https://twitter.com/intent/tweet?text=Cappuccino%20is%20out.A%20mostly%20reasonable%20approach%20and %20non-boring%20guide%20for%20Junior%20Developers%20to%20write%20professional%20Oriented-Object%20code.">Tweet</a>&nbsp &nbsp|&nbsp &nbsp<a href="https://spectrum.chat/users/menai-ala-eddine">Chat</a></h6>

<hr>

> **Note**: This guide is inspired by Robert C. Martin's Book **Clean Code**, **Google Java Style Guide**, **Ali-baba Guide**, **Oracle Guide**, **hundreds of online blogs** and **our experience** with a simple and easy-to-learn style powered by **examples**.
> We try to reduce blah-blah and provide useful examples that cover all cases.

<hr>

In the old days, [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) said:

> _Talking is shit, show me the code._

In 2020 we say:

> _Code that works is shit, show us the tests._

<a  href="https://twitter.com/intent/tweet?text=Code20%that20%works20%is20%shit,20%show20%us20%the20% tests.">Tweet</a>

M. Ala Eddine says:

> _Yesterday, I was writing code for machines. Today, I'm trying to write code for everyone._

<a  href="https://twitter.com/intent/tweet?text=Yesterday,20%I20%was20%writing20%code20%for20%machines.20%Today, 20%I'm20%trying20%to20%write20%code20%for20%everyone.">Tweet</a>

<h2 style="font-size:24px;font-weight:bold">Why Cappuccino?</h2>

1. 99% of junior developers <u> **have no-time**</u> to read books that have <u> **400 or 500 pages**</u>.

2) Most of guidelines are <u>**static**</u> and <u> **bored**</u> with <u> **journal-like** </u> style.

3) Junior developers struggle to find <u>**easy-to-learn** </u> best practices and guidelines to improve their <u> **skills** </u> in <u> **short-time** </u>.

4) Junior developers want to write <u>**code that works**</u>, not a solid code that follows <u>**standard convention**</u>, pass all <u>**test cases**</u>, and can be <u>**scalable any time**</u>.

<h2 style="font-size:24px;font-weight:bold">Features & Benefits</h2>

- Built particularly for **junior developers** and also for all developers.

- **Ease to read**, **simple** explanations and **rich** with examples.

- Able to write **quality code** in the future.

- Avoid your current repetitive **errors**.

- **Updates** and new **features** each week.

<h2 style="font-size:24px;font-weight:bold">Who read this guide</h2>

**[Menai Ala Eddine](https://github.com/MenaiAla)**

> Though I'm the writer I enjoyed it as a reader.

<h2 style="font-size:24px;font-weight:bold">Table of content</h2>

1. ### [Meaningfull Names](#Meaningful-Names)

2. ### [Functions](#Functions)

3. ### [Formatting](#Formatting)

4. ### [Comments](#Comments)

5. ### [Objects and Data Structures](#Objects-and-Data-Structures)

6. ### [Error Handling](#Error-Handling)

7. ### [Classes](#Classes)

8. ### [Kent Beck’s Four Rules Of Simple Design](#Kent-Beck’s-Four-Rules-Of-Simple-Design)

9. ### [Smells and Heuristics](#Smells-and-Heuristics)

10. ### [In The Next Week](#In-The-Next-Week)

11. ### [Contributors](#Contributors)

12. ### [Chat With Us](#Chat-With-Us)

## [Meaningfull Names](#Meaningfull-Names)

Programming is about names and names are everywhere, we name our variables, functions, classes, and packages. Indeed, our code contains only names.

<h2 style="font-size:20px;font-weight:bold">Rules For Naming</h2>

<h2 style="font-size:17px;font-weight:bold">Package Names</h2>

Package names are all lowercase.

```java
// bad
import com.app.Users.Data
```

```java
// good
import com.app.users.data
```

<h2 style="font-size:17px;font-weight:bold">Class Names</h2>

Class names are written in UpperCamelCase except for domain models such as DO, BO, DTO, DAO, VO, and so on.

```java
// bad
public class user {..}
```

```java
// good
public class User {..}
```

```java
// bad
public class userDao {..}
```

```java
// good
public class UserDAO {..}
```

> > DAO refers to Data Access Object. We use this kind of class in the database layer in case of ORM persistence.

```java
// bad
public class HTMLPage {..}
```

```java
// good
public class HtmlPage {..}
```

```java
// bad
public class PrOgRaMMiNg {..}
```

```java
// good
public class Programming {..}
```

```java
// bad
public class CompanyOfFacebook {..}
```

```java
// good
public class FacebookCompany {..}
```

```java
// bad
public class AddingCoffeeInMilk {..}
```

```java
// good
public class CoffeeInMilk {..}
```

Also, you should know :

- Abstract class names must start with `Abstract` or `Base`.

- Pattern class names must end with The name of that `Pattern`.

- A class names that implement an interface must end with `Impl`.

* A class Enum must end with `Enum`.

* Exception class names must end with `Exception`.

* Test case names shall start with the class names to be tested and end with `Test`.

```java
// bad
public abstract class User {..}
```

```java
// good
public abstract class AbstractUser {..}
```

```java
// good
public abstract class BaseUser {..}
```

```java
// bad
public class User {..}
```

> > We assume this `class` implement `Factory` Pattern.

```java
// good
public class UserFactory {..}
```

```java
// bad
public class Profile implements IProfile {..}
```

```java
// good
public class ProfileImpl implements IProfile {..}
```

```java
// bad
public enum UserStatus {..}
```

```java
// good
public enum UserStatusEnum {..}
```

```java
// bad
public class HackedUser {..}
```

> > We assume this `class` is reserved for an `Exception`.

```java
// good
public class HackedUserException {..}
```

```java
// bad
public class UTest {..}
```

> > We assume this `class` is reserved for `Testing`.

```java
// good
public class UserTest {..}
```

<h2 style="font-size:17px;font-weight:bold">Method Names</h2>

Method names are written in lowercase.

```java
// bad
public void ConnectNetwork () {..}
```

```java
// bad
public void CONNECTNETWORK () {..}
```

```java
// bad
public void connect_network () {..}
```

```java
// good
public void connectNetwork () {..}
```

<h2 style="font-size:17px;font-weight:bold">Constants Names</h2>

Constant names use CONSTANT_CASE: all uppercase letters, with each word separated from the next by a single underscore. But what is a constant, exactly?

Constants are `static final` fields whose contents are deeply immutable and whose methods have no detectable side effects. This includes **primitives**, **Strings**, **immutable types**, and **immutable collections** of immutable types. If any of the instance's observable state can change, it is not a constant.

Unfortunately, we still see developers who define their constants like this :

```java
// very bad
public static final int pi = 3.14;
```

```java
// bad
static final ImmutableMap <String, Integer> facebookFounders = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);
```

```java
// good
static final ImmutableMap <String, Integer> FACEBOOK_FOUNDERS = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);
```

```java
// bad
static  ImmutableMap <String, Integer> GOOGLE_FOUNDERS = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);
```

> > Because it's not a `constant`. We removed `final`
> > keyword.

```java
// good
static  ImmutableMap<String, Integer> googleFounders = ImmutableMap.of("Lary Page", 58, "Sergey Bring", 52);
```

<h2 style="font-size:17px;font-weight:bold">Parameters Names</h2>

Parameters' names are written in lowercase.

```java
// bad
public void area (int Width, int Height) {..}
```

```java
// good
public void area (int width, int height) {..}
```

<h2 style="font-size:20px;font-weight:bold">Use Intention-Revealing Names</h2>

Choosing a convention and good names may take time but saves more then it takes. So take your names Seriously and let your code talking about itself not by providing additional useless comments.

```java
// very bad
int d; // daily active users
```

> > Without comment we can guess it `day`.

```java
// bad
int dau; // daily active users
```

```java
// good
int activeUsers; // daily active users
```

> > Without comment we can guess it `monthlyActiveUsers`.

```java
// super
int dailyActiveUsers;
```

```java
// bad
public List<User> getAll () {..} // get list of users
```

> > We know this method gets all users but what kind of users ? `online users`, `offline users`? Furthermore, if someone invokes this method how does he know that it returns `List`, `Map` or `Set`?

```java
// good
public List<User> getUsers () {..}
```

```java
// super
public List<User> getUsersList () {..}
```

```java
// fantastic
public List<User> getAllUsersList () {..}
```

<h2 style="font-size:20px;font-weight:bold">Avoid Disinformation & Abbreviation</h2>

You should write code for others not only for yourself!

```java
// bad
String os; // operating system name
```

> > Without comment we can guess it `Open Source`.

```java
// good
String operatingSystem;
```

> > But an operating system can have many properties.

```java
// super
String operatingSystemName;
```

<h2 style="font-size:17px;font-weight:bold">Don't use prefixes and PHP style</h2>

```java
// bad
String __Name;
int age_;
double $_amount;
```

```java
// bad
String LName;
int Age;
double __amount;
```

```java
// good
String name;
int age;
double amount;
```

<h2 style="font-size:17px;font-weight:bold">Make Meaningful Distinctions</h2>

Programmers create problems for themselves when they write code solely to satisfy a compiler or interpreter.

```java
// bad
public static void copyChars (char s[], char d[]) {..}
```

```java
// good
public static void copyChars (char src[], char dest[]) {..}
```

```java
// Super
public static boolean copyChars (char source[], char destination[]) {..}
```

> > > You may notice that we used `boolean` instead of `void`. This will help us to improve the developer experience and make the function more reusable and testable. Without `return` we could not know if the characters are copied properly or no.

<h2 style="font-size:17px;font-weight:bold">Use Pronounceable Names</h2>

Humans are good at words. A signiﬁcant part of our brains is dedicated to the concept of words. And words are, by deﬁnition, pronounceable.

```java
// bad
public static void genAuthPswrd () {..}
```

> > > You will be able to pronounce it only if you drink 10 cups of wine!

```java
// good
public static void generateAuthPassword () {..}
```

```java
// super
public static void generateAuthenticationPassword () {..}
```

<h2 style="font-size:17px;font-weight:bold">Use Searchable Words</h2>

I'm sure that most of us use direct numbers in check-in conditions.

```java
// bad
if (connectedUsers==100) {..}
```

> > Imagine that you've 50 `checks` like this , how many changes you will make?

```java
// good
public static final MAX_CONNECTION = 100;
if (connectedUsers==MAX_CONNECTION) {..}
```

<h2 style="font-size:17px;font-weight:bold">Avoid Encodings</h2>

In days of old, programmers were forced to add notations and suffixes and prefixes for variables, classes, and functions because the compiler did not check the types in those days.

Today, most programming languages are typed.

```java
// bad
String passwordString;
int maxConInteger;
User appUser;
```

```java
// good
String password;
int maxConnections;
User user;
User appUser;
```

> > Remember that using `String` for passwords is bad practice because `String` is immutable even if you encrypt it. Use `Char []` instead of it.

```java
// bad
public class CarFactory implements CarFactoryInterface {..}
```

```java
// good
public class CarFactoryImp implements ICarFactory {..}
```

<h2 style="font-size:17px;font-weight:bold">Avoid Mental Mapping</h2>

Not all readers are translators and they can understand what's in your mind. Don't try to be a smart programmer in your code, Be an explainer!

<h2 style="font-size:15px;font-weight:bold">Loops</h2>

Certainly, a loop counter may be named `i` or `j` or `k`.Those single-letter names for loop counters are traditional.

```java
// bad
for (i=0; i< onlineUsersList.length; i++) {
     int j = 0;
     while (j<10) {..}
}
```

```java
// good
for (index=0; index< onlineUsersList.length; index++) {
     int internalIndex = 0;
     while (internalIndex==0) {..}
}
```

<h2 style="font-size:15px;font-weight:bold">Class Names</h2>

Classes and objects should have noun or noun phrase names like `User`, `Page`, `Profile`. Avoid words like `Admin`, `Process`, `OS`, `Http`, or `Setup` in the name of a class.

- A class **name** should not be one letter `X`.
- A class **name** should not be a **verb**.
- A class **name** should not be a **part** of the name.
- A class **name** should not have contain **conjunctions** ( `And`, `Or` ) or **operations** ( `Plus`, `Minus`).
- A class **name** should be a **complete** and **comprehensive** name.

```java
// bad
public class OnOrOFF {..}
public class Work {..}
public class Addr {..}
```

```java
// good
public class LampState {..}
public class Activity {..}
public class Address {..}
```

<h2 style="font-size:15px;font-weight:bold">Method Names</h2>

Methods should have verb or verb phrase names like `addUser`, `deletePage` or `save`. Accessors, mutators, and predicates should be named for their value and preﬁxed with `get`, `set`, and `is`.

```java
// bad
String username = user.userName();

Puzzle initialPuzzle = new Puzzle (pieces)
```

```java
// good
String username = user.getName();

Puzzle randomPuzzle = PuzzleContext.initRandomPuzzle(pieces); // static factory
```

> > We use static factory methods with names to describe the returned `object` from that arguments. In logic, when you start a game you will have **only one** initiation or starting state.

<h2 style="font-size:17px;font-weight:bold">Don't Be Cute</h2>

Cuteness in code may work against you and your coding style. Or even your personality when a stranger read your code.

```java
// bad
public class Poppy {..}
public class Dude {..}
```

```java
// good
public class Cat {..}
public class Friend {..}
```

<h2 style="font-size:17px;font-weight:bold">Pick one word per concept</h2>

In other words, don't use the whole lexical champ in the same class. Imagine that you have `get` `find` `fetch` `retrieve` `search` or `set`, `assign` and `add`, and so on in the same class or script. Many developers make this mistake and you should avoid it by choosing **one word** for the **same action**.

```java
// bad
public class Book {
public Book getOneBook () {..}
public List<Book> findAllBooksList () {..}
public List <Book> fetchFavoriteBooks () {..}
}
```

```java
// good
public class Book {
public Book getOneBook () {..}
public List<Book> getAllBooksList () {..}
public List <Book> getFavoriteBooksList () {..}
}
```

> > As a standard we use `find` in database layer classes and `fetch` for async methods that are related to external APIs.

If you follow the **one word per concept** rule, you could end up with many classes that have, for example, an `add` method. As long as the parameter lists and return values of the various add methods are semantically equivalent, all is well. But sometimes, we will be enforced to break the concept to become more descriptive.

```java
// good
public class Sticker {
public boolean add () {..}
public boolean remove () {..}
}
```

```java
// super
public class Sticker {
public boolean pin () {..}
public boolean unpin () {..}
}
```

<h2 style="font-size:17px;font-weight:bold">Use Problem Domain Names</h2>

The question is why you're writing code?

Of course to solve a problem, but what it means **Problem Domain Names**?

Problem domain names are the lexical champ of words that we can use to describe our domain.
For example the domain of **Social Media** we can use these names and actions :

`User`, `Like`, `Comment`, `Share`

Could you tell us what `Oil` means in the Social Media domain?

<h2 style="font-size:17px;font-weight:bold">Use Solution Domain Names</h2>

Again? what does that mean?

It means that only programmers who will read your code, not History authors ! so don't fear to add names that refer to computer science terms, algorithm names, math names, and so on.

For example, we can add `Singleton`, `Factory`, `Context`, `Template`, `Thread` as extensions for special classes, but we must be aware before choosing the right name.

```java
// bad
public class ProfileVisitor {..}
```

> > What the word `Visitor` refers to? It refers to its real sense or it refers to `Visitor` Pattern?

```java
// good
public class ProfileSingleton {..}
```

> > We understand this `class` uses `Singleton` Pattern.

```java
// good
public class RocketThread extends Thread {..}
```

> > We understand this `class` extends `Thread`.

```java
// good
public class AlbumFactory {..}
```

> > We understand this `class` uses `Factory` Pattern.

<h2 style="font-size:17px;font-weight:bold">Provide Meaningful Context</h2>

Each variable has one context. Each function or method has one context. Each class has one context, not two or three.

```java
// bad
public class Computer {
  String v;
  String os;
}
```

> > What's `v` and `os` ?

```java
// good
public class Computer {
  String version;
  String operatingSystem;
}
```

```java
// super
public class Computer {
  String version;
  List<OperatingSystem> operatingSystems;
}


public class OperatingSystem {
String name;
String version;
Date distributionDate;
}
```

> > A computer can have more than one operating system. PCs can run both Windows and Linux.

```java
// bad
public class User {
  String firstName;
  String lastName;
  String street;
  String city;
  String zipCode;
  String state;
}
```

```java
// good
public class User {
  private FullName fullname;
  private Adress adress;
}

public class FullName {
  private String firstName;
  private String lastName;
}

public class Adress {
  private String street;
  private String city;
  private String zipCode;
  private String state;
}
```

> > You can use `FullName` class for other classes in the future for example: `Customer`,`Advertiser`. Also, each user may have more than one `address`

## [Functions](Functions)

The reason we write functions is to decompose a larger concept into small concepts.

<h2 style="font-size:17px;font-weight:bold">Use Descriptive Names</h2>

The name of the function should be a **verb** and describes what it does.
The function and argument should form a very nice verb/noun pair.

```java
// bad
public void txt2pdf () {..}
```

```java
// good
public void convertTxt2Pdf () {..}
```

```java
// good
public void convertTextToPdf () {..}
```

Uncle Bob said :

> Don’t be afraid to make a name long. A long descriptive name is better than a short enigmatic name. A long descriptive name is better than a long descriptive comment.

M. Ala Eddine says:

> Both **name** and **parameters** will tell me what your function does.

<a  href="https://twitter.com/intent/tweet?text=Both20%name20%and20%parameters20%will20%tell20%me20%what20%your 20%function20%does.">Tweet</a>

```java
// bad
// This function adds only one item
public void add (Item item) {..}
```

```java
// good
public void addOne (Item item) {..}
```

```java
// good
public void addSingle (Item item) {..}
```

```java
// super
public void insertOne (Item item) {..}
```

> > `add` is a generic word for a function that adds `items` into a `list` or `array`. We prefer `insert`.

<h2 style="font-size:17px;font-weight:bold">Small!</h2>

The ﬁrst rule of functions is that they should be small. The second rule of functions is that they should be smaller than that.

```java
// very bad
public void write () {
    // 10 blocks or 100 lines
}
```

> > You will spend a **month** to create a test that passes successfully.

```java
// bad
public void write () {
    // 4 blocks or 40 lines
}
```

> > You will spend a **week** to create a test that passes successfully.

```java
// good
public void write () {
    // 2 blocks or 10 lines
}
```

> > You will spend **10 minutes** to create a test that passes successfully.

```java
// good
public void write () {
// 1 block
}
```

```java
// fantastic
public void write () {
// one line
}
```

> > You will spend **2 minutes** to test this function.

<h2 style="font-size:15px;font-weight:bold">Blocks and Indenting</h2>

This implies that the blocks within `if` statements, `else` statements, `while` statements, and so on should be one line long.

```java
// bad
public void vote () {
    try {
    if (condition) {
     // 10 lines of code
      if(condition) {
        // 10 lines of code
        }
    }
    while (condition) {
    // more code
     }
    }
    }catch (Exception e) {..}
```

```java
// good
public void vote () {

    try {
    // do something
    } catch(e) {
    // handle exception
    }
}
```

```java
// super
public void vote () {
    try {
    // do something
    }catch (e) {
    // handle exception
    }
    }finally {
    // finalize with something
}
```

> > Most programmers miss `finally` block.

<h2 style="font-size:17px;font-weight:bold">Do one thing</h2>

The problem with this rule is how do I count one thing?

We prefer count **one thing** by **one block**.

```java
// bad
public void commit () {
    // first block
    if (condition) {
    // do X
    }
    // second block
    if (condition) {
    // do Y
    }
    // third block
    for (int index=0; index<list.length; index++) {
    // do Z
    }
}
```

```java
// good
public void commit () {
    // one block
    if (condition) {
    // do X
    }
    else (condition) {
    // do X1
    }
}
```

```java
// super
public void commit () {
    // one block
    if (condition) {
    // do X
    }
    // do X1
}
```

```java
// good
public void commit () {
    // one block
    for (int index=0; index<list.length; index++) {
    // do X
    }
}
```

```java
// good
public void commit () {
    // one block
    for (int index=0; index<list.length; index++) {
      if (condition) {
      // do thing
      }else {
        // do thing
      }
    }
}
```

It's not only you who have this problem, all of us we struggle to create functions that follow Single Responsibility Principale **SRP**. But, there's a _Quote_ that help us understand SRP rule :

> > Functions do one thing. They should do it well. They should do it only.

- If you can explain your function in **one short paragraph** without using **And** or **Or**, your function does one thing.

- If you can not extract your function into other functions, your function does one thing.

**How to create a function that sends an email ?**

To send an email, we check if there's an `available connection` **and** a `constructed email`.

> **Note**: You may notice **and** here but it refers that there are two tests in one level, not 2 things.

```java
// very bad
public void sendEmail (Email email) {
    // 10-20 lines of code that tests internet connection
    if (email!=null) {
      // do thing
     }else {
       // do other thing
     }
}
```

```java
// bad
public void sendEmail (Email email) {
    try {
      // 10-20 lines of code that tests internet
    connection

    if (email!=null) {
      // do thing
     }
    }catch (Exception e) {..}
}
```

```java
// good
public void sendEmail (Email email) {
    try {
       if (isConnected()) {
         if (email!=null) {
      // do thing
          }
        }
     }catch (Exception e) {..}
}
```

```java
// super
public boolean sendEmail (Email email) {
   try {
     if (isConnected()) {
     // sending email code-block
       }
     }catch (Exception e) {
        // handle error
        return false;
    }finally {
     // final action
     }
}
```

> > You may noticed that we removed `if (email!=null) {..}` because the test will be outside of the function.

<h2 style="font-size:17px;font-weight:bold">Reading Code From Top To Down</h2>

Nice code style is not the same as a well-organized code.

We can explain step-down rule through these actions:

- To drink milk we mix sugar first.

- To mix sugar we add sugar first.

- To add sugar .......

```java
// very bad

public boolean mixSugar () {
// Did we add sugar to mix it?
// Let's move next
// But we have drinkMilk!
}

public boolean drinkMilk () {
// Did we mix sugar to drink coffee?
// Let's move up
}

public boolean addSugar () {
// Did we add sugar to mix it ?
// Let's move up
// But we have drinkMilk !
}
```

> > Imagine you have a class with just 40 functions ( methods ) and they are organized like this way. We expect you will use pomade for your neck after you finish reading this script.

```java
// bad

public boolean addSugar () {..}

public boolean mixSugar () {
// Did we add sugar to mix it ?
// Let's move up
}

public boolean drinkMilk () {
// Did we mix sugar to drink coffee ?
// Let's move up
}
```

```java
//super

public boolean drinkMilk () {
// Did we mix sugar?
// Move next
}

public boolean mixSugar () {
// Did we add Sugar ?
// Move next
}

public boolean addSugar () {..}
```

By learning this trick you can not be a mess programmer, and you can avoid **WTF moments** when you search a function in long class, API or script.

<h2 style="font-size:17px;font-weight:bold">Avoid Switch Statement</h2>

By their nature `switch` do `N` things. If you will use `switch` you will break **SRP** rule.

```java
// very bad
public void drawShape (Shape shape) {
    switch (shape.type)
    {
        case RECTANGLE;
        drawRectangle();
        case CIRCLE;
        drawCircle();
        case TRIANGLE;
        drawTriangle();
        default:
        point();
    }
}
```

> > This function is large and it will grow when we add new Shape. It violates **Open-Closed Principale** (OCP).

```java
// good
public void drawShape (Shape shape) {
    if (shape.type==POINT) {
    point();
    }
    paint(shape.type);
}
```

> > What do you think now ? could you extract this function into other functions and make it better ? if yes [Pull New Request](pull)

<h2 style="font-size:17px;font-weight:bold">Functions Arguments</h2>

The ideal number of arguments for a function is **zero** (niladic). Next comes **one** (monadic), followed closely by **two** (dyadic). **Three** arguments (triadic) should be avoided where possible. More than three please could you justify why you're using three arguments?

```java
// very bad
public void write (File file, int size, String word, String extension, ...) {..}
```

```java
// bad
public void write (File file, ...args) {..}
```

```java
// good
public void write (File file, Array<Option> options) {..}
```

```java
//super
public void write (FileFactory fileFactory) {..}
```

> > We use `Factory Pattern` to create `FileFactory` object that contains all properties including the `file` and its `options`. This will make our tests easy and speedy.

<h2 style="font-size:17px;font-weight:bold">Flag Arguments In Monadic Functions</h2>

Passing a `boolean` into a function is a truly **terrible practice**. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing.

```java
//very bad
delete(true);
```

> > We expect this function will delete something, but when you pass `true` as a flag argument, you will immediately complicate the signature of the method. we will expect that function will do **two things** and the flag who will decide its behavior. In the world of software, a `deletion` operation is followed by `archive` operation, and we expect `delete` operation will `archive` too!

<h2 style="font-size:17px;font-weight:bold">Dyadic Functions</h2>

A function with two arguments is harder to understand than a monadic function.

```java
replay(video,pausedTime);
```

> > This function will replay a `video` at a `pausedTime`, anyone can understand it from the **name** and the **parameters**.

```java
minus(1,2);
```

> > Hmm! This function will make mathematic operation but could you expect the result? `-1` or `1`.

```java
pin(sticker,board);
```

> > This function will pin sticker on a specific board, anyone can understand it from the **name** and the **parameters** and nobody will expect that it pins a board on a sticker!

We recommend using `Factories`, `Enum`, `Object`, `Array` for two, and more arguments.

```java
// very bad
calculateVolume(width, height, depth, perimeter);
```

```java
// dimension is an object that contains width, height, depth and perimeter properties
calculateVolume(dimension);
```

<h2 style="font-size:17px;font-weight:bold">Triadic Functions</h2>

We will be in big trouble when our functions take three arguments. Programmers who will use your function, they need at least `2 minutes` to understand it very well. and you will spend more time to create tests for them. **tests! tests! tests !**

```java
// very bad
formatDate(1,2,1994)
```

> > Which one is the month `1` or `2`?

```java
// bad
formatDate(mm,d,yyyy)
```

> > Bad practice to name arguments.

```java
// good
formatDate(month,day,year)
```

> > But it has many arguments.

```java
// super
formatDate(dateFactory)
```

> > `DateFactory` is a factory that creates date instance. It includes properties such as `day`, `month`, `year` and it's extensible to add `time` without changing `formatDate` parameters each time.

<h2 style="font-size:17px;font-weight:bold">Have No Side Effects</h2>

Sometimes we write a function and we guess it does **one thing** but behind the scenes, it does a hidden thing without especially **Dyadic** functions.

```java
public boolean checkCredentials(String email, Char[] password) {

  if (email==getEmail() && password==getPassword()) {
    displayWelcomeMessage();
      return true;
    }
  return false;
}
```

> > You may notice this function does more than **one thing**, it checks credentials then displays welcome message but what it will happen if the credentials are correct but `displayWelcomeMessage()` does not work properly?

<h2 style="font-size:17px;font-weight:bold">Output Arguments</h2>

We use arguments as **inputs** not as **outputs**.

Let' say we have this class :

```java
public class Combat {
    Fighter jack, alex;
    // Previous code;
    attack(jack, alex);
    // Rest of code;
}
```

> > Who's the attacker `jack` or `alex`?

It doesn’t take long to look at the function signature and see:

```java
private void attack (Fighter attacked, Fighter attacker) {..}
```

> > You guessed `jack` is the attacker?

This clariﬁes the issue, but only at the expense of checking the declaration of the function.

In the days before object-oriented programming, it was sometimes necessary to have output arguments. However, much of the need for output arguments disappear in OO languages because this is intended to act as an output argument.

In other words, it would be better for `attack` to be invoked as

```java
     alex.attack(jhon);
```

<h2 style="font-size:17px;font-weight:bold">Command Query Separation</h2>

Functions should either **do something** or **answer something**, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion. Consider, for example, the following function:

```java
public boolean createFile (File file ) {..}
```

This function creates a new file and returns `true` if it is successful and false if no such file exists. This leads to odd statements like this:

```java
if (createFile(file)) {..}
```

The solution is to separate the **command** from the **query** like this :

```java
if (isFile(file)) {
    shareFile(file)
}
```

<h2 style="font-size:17px;font-weight:bold">Prefer Exceptions to Returning Error Codes</h2>

Don't use `if/else` to return `errors`.

```java
// bad
if (isFile(file)) {
    shareFile(file)
    }else {
    logger.log("This is not a file");
}
```

```java
// good
try {
   shareFile(file);
}catch (Exception e) {
  logger.log(e.getMessage())
}finally {
  close();
}

private void shareFile (File file) throws Exception {
  isFile (file) ? ... : ...
}
```

<h2 style="font-size:17px;font-weight:bold">Don't Repeat Yourself</h2>

Duplication is the root of all evil in software. duplicated `functions`, `classes`, `interfaces`, `if/else`, `loops` and so on. Structured programming, Aspect-Oriented Programming, Component Oriented Programming, are all, in part, strategies for eliminating duplication. We don't really see developers focus on these strategies but **[Design Patterns](designpatterns)** and **[Refactoring](Refactoring)** are the reasonable approaches to eliminate duplication.

<h2 style="font-size:17px;font-weight:bold">Senior Programmers Vs Junior Programmers</h2>

M. Ala Eddine says:

> _I don't measure seniority by years, I measure it by code quality. I don't call myself a senior developer, I let my code talks instead of me. There are so many senior developers who write ugly code on StackOverflow._

<a  href="https://twitter.com/intent/tweet?text=I20%don't20%measure20%seniority20%by20%years,20%I20%measure20%it20%by20%code20%quality.20%I20%don't20%call20%myself20%a20%senior20%developer,20%I20%let20%my20%code20%talk20%instead20%of20%me.20%There20%are20%senior20%developers20%who20%write20%ugly20%code20%on20%StackOverflow.">Tweet</a>

**Junior Developer**

```java
public void maxNumber (int a, int b) {
  if(a>b){
       return a
   }else{
      return b
   }
}
```

**Mid-Level Developer**

```java
public void maxNumber (int firstNumber, int secondNumber) {
   return firstNumber > secondNumber ? firstNumber : ( (firstNumber==secondNumber) ? equal() : secondNumber;
}
```

> > Don't worry if you use long names for your variables. We want to make our programs tell stories not to provide puzzles for their readers.

**Senior Developer**

```java
public void maxNumber (int firstNumber, int secondNumber) {
   if(firstNumber==secondNumber) equal();
     return Math.max(firstNumber,secondNumber);
}
```

## [Formatting](#Formatting)

<h2 style="font-size:20px;font-weight:bold">Braces</h2>

Braces are used with `if`, `else`, `for`, `do` and `while` statements, even when the body is empty or contains only a single statement.

<h2 style="font-size:17px;font-weight:bold">1. No line break before the opening brace.</h2>

```java
// bad
public int one ()
      {
        return 1;
      }
```

```java
// good
public int one () {
  return 1;
}
```

<h2 style="font-size:17px;font-weight:bold">2. Line break after the opening brace.</h2>

```java
// bad
public int one () { return 1;}
```

```java
// good
public int one () {
  return 1;
}
```

<h2 style="font-size:17px;font-weight:bold">3. Line break before the closing brace.</h2>

```java
// bad
public int one () {
  return 1;}
```

```java
// good
public int one () {
  return 1;
}
```

<h2 style="font-size:17px;font-weight:bold">4. Line break after the closing brace, only if that brace terminates a statement or terminates the body of a method, constructor, or named class. For example, there is no line break after the brace if it is followed by else or a comma.</h2>

```java
// bad
if (x==1) {
// do somehting
}
else {
// do other
}
```

```java
// good
if (x==1) {
// do somehting
}else {
// do other
}
```

<h2 style="font-size:20px;font-weight:bold">Block</h2>

<h2 style="font-size:15px;font-weight:bold">Empty Block</h2>

An empty block may be closed immediately after it is opened, with no characters or line break in between `({})`, unless it is part of a multi-block statement (one that directly contains multiple blocks: `if/else` or `try/catch/finally`.

```java
// very bad
try {
    doSomething();
} catch (Exception e) {}
```

> > No concise empty blocks in a multi-block statement.

```java
// bad
public void close () {
// We will implement it later
}
```

```java
// good
public void close () {..}
```

<h2 style="font-size:15px;font-weight:bold">One line per statement</h2>

Each statement is followed by a line break.

```java
// bad
String name; int size;
```

```java
// good
String name;
int size;
```

<h2 style="font-size:15px;font-weight:bold">Variable Declarations</h2>

Every variable declaration (field or local) declares only one variable.

```java
// bad
double width, height;
```

> > What if you've 10 variables with the type `int`?
> > Remember that we're looking for readability.

```java
// good
double width;
double height;
```

## [Comments](#Comments)

M. Ala Eddine says:

> _When I was a student and I don't have time to make my home coding project, I copy it from one of my classmate and I try to refactor it by changing names and adding a lot of comments. I use comments to cheat._

<a  href="https://twitter.com/intent/tweet?text=When20%I20%was20%a20%student20%and20%I20%don't20%have20%time20%to20%make20%my20%home20%coding20%project,20%I20%copy20%it20%from20%one20%of20%my20%classmate20%and20%I20%try20%to20%refactor20%it20%by20%changing20%names
and20%adding20%a20%lot20%of20%comments.20%I20%use20%comments20%to20%cheat">Tweet</a>

```java
// very bad

// Write characters in file
private void write (File file) {
  Char chars = []; // Array of characters
}
```

```java
private void writeChars (File file) {
    Char characters = [];
}
```

<h2 style="font-size:20px;font-weight:bold">Explain Yourself In Code</h2>

Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments. Rather than spend your time writing the comments that explain the mess you’ve made, spend it cleaning that mess.

```java
// very bad

// check the color, version and the operating system of the device
if (device.color="black" && device.version == 1.2 && device.operatingSystem=="android")
```

> > What if you will add `screen size` and `memory` in the future and you have 50 `checks` like this in your program? You will change both `comments` & `checks` 50 times.

```java
// good

// check the characteristics of the device
if (device.hasCharacteristics(color,version,operatingSsystem))
```

```java
//  super
if (device.hasCharacteristics (characteristics))
```

<h2 style="font-size:20px;font-weight:bold">Good Comments</h2>

Some comments are necessary or beneﬁcial.

<h2 style="font-size:17px;font-weight:bold">Legal Comments</h2>

Sometimes our corporate coding standards force us to write certain comments for legal reasons. For example, copyright and authorship statements are necessary and reasonable things to put into a comment at the start of each source ﬁle.

<h2 style="font-size:17px;font-weight:bold">Informative Comments</h2>

It is sometimes useful to provide basic information with a comment.

```java
// This method is deprecated in 1.2.6
private void clone () {..}

// This loop consume some memory
// We're trying to optimize it
for (index=0; index < clouds.length; index++) {..}
```

<h2 style="font-size:20px;font-weight:bold">Bad Comments</h2>

Most comments fall into this category. Usually, they are crutches or excuses for poor code or justiﬁcations for insufﬁcient decisions, amounting to little more than the programmer talking to himself.

<h2 style="font-size:17px;font-weight:bold">Redundant Comments</h2>

```java
public class Car {
  String color; // This is the color of a car
}

// return true if the device has memory and false if it has not
private boolean hasMemory (Device device) {...}
```

<h2 style="font-size:17px;font-weight:bold">Misleading Comments</h2>

```java
//bad

// return true if the board is blank and false if it's not
private boolean isBlank () {
  if(board.size==0) return true;
}
```

> > This method does not return `false`!

```java
/** The version of the device. */ private String operatingSystemVersion;
```

> > This is a version of an operating system not the version of a device!

<h2 style="font-size:17px;font-weight:bold">Noising Comments</h2>

Sometimes you see comments that are nothing but noise. They restate the obvious and provide no new information.

```java
/* Default constructor. */
public Paper () { }
/* Private method. */
private void pin () { }
```

## [Objects and Data Structures](#Objects-and-Data-Structures)

```java
public class User {
  private String firstName;
  private String lastName;

  public User (String firstName, String lastName) {
      this.firstName=firstName;
      this.lastName=lastName;
  }

  public String getFirstName () {
      return firstName;
  }

  public void setFirstName (String firstName) {
      this.firstName=firstName;
      return this;
  }

  public String getLastName () {
      return lastName;
}

public void setLastName (String lastName) {
      this.lastName=lastName;
      return this;
}
```

We make our variables `private` because we don't anyone touch them but why we expose them through `getters` and `setters`?

<h2 style="font-size:20px;font-weight:bold">Data Abstraction</h2>

Concrete Shape :

```java
public class Rectangle {
  public double width;
  public double height;
  public double area () {
    return width * heigth;
  }
}
```

Abstract Shape :

```java
public interface Shape {
  public double getWidth ();
  public double getHeigth ();
  public double area ();
}
```

The beautiful thing about the `abstract` shape is you can not tell whether the implementation is **Rectangle**, **Square**, or a **Circle**. The interface represents only the data structure and it gives you the freedom to implement your shapes as possible as you can.

Many programmers think that hiding implementation is by using the keyword `private` but the real definition of hiding implementation is about abstraction! In other words a `class` without `getters` and `setters`

Stick on your head :

**Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.**

## [Error Handling](#Error-Handling)

<h2 style="font-size:20px;font-weight:bold">Use Exceptions Rather Than Return Code</h2>

```java
// bad
public void startGame (Player player) {
    ...
    GameField gameField = createField();
      if (gameField.created()){
        if (player.status==READY)
         {
          play();
         }else {
          logger.log("Player is not ready")
         }
          playGame();
         }else {
            logger.log("Unable to create a game field")
         }
}
```

```java
// good
public void startGame (Player player) {
  ...
    try {
        playGame();
    }catch (GameError error) {
               logger.log(error)
    }

}

public void playGame () throws GameError {
   GameField gameField=createField();
   ....
}

public void createField () {
  ....
  throw new GameError("Unable to create a field")
  .....
}

public void play () {
  ....
  throw new GameError("Player is not ready")
  .....
}
```

<h2 style="font-size:20px;font-weight:bold">Don't Return Null</h2>

Do you check the `null` status in your code?

```java
....
public void promote (Post post) {
  if (post!=null) {
    Network network=socialMedia.getNetwork();
    network.share(post);
  }
}
....
```

> > What will happen if `socialMedia` is `null` ? or `network` is `null`?

We expect that you will solve this problem by checking `null` status :

```java
....
public void promote (Post post) {
  if (post!=null) {
    if (socialMedia!=null) {
       Network network=socialMedia.getNetwork();
      if (network!==null) {
          network.share(post);
       }else {
          return null;
       }
    }else {
       return null;
    }
  }else {
      return null;
  }
}
....
```

But did you notice when you use **JDK** methods they return `exceptions` for the case of `null` such as `NullPointerExpection`?

It’s easy to say that the problem with the code above is that it is missing a `null` check, but in actuality, the problem is that it has _too many_.

We expect that you will solve this problem by checking `null` status :

```java
....
public void promote (Post post) {
  try {
    Network network=socialMedia.getNetwork();
    network.share(post);
    } catch (PostSharingError postError) {
          logger.log(postError);
    }
}
```

<h2 style="font-size:20px;font-weight:bold">Don't Pass Null</h2>

Returning `null` from methods are bad, but passing `null` into methods is worse.

```java
public void area (double width, double height) {
  return width * height;
}
```

What will happen when you pass `null` :

```java
area(null,null);
```

Of course a `NullPointerException`.

We could solve this problem by throwing **Custom Exception** in `area` method.

```java
public void area (double width, double height) {
  if (width==null || height==null) throw InvalidArgumentException("Invalid argument")
          return width * height;
}
```

## [Classes](#Classes)

OOP is about `classes` and `objects`.

<h2 style="font-size:20px;font-weight:bold">Organization</h2>

Following the standard Java convention, a class should begin with :

1.  public static constants.
2.  private static variables.
3.  private instance variables.
4.  public functions should follow the list of variables.
5.  private utilities called by a public function right after the public function itself.

```java
// bad
public class Space {

  private double depth;
  private boolean opened;

  public static int PI=3.14;
  public static int VECTOR_DIMENSION= 3;

  private int area () {..}
  private static air;

  public double measureVolume (args) {..}

}
```

```java
// super
public class Space {

  public static int PI=3.14;
  public static int VECTOR_DIMENSION= 3;

  private static air;

  private double depth;
  private boolean opened;
  public double measureVolume (args) {..}
  private int area () {..}
}
```

<h2 style="font-size:20px;font-weight:bold">Should Be Small</h2>

The ﬁrst rule of classes is that they should be small. The second rule of classes is that they should be smaller than that.

With **functions** we measured size by counting physical lines. With **classes** we use a different measure. We count responsibilities.

Let's take the example of a Employee `class` that has 100 methods:

```java
public class Employee {
  .....
  public String getName () {..}
  public int getBadgeNumber () {..}
  public void manageTeam (args) {..}
  public void writeReport (args) {..}
  public void manageStuff (args) {..}
  public void developSoftware (args) {..}
  public void designSoftware (args) {..}
  public void testSoftware (args) {..}
  public void repairHardware (args) {..}
  .....
}
```

The problem with this `class` it has _many responsibilies_.

We can avoid that by creating extracting specific classes for each group of functions :

```java
public class Developer implements Employee {
  ...
  public void developSoftware (args) {..}
  public void testSoftware(args) {..}
       ...
  }

  public class Designer implements Employee{
       ...
       public void designSoftware (args) {..}
       ...
  }

  public interface Employee {
       ...
       String getName ();
       int getBadgeNumber ();
       ...
  }
```

<h2 style="font-size:20px;font-weight:bold">Single Responsibility Principale (SRP) </h2>

SRP is one of the more important concepts in OO design.

The Single Responsibility Principle (SRP) states that a class or module should have one, and only one reason to change.

```java
// bad

     public class Computer {

     public void setOperatingSystemName (String name){..}

     public void setOperatingSystemVersion (String version) {..}

     public void setOperatingSystemProvider (String provider) {..}

     public void getMaterialType () {..}

     public void getScreenSize () {..}

     public void getKeyboardCategory () {..}

     public void getGraphic () {..}

     public void getCPU () {..}

     }
```

```java
// bad
public class Computer {

  private Hardware hardware;
  private Software software;
}

public class Hardware {

  public void getMaterialType () {..}

  public void getScreenSize () {..}

  public void getKeyboardCategory () {..}

  public void getGraphic () {..}

  public void getCPU () {..}

}


public class Software {

  public void setOperatingSystemName (String name) {..}

  public void setOperatingSystemVersion (String version) {..}

  public void setOperatingSystemProvider (String provider) {..}

}
```

## [Kent Beck’s Four Rules Of Simple Design](#Kent-Beck’s-Four-Rules-Of-Simple-Design)

They are four rules that help us in creating well-designed software.

According to Kent, a design is “simple” if it follows these rules:

1.  Runs all the tests ( Code Coverage ).

2.  It contains no duplication.

3.  Expresses the intent of the programmer.

4.  Minimizes the number of classes and methods.

<h2 style="font-size:20px;font-weight:bold">Runs all the tests</h2>

Menai Ala Eddine says :

> Makeup make a woman beautiful. Tests make a software powerful. Don't ignore tests.

<a  href="https://twitter.com/intent/tweet?text=Makeup20%make20%a20%woman20%beautiful.20%Tests20%make20%a20%software20%powerful.20%Don't20%ignore20% tests.">Tweet</a>

<h2 style="font-size:20px;font-weight:bold">Contains no duplication</h2>

Duplication is the primary enemy of a well-designed system.

Duplication represents :

1. Additional work.

2. Additional risk.

3. Unnecessary complexity.

We can remove duplication by incremental refactoring. There's no release without duplication. The mechanism of refactoring is improving our code without breaking our tests.

Refactoring can be :

1. Increase cohesion.

2. Decrease coupling.

3. Separate concerns.

4. Modularize system concerns.

5. Shrink our functions and classes.

6. Choose better names.

```java
// bad

_Before refactoring_

public class Game {

  public void startCombat (Player player) {

    if (player.hasClothes() && player.hasWeapon() &&
        player.hasExtensions()) {
     ....
     }
  }

  public void changeCombat (Player player) {

    if (player.hasClothes() && player.hasWeapon() &&
        player.hasExtensions()) {
     ..
    }
  }
}
```

```java
// good

_After refactoring_

public class Game {

  public void startCombat (Player player) {

    if (player.isReady()) {
     ....
    }
  }
}

public void changeCombat (Player player) {

 if (player.isReady()) {
     ....
 }
    }
}

// Inside Player class
public boolean isReady() {
  return player.hasClothes() && player.hasWeapon()&& player.hasExtensions();
}
```

<h2 style="font-size:20px;font-weight:bold">Expresses the intent of the programmer</h2>

It's easy to write code that _we_ understand, but it's very hard to write code that _everyone_ can understand.

The only and the best solution to write programs for others is to let programs express themselves and what they do.

Here, are few tips can help you to write code for everyone :

1.  Choose meaningful names.

2.  Keep your classes and functions small.

3.  Use well-known design patterns.

4.  Create well-written unit tests.

5.  Add only informative comments.

6.  Repeat.

<h2 style="font-size:20px;font-weight:bold">Minimal Classes and Methods</h2>

By keeping our classes and methods minimal, we have an opportunity to eliminate duplication and avoid the chaos. Minimal means that classes and functions have a high-level of Single Responsibility Principale ( SRP ).

## [Smells and Heuristics](#Smells-and-Heuristics)

<h2 style="font-size:20px;font-weight:bold">Comments</h2>

<h2 style="font-size:17px;font-weight:bold">1. Inappropriate Information</h2>

Many developer add some _meta-data_ information in their comments such as `author`,`creation date`, `update data`, and so on, but they forget that there are tools that keep this information and changes such as **version control**.

```java
/** I changed the name of this method from "commentWithImage" to "commentWithMedia" because I added other media types such as Audios.*/
public void commentWithMedia (String comment, Media media) {..}
```

<h2 style="font-size:17px;font-weight:bold">2. Obselete Comment</h2>

A comment that has gotten old, irrelevant, and incorrect is obsolete.

```java
/**The last update of this class is 12-12-2019
....
....
*
*/
```

> > In the reality this class has new update in 30-05-2020

<h2 style="font-size:17px;font-weight:bold">3. Redundant Comment</h2>

A comment is redundant if it describes something that adequately describes itself.

```java
private String userName; // This is the name of user
```

> > Hmm! we thought it's reserved for the name of the car.

```java
// Check the user's password
if (user.getPassword() == decryptedPassword()) {
      ....
}
```

> > Hmm! we thought it checks the user's name.

```java
/**
* @param destination
* @return
* @throws NotExistDestinationException
*/
public gotToDestination (String destination) throws NotExistDestinationException
```

> > Please stop using this kind of Jdoc documentation in your code.

<h2 style="font-size:17px;font-weight:bold">4. Poorly Written Comment</h2>

```java
// This method deletes everything in the system
public boolean deleteAll () {..}
```

> > What did you mean with `Everything` ?

<h2 style="font-size:17px;font-weight:bold">5.  Commented-Out Code</h2>

Commented code, no meaningful comments, out-dated comments, hints, references, to-do tasks, ideas, and so on.

```java
public void decomposeEngine () {
  ...
  /**
   * Tomorrow I will explain why I added these variables
   * int phases=0;
   * Date date;
   */
   ...
}
```

<h2 style="font-size:20px;font-weight:bold">Functions</h2>

<h2 style="font-size:17px;font-weight:bold">1. Too Many Arguments</h2>

Functions should have a small number of arguments. No argument is best, followed by one, two, and three.

```java
public void read (String title, String sectionTitle, int pageNumber, int lineNumber) {..}
```

> > Let's say you've many functions like this and in the future, you will add `word` parameter, how many changes you will do? Also, can we see your unit test, please?

```java
public void read (BookOptions bookOptions) {..}
```

> > Simple, extensible, and easy to test.

<h2 style="font-size:17px;font-weight:bold">2. Flag Arguments</h2>

Unfortunately, many developers and even popular open-source projects use them.

```java
//bad
shutDown(true);
```

> > Could we know what `true` refers to?

```java
//good
boolean forcedShutdown = true;
shutDown(true);
```

> > At least, this can make sense.

```java
//super
shutDown();
enforceShutdown();
```

> > Why not like this? your function will keep SRP rule, easy to understand, extensible.

<h2 style="font-size:17px;font-weight:bold">3. Dead Functions</h2>

Methods that are never called should be discarded.

<h2 style="font-size:20px;font-weight:bold">Tests</h2>

The hard phase in the development cycle.

<h2 style="font-size:17px;font-weight:bold">1. Insufﬁcient Tests</h2>

How many tests should be in a test suite? Unfortunately, the metric many programmers use is “That seems like enough.”

<h2 style="font-size:17px;font-weight:bold">2. Use Coverage Tool</h2>

Coverage tools report gaps in your testing strategy. They make it easy to ﬁnd modules, classes, and functions that are insufﬁciently tested.

<h2 style="font-size:17px;font-weight:bold">3. Tests should be fast</h2>

A slow test is a test that won’t get run. When things get tight, it’s the slow tests that will be dropped from the suite. So do what you must to keep your tests fast.

## [Contributors](#Contributors)

- [Menai Ala Eddine](https://github.com/MenaiAla)

- [Ilyes Houdjej](https://github.com/ilyeSudo)

## [Chat With Us](#Chat-With-Us)

- Find us on [Spectrum](https://spectrum.chat/users/menai-ala-eddine)
