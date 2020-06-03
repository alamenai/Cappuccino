<h1 align="center">Cappuccino</h1>

<h4 align="center"><i>A mostly reasonable approach and non-boring guide for Junior Developers to write professional Oriented-Object code.</i></h4>
<hr>
<h6 align="center"><a href="https://github.com/MenaiAla/Cappuccino/pulls">Contribute</a>&nbsp &nbsp|&nbsp &nbsp <a  href="https://twitter.com/intent/tweet?text=Hello%20world">Share</a>&nbsp &nbsp|&nbsp &nbsp<a href="https://spectrum.chat/users/menai-ala-eddine">Chat</a></h6>

<hr>

> **Note**: This guide is inspired by Robert C. Martin's Book **Clean Code**, **Google Java Style Guide**, **Ali-baba Guide**, **Oracle Guide**, **hundreds of online blogs** and **our experience** with a simple and easy-to-learn style powered with **examples**.
> We try to reduce blah-blah and provide useful examples that cover all cases.

<hr>

In the old days, [Linus Torvalds](Trevals) said:

> _Talking is shit, show me the code_

In 2020 we say:

> _Code that works is shit, show us the tests_

[tweet](tweet)

M. Ala Eddine says:

> _Yesterday, I was writing code for machines. Today, I'm trying to write code for everyone._

[tweet](tweet)

<h2 style="font-size:24px;font-weight:bold">Why Cappuccino?</h2>

1. 99% of junior developers <u> **have no-time**</u> to read books that have <u> **400 or 500 pages**</u>.

2) Most of guidelines are <u>**static**</u> and <u> **bored**</u> with <u> **journal-like** </u> style.

3) Junior developers struggle to find <u>**easy-to-learn** </u> best practices and guidelines to improve their <u> **skills** </u> in <u> **short-time** </u>.

4) Junior developers want to write <u>**code that works**</u>, not a solid code that follows <u>**standard convention**</u>, pass all <u>**test cases**</u>, and can be <u>**scalable any time**</u>.

<h2 style="font-size:24px;font-weight:bold">Features & Benefits</h2>

- Built particularly for **junior developers** and also for all developers.

- **Ease to read**, **Simple** explanations and **rich** with examples.

- Able to write **quality code** in the future.

- Avoid your current repetitive **errors**.

- **Updates** and new **features** each week.

<h2 style="font-size:24px;font-weight:bold">Who read this guide</h2>

**[Menai Ala Eddine](..)**

> Though I'm the writer I enjoyed it as a reader.

**[Ilyes houdjej](..)**

> Ilyes houdjej feedback.

<h2 style="font-size:24px;font-weight:bold">Table of content</h2>

1. **[Meaningfull Names](#Meaningful-Names)**
2. **[Functions](#Functions)**
3. **[Formatting](#Functions)**
4. **[Comments](#Functions)**
5. **[Objects & Data Structures](#Functions)**
6. **[Error Handling](#Functions)**
7. **[Classes](#Functions)**
8. **[Kent Beck’s Four Rules Of Simple Design](#Functions)**
9. **[Smells and Heuristics](#Functions)**
10. **[In The Next Week](#Functions)**
11. **[Contributors](#Functions)**
12. **[Chat With Us](#Functions)**

<a href="" style="font-size:24px;font-weight:bold">Meaningfull Names</a>

Programming is about names and names are everywhere, we name our variables, functions, classes, and packages. Indeed, our code contains only names.

<h2 style="font-size:20px;font-weight:bold">Rules For Naming</h2>

<h2 style="font-size:17px;font-weight:bold">Package Names</h2>

Package names are all lowercase.

**Bad**

     com.app.Users.Data

**Good**

     com.app.users.data

<h2 style="font-size:17px;font-weight:bold">Class Names</h2>

Class names are written in UpperCamelCase except for domain models such as DO, BO, DTO, DAO, VO, and so on.

**Bad**

     public class user {..}

**Good**

     public class User {..}

**Bad**

     public class userDao {..}

**Good**

     public class UserDAO {..}

> > DAO refers to Data Access Object. We use this kind of class in the database layer in case of ORM persistence.

**Bad**

     public class HTMLPage {..}

**Good**

     public class HtmlPage {..}

**Bad**

     public class PrOgRaMMiNg {..}

**Good**

     public class Programming {..}

**Bad**

     public class CompanyOfFacebook {..}

**Good**

     public class FacebookCompany {..}

**Bad**

     public class AddingCoffeeInMilk {..}

**Good**

     public class CoffeeInMilk {..}

Also, you should know :

- Abstract class names must start with `Abstract` or `Base`.

- Pattern class names must end with The name of that `Pattern`.

- A class names that implement an interface must end with `Impl`.

* A class Enum must end with `Enum`.

* Exception class names must end with `Exception`.

* Test case names shall start with the class names to be tested and end with `Test`.

**Bad**

     public abstract class User {..}

**Good**

     public abstract class AbstractUser {..}

**Good**

     public abstract class BaseUser {..}

**Bad**

     public class User {..}

> > We assume this `class` implement `Factory` Pattern.

**Good**

     public class UserFactory {..}

**Bad**

     public class Profile implements IProfile {..}

**Good**

     public class ProfileImpl implements IProfile {..}

**Bad**

     public enum UserStatus {..}

**Good**

     public enum UserStatusEnum {..}

**Bad**

     public class HackedUser {..}

> > We assume this `class` is reserved for an `Exception`.

**Good**

     public class HackedUserException {..}

**Bad**

     public class UTest {..}

> > We assume this `class` is reserved for `Testing`.

**Good**

     public class UserTest {..}

<h2 style="font-size:17px;font-weight:bold">Method Names</h2>

Method names are written in lowercase.

**Bad**

     public void ConnectNetwork () {..}

**Bad**

     public void CONNECTNETWORK () {..}

**Bad**

     public void connect_network () {..}

**Good**

     public void connectNetwork () {..}

<h2 style="font-size:17px;font-weight:bold">Constants Names</h2>

Constant names use CONSTANT_CASE: all uppercase letters, with each word separated from the next by a single underscore. But what is a constant, exactly?

Constants are `static final` fields whose contents are deeply immutable and whose methods have no detectable side effects. This includes **primitives**, **Strings**, **immutable types**, and **immutable collections** of immutable types. If any of the instance's observable state can change, it is not a constant.

Unfortunately, we still see developers who define their constants like this :

      public static final int pi = 3.14;

**Bad**

     static final ImmutableMap<String, Integer> facebookFounders = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);

**Good**

      static final ImmutableMap<String, Integer> FACEBOOK_FOUNDERS = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);

**Bad**

     static  ImmutableMap<String, Integer> GOOGLE_FOUNDERS = ImmutableMap.of("Mark Zuckerburg", 40, "Andrew McCollum", 38);

> > Because it's not a `constant`. We removed `final`
> > keyword.

**Good**

       static  ImmutableMap<String, Integer> googleFounders= ImmutableMap.of("Lary Page", 58, "Sergey Bring", 52);

<h2 style="font-size:17px;font-weight:bold">Parameters Names</h2>

Parameters' names are written in lowercase.

**Bad**

     public void area (int Width, int Height) {..}

**Good**

     public void area (int width, int height) {..}

<h2 style="font-size:20px;font-weight:bold">Use Intention-Revealing Names</h2>

Choosing a convention and good names may take time but saves more then it takes. So take your names Seriously and let your code talking about itself not by providing additional useless comments.

**Very Bad**

     int d; // daily active users

> > Without comment we can guess it `day`.

**Bad**

     int dau; // daily active users

**Good**

     int activeUsers; // daily active users

> > Without comment we can guess it `monthlyActiveUsers`.

**Super**

     int dailyActiveUsers;

**Bad**

      public List<User> getAll () {..} // get list of users

> > We know this method gets all users but what kind of users ? `online users`, `offline users`? Furthermore, if someone invokes this method how does he know that it returns `List`,`Map`, or `Set`?

**Good**

     public List<User> getUsers () {..}

**Super**

     public List<User> getUsersList () {..}

**Fantastic**

     public List<User> getAllUsersList () {..}

<h2 style="font-size:20px;font-weight:bold">Avoid Disinformation & Abbreviation</h2>

You should write code for others not only for yourself!

**Bad**

      String os; // operating system name

> > Without comment we can guess it `Open Source`.

**Good**

    String operatingSystem;

> > But an operating system can have many properties.

**Super**

    String operatingSystemName;

<h2 style="font-size:17px;font-weight:bold">Don't use prefixes and PHP style</h2>

**Bad**

          String __Name;
          int age_;
          double $_amount;

**Bad**

          String LName;
          int Age;
          double __amount;

**Good**

          String name;
          int age;
          double amount;

<h2 style="font-size:17px;font-weight:bold">Make Meaningful Distinctions</h2>

Programmers create problems for themselves when they write code solely to satisfy a compiler or interpreter.

**Bad**

      public static void copyChars (char s[], char d[]) {..}

**Good**

    public static void copyChars (char src[], char dest[]) {..}

**Super**

    public static boolean copyChars (char source[], char destination[]) {..}

> > > You may notice that we used `boolean` instead of `void`. This will help us to improve the developer experience and make the function more reusable and testable. Without `return` we could not know if the characters are copied properly or no.

<h2 style="font-size:17px;font-weight:bold">Use Pronounceable Names</h2>

Humans are good at words. A signiﬁcant part of our brains is dedicated to the concept of words. And words are, by deﬁnition, pronounceable.

**Bad**

      public static void genAuthPswrd () {..}

> > > You will be able to pronounce it only if you drink 10 cups of wine!

**Good**

    public static void generateAuthPassword () {..}

**Super**

    public static void generateAuthenticationPassword () {..}

<h2 style="font-size:17px;font-weight:bold">Use Searchable Words</h2>

I'm sure that most of us use direct numbers in check-in conditions.

**Bad**

      if (connectedUsers==100) {..}

> > Imagine that you've 50 `checks` like this , how many changes you will make?

**Good**

       public static final MAX_CONNECTION = 100;
       if (connectedUsers==MAX_CONNECTION) {..}

<h2 style="font-size:17px;font-weight:bold">Avoid Encodings</h2>

In days of old, programmers were forced to add notations and suffixes and prefixes for variables, classes, and functions because the compiler did not check the types in those days.

Today, most programming languages are typed.

**Bad**

     String passwordString;
     int maxConInteger;
     User appUser;

**Good**

     String password;
     int maxConnections;
     User user;

> > Remember that using `String` for passwords is bad practice because `String` is immutable even if you encrypt it. Use `Char []` instead of it.

**Bad**

    public class CarFactory implements CarFactoryInterface {..}

**Good**

    public class CarFactoryImp implements ICarFactory {..}

<h2 style="font-size:17px;font-weight:bold">Avoid Mental Mapping</h2>

Not all readers are translators and they can understand what's in your mind. Don't try to be a smart programmer in your code, Be an explainer!

<h2 style="font-size:15px;font-weight:bold">Loops</h2>

Certainly, a loop counter may be named `i` or `j` or `k`.Those single-letter names for loop counters are traditional.

**Bad**

    for (i=0; i< onlineUsersList.length; i++) {
     int j=0;
     while (j<10) {..}
    }

**Good**

    for (index=0; index< onlineUsersList.length; index++) {
     int internalIndex=0;
     while ( internalIndex==0) {..}
     }

<h2 style="font-size:15px;font-weight:bold">Class Names</h2>

Classes and objects should have noun or noun phrase names like `User`, `Page`, `Profile`. Avoid words like `Admin`, `Process`, `OS`, `Http`, or `Setup` in the name of a class.

- A class **name** should not be one letter `X`.
- A class **name** should not be a **verb**.
- A class **name** should not be a **part** of the name.
- A class **name** should not have contain **conjunctions** ( `And`, `Or` ) or **operations** ( `Plus`, `Minus`).
- A class **name** should be a **complete** and **comprehensive** name.

**Bad**

      public class OnOrOFF {..}
      public class Work {..}
      public class Addr {..}

**Good**

      public class LampState {..}
      public class Activity {..}
      public class Address {..}

<h2 style="font-size:15px;font-weight:bold">Method Names</h2>

Methods should have verb or verb phrase names like `addUser`, `deletePage`, or `save`. Accessors, mutators, and predicates should be named for their value and preﬁxed with `get`, `set`, and `is`.

**Bad**

    String username = user.userName();

    Puzzle initialPuzzle = new Puzzle (pieces)

**Good**

    String username = user.getName();

    Puzzle randomPuzzle = PuzzleContext.initRandomPuzzle(pieces); // static factory

> > We use static factory methods with names to describe the returned `object` from that arguments. In logic, when you start a game you will have **only one** initiation or starting state.

<h2 style="font-size:17px;font-weight:bold">Don't Be Cute</h2>

Cuteness in code may work against you and your coding style. Or even your personality when a stranger read your code.

**Bad**

    public class Poppy {..}
    public class Dude {..}

**Good**

    public class Cat {..}
    public class Friend {..}

<h2 style="font-size:17px;font-weight:bold">Pick one word per concept</h2>

In other words, don't use the whole lexical champ in the same class. Imagine that you have `get` `find` `fetch` `retrieve` `search` or `set`, `assign` and `add`, and so on in the same class or script. Many developers make this mistake and you should avoid it by choosing **one word** for the **same action**.

**Bad**

    public class Book {
    public Book getOneBook () {..}
    public List<Book> findAllBooksList () {..}
    public List <Book> fetchFavoriteBooks () {..}
    }

**Good**

    public class Book {
    public Book getOneBook () {..}
    public List<Book> getAllBooksList () {..}
    public List <Book> getFavoriteBooksList () {..}
    }

> > As a standard we use `find` in database layer classes and `fetch` for async methods that are related to external APIs.

If you follow the **one word per concept** rule, you could end up with many classes that have, for example, an `add` method. As long as the parameter lists and return values of the various add methods are semantically equivalent, all is well. But sometimes, we will be enforced to break the concept to become more descriptive.

**Good**

    public class Sticker {
    public boolean add () {..}
    public boolean remove () {..}
    }

**Super**

    public class Sticker {
    public boolean pin () {..}
    public boolean unpin () {..}
    }

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

**Bad**

    public class ProfileVisitor {..}

> > What the word `Visitor` refers to? It refers to its real sense or it refers to `Visitor` Pattern?

**Good**

    public class ProfileSingleton {..}

> > We understand this `class` uses `Singleton` Pattern.

**Good**

    public class RocketThread extends Thread {..}

> > We understand this `class` extends `Thread`.

**Good**

    public class AlbumFactory {..}

> > We understand this `class` uses `Factory` Pattern.

<h2 style="font-size:17px;font-weight:bold">Provide Meaningful Context</h2>

Each variable has one context. Each function or method has one context. Each class has one context, not two or three.

**Bad**

    public class Computer {
    String v;
    String os;
    }

> > What's `v` and `os` ?

**Good**

    public class Computer {
    String version;
    String operatingSystem;
    }

**Super**

    public class Computer {
    String version;
    List<OperatingSystem> operatingSystems;
    }

    public class OperatingSystem {
    String name;
    String version;
    Date distributionDate;
    }

> > A computer can have more than one operating system. PCs can run both Windows and Linux.

**Bad**

    public class User {
    String firstName;
    String lastName;
    String street;
    String city;
    String zipCode;
    String state;
    }

**Good**

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

> > You can use `FullName` class for other classes in the future for example: `Customer`,`Advertiser`. Also, each user may have more than one `address`

<a href="" style="font-size:24px;font-weight:bold">Functions</a>

The reason we write functions is to decompose a larger concept into small concepts.

<h2 style="font-size:17px;font-weight:bold">Use Descriptive Names</h2>

The name of the function should be a **verb** and describes what it does.
The function and argument should form a very nice verb/noun pair.

**Bad**

    public void txt2pdf () {..}

**Good**

    public void convertTxt2Pdf () {..}

**Super**

    public void convertTextToPdf () {..}

Uncle Bob said :

> Don’t be afraid to make a name long. A long descriptive name is better than a short enigmatic name. A long descriptive name is better than a long descriptive comment.

M. Ala Eddine says:

> Both **name** and **parameters** will tell me what your function does.

**Bad**

    // This function adds only one item
    public void add (Item item) {..}

**Good**

    public void addOne (Item item) {..}

**Good**

    public void addSingle (Item item) {..}

**Super**

    public void insertOne (Item item) {..}

> > `add` is a generic word for a function that adds `items` into a `list` or `array`. We prefer `insert`.

<h2 style="font-size:17px;font-weight:bold">Small!</h2>

The ﬁrst rule of functions is that they should be small. The second rule of functions is that they should be smaller than that.

**Very Bad**

    public void write () {
    // 10 blocks or 100 lines
    }

> > You will spend a **month** to create a test that passes successfully.

**Bad**

    public void write () {
    // 4 blocks or 40 lines
    }

> > You will spend a **week** to create a test that passes successfully.

**Good**

    public void write () {
    // 2 blocks or 10 lines
    }

> > You will spend **10 minutes** to create a test that passes successfully.

**Super**

    public void write () {
    // 1 block
    }

**Fantastic**

    public void write () {
    // one line
    }

> > You will spend **2 minutes** to test this function.

<h2 style="font-size:15px;font-weight:bold">Blocks and Indenting</h2>

This implies that the blocks within `if` statements, `else` statements, `while` statements, and so on should be one line long.

**Bad**

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

**Good**

    public void vote () {
    try {
    // do something
    } catch(e) {
    // handle exception
    }
    }

**Super**

    public void vote () {
    try {
    // do something
    }catch (e) {
    // handle exception
    }
    }finally {
    // finalize with something
    }

> > Most programmers miss `finally` block.

<h2 style="font-size:17px;font-weight:bold">Do one thing</h2>

The problem with this rule is how do I count one thing?

We prefer count **one thing** by **one block**.

**Bad**

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

**Good**

        public void commit () {
        // one block
        if (condition) {
        // do X
        }
        else (condition) {
        // do X1
        }
        }

**Super**

        public void commit () {
        // one block
        if (condition) {
        // do X
        }
        // do X1
        }

**Good**

        public void commit () {
        // one block
        for (int index=0; index<list.length; index++) {
        // do X
        }
        }

**Good**

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

It's not only you who have this problem, all of us we struggle to create functions that follow Single Responsibility Principale **SRP**. But, there's a _Quote_ that help us understand SRP rule :

> > Functions do one thing. They should do it well. They should do it only.

- If you can explain your function in **one short paragraph** without using **And** or **Or**, your function does one thing.

- If you can not extract your function into other functions, your function does one thing.

**How to create a function that sends an email ?**

To send an email, we check if there's an `available connection` **and** a `constructed email`.

> **Note**: You may notice **and** here but it refers that there are two tests in one level, not 2 things.

**Very Bad**

    public void sendEmail (Email email) {
    // 10-20 lines of code that tests internet connection

    if (email!=null) {
      // do thing
     }else {
       // do other thing
      }
    }

**Bad**

    public void sendEmail (Email email) {
    try {
      // 10-20 lines of code that tests internet
    connection

    if (email!=null) {
      // do thing
     }
    }catch (Exception e) {..}
    }

**Good**

    public void sendEmail (Email email) {
    try {
     if (isConnected()) {
     if (email!=null) {
      // do thing
     }
        }
     }catch (Exception e) {..}
    }

**Super**

    public boolean sendEmail (Email email) {
    try {
     if (isConnected()) {
     // sending email code-block
     }
     }
     catch (Exception e) {
     // handle error
     return false;
     }finally {
     // final action
     }
    }

> > You may noticed that we removed `if (email!=null) {..}` because the test will be outside of the function.

<h2 style="font-size:17px;font-weight:bold">Reading Code From Top To Down</h2>

Nice code style is not the same as a well-organized code.

We can explain step-down rule through these actions:

- To drink milk we mix sugar first.

- To mix sugar we add sugar first.

- To add sugar .......

**Very Bad**

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

> > Imagine you have a class with just 40 functions ( methods ) and they are organized like this way. We expect you will use pomade for your neck after you finish reading this script.

**Bad**

    public boolean addSugar () {..}

    public boolean mixSugar () {
    // Did we add sugar to mix it ?
    // Let's move up
    }

    public boolean drinkMilk () {
    // Did we mix sugar to drink coffee ?
    // Let's move up
    }

**Super**

    public boolean drinkMilk () {
    // Did we mix sugar?
    // Move next
    }

    public boolean mixSugar () {
    // Did we add Sugar ?
    // Move next
    }

    public boolean addSugar () {..}

By learning this trick you can not be a mess programmer, and you can avoid **WTF moments** when you search a function in long class, API or script.

<h2 style="font-size:17px;font-weight:bold">Avoid Switch Statement</h2>

By their nature `switch` do `N` things. If you will use `switch` you will break **SRP** rule.

**Very Bad**

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

> > This function is large and it will grow when we add new Shape. It violates **Open-Closed Principale** (OCP).

**Good**

    public void drawShape (Shape shape) {
    if (shape.type==POINT) {
    point();
    }
    paint(shape.type);
    }

> > What do you think now ? could you extract this function into other functions and make it better ? if yes [Pull New Request](pull)

<h2 style="font-size:17px;font-weight:bold">Functions Arguments</h2>

The ideal number of arguments for a function is **zero** (niladic). Next comes **one** (monadic), followed closely by **two** (dyadic). **Three** arguments (triadic) should be avoided where possible. More than three please could you justify why you're using three arguments?

**Very Bad**

        public void write (File file, int size, String word, String extension, ...) {..}

**Bad**

        public void write (File file, ...args) {..}

**Good**

        public void write (File file, Array<Option> options) {..}

**Super**

        public void write (FileFactory fileFactory) {..}

> > We use `Factory Pattern` to create `FileFactory` object that contains all properties including the `file` and its `options`. This will make our tests easy and speedy.

<h2 style="font-size:17px;font-weight:bold">Flag Arguments In Monadic Functions</h2>

Passing a `boolean` into a function is a truly **terrible practice**. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing.

**Very Bad**

        delete(true);

> > We expect this function will delete something, but when you pass `true` as a flag argument, you will immediately complicate the signature of the method. we will expect that function will do **two things** and the flag who will decide its behavior. In the world of software, a `deletion` operation is followed by `archive` operation, and we expect `delete` operation will `archive` too!

<h2 style="font-size:17px;font-weight:bold">Dyadic Functions</h2>

A function with two arguments is harder to understand than a monadic function.

     replay(video,pausedTime);

> > This function will replay a `video` at a `pausedTime`, anyone can understand it from the **name** and the **parameters**.

     minus(1,2);

> > Hmm! This function will make mathematic operation but could you expect the result? `-1` or `1`.

    pin(sticker,board);

> > This function will pin sticker on a specific board, anyone can understand it from the **name** and the **parameters** and nobody will expect that it pins a board on a sticker!

We recommend using `Factories`, `Enum`, `Object`, `Array` for two, and more arguments.

**Very Bad**

     calculateVolume(width, height, depth, perimeter);

**Super**

     // dimension is an object that contains width, height, depth and perimeter properties
     calculateVolume(dimension);

<h2 style="font-size:17px;font-weight:bold">Triadic Functions</h2>

We will be in big trouble when our functions take three arguments. Programmers who will use your function, they need at least `2 minutes` to understand it very well. and you will spend more time to create tests for them. **tests! tests! tests !**

**Very Bad**

     formatDate(1,2,1994)

> > Which one is the month `1` or `2`?

**Bad**

     formatDate(mm,d,yyyy)

> > Bad practice to name arguments.

**Good**

     formatDate(month,day,year)

> > But it has many arguments.

**Super**

     formatDate(dateFactory)

> > `DateFactory` is a factory that creates date instance. It includes properties such as `day`, `month`, `year` and it's extensible to add `time` without changing `formatDate` parameters each time.

<h2 style="font-size:17px;font-weight:bold">Have No Side Effects</h2>

Sometimes we write a function and we guess it does **one thing** but behind the scenes, it does a hidden thing without especially **Dyadic** functions.

    public boolean checkCredentials(String email, Char[] password) {

    if (email==getEmail() && password==getPassword())
    {
      displayWelcomeMessage();
      return true;
    }
      return false;
    }

> > You may notice this function does more than **one thing**, it checks credentials then displays welcome message but what it will happen if the credentials are correct but `displayWelcomeMessage()` does not work properly?

<h2 style="font-size:17px;font-weight:bold">Output Arguments</h2>

We use arguments as **inputs** not as **outputs**.

Let' say we have this class :

      public class Combat {
       Fighter jack, alex;
      // Previous code;
      attack(jack, alex);
      // Rest of code;
      }

> > Who's the attacker `jack` or `alex`?

It doesn’t take long to look at the function signature and see:

      private void attack (Fighter attacked, Fighter attacker) {..}

> > You guessed `jack` is the attacker?

This clariﬁes the issue, but only at the expense of checking the declaration of the function.

In the days before object-oriented programming, it was sometimes necessary to have output arguments. However, much of the need for output arguments disappear in OO languages because this is intended to act as an output argument.

In other words, it would be better for `attack` to be invoked as

     alex.attack(jhon);

<h2 style="font-size:17px;font-weight:bold">Command Query Separation</h2>

Functions should either **do something** or **answer something**, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion. Consider, for example, the following function:

      public boolean createFile (File file ) {..}

This function creates a new file and returns `true` if it is successful and false if no such file exists. This leads to odd statements like this:

       if (createFile(file)) {..}

The solution is to separate the **command** from the **query** like this :

      if (isFile(file)) {
       shareFile(file)
       }

<h2 style="font-size:17px;font-weight:bold">Prefer Exceptions to Returning Error Codes</h2>

Don't use `if/else` to return `errors`.

**Bad**

      if (isFile(file)) {
       shareFile(file)
       }else {
       logger.log("This is not a file");
       }

**Good**

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

<h2 style="font-size:17px;font-weight:bold">Don't Repeat Yourself</h2>

Duplication is the root of all evil in software. duplicated `functions`, `classes`, `interfaces`, `if/else`, `loops` and so on. Structured programming, Aspect-Oriented Programming, Component Oriented Programming, are all, in part, strategies for eliminating duplication. We don't really see developers focus on these strategies but **[Design Patterns](designpatterns)** and **[Refactoring](Refactoring)** are the reasonable approaches to eliminate duplication.

<h2 style="font-size:17px;font-weight:bold">Senior Programmers Vs Junior Programmers</h2>

M. Ala Eddine says:

> _I don't measure seniority by years, I measure it by code quality. I don't call myself a senior developer, I let my code talk instead of me. There are senior developers who write ugly code on StackOverflow._

[tweet](tweet)

**Junior Developer**

     public void maxNumber (int a, int b) {
     if(a>b){
       return a
     }else{
      return b
     }
    }

**Mid-Level Developer**

     public void maxNumber (int firstNumber, int secondNumber) {
     return firstNumber > secondNumber ? firstNumber : ( (firstNumber==secondNumber) ? equal() : secondNumber;
    }

> > Don't worry if you use long names for your variables. We want to make our programs tell stories not to provide puzzles for their readers.

**Senior Developer**

     public void maxNumber (int firstNumber, int secondNumber) {
     if(firstNumber==secondNumber) equal();
     return Math.max(firstNumber,secondNumber);
     }

**Junior Developer**

     private int getTotalVowels(String phrase) {

     }

**Senior Developer**

     private int getTotalVowels(String phrase) {
    return phrase.split('').reduce((accumulator,character)=> phrase.filter(
    }

<a href="" style="font-size:24px;font-weight:bold">Formatting</a>

<h2 style="font-size:20px;font-weight:bold">Braces</h2>

Braces are used with `if`, `else`, `for`, `do` and `while` statements, even when the body is empty or contains only a single statement.

<h2 style="font-size:17px;font-weight:bold">1. No line break before the opening brace.</h2>

**Bad**

      public int one ()
      {
        return 1;
      }

**Good**

      public int one () {
        return 1;
      }

<h2 style="font-size:17px;font-weight:bold">2. Line break after the opening brace.</h2>

**Bad**

      public int one () { return 1;}

**Good**

      public int one () {
        return 1;
      }

<h2 style="font-size:17px;font-weight:bold">3. Line break before the closing brace.</h2>

**Bad**

      public int one () {
      return 1;}

**Good**

      public int one () {
        return 1;
      }

<h2 style="font-size:17px;font-weight:bold">4. Line break after the closing brace, only if that brace terminates a statement or terminates the body of a method, constructor, or named class. For example, there is no line break after the brace if it is followed by else or a comma.</h2>

**Bad**

      if (x==1) {
        // do somehting
      }
      else {
        // do other
      }

**Good**

       if (x==1) {
        // do somehting
        }else {
        // do other
        }

<h2 style="font-size:20px;font-weight:bold">Block</h2>

<h2 style="font-size:15px;font-weight:bold">Empty Block</h2>

An empty block may be closed immediately after it is opened, with no characters or line break in between `({})`, unless it is part of a multi-block statement (one that directly contains multiple blocks: `if/else` or `try/catch/finally`.

**Very Bad**

       try {
       doSomething();
       } catch (Exception e) {}

> > No concise empty blocks in a multi-block statement.

**Bad**

      public void close () {
      // We will implement it later
      }

**Good**

       public void close () {..}

<h2 style="font-size:15px;font-weight:bold">One line per statement</h2>

Each statement is followed by a line break.

**Bad**

      String name; int size;

**Good**

         String name;
         int size;

<h2 style="font-size:15px;font-weight:bold">Variable Declarations</h2>

Every variable declaration (field or local) declares only one variable.

**Bad**

      double width, height;

> > What if you've 10 variables with the type `int`?
> > Remember that we're looking for readability.

**Good**

         double width;
         double height;

<a href="" style="font-size:24px;font-weight:bold">Comments</a>

M. Ala Eddine says:

> _When I was a student and I don't have time to make my home coding project, I copy it from one of my classmate and I try to refactor it by changing names and adding a lot of comments. I use comment to cheat._

[tweet](tweet)

**Very Bad**

        // Write characters in file
        private void write (File file) {
        Char chars = []; // Array of characters
        }

**Super**

    private void writeChars (File file) {
    Char characters = [];
    }

<h2 style="font-size:20px;font-weight:bold">Explain Yourself In Code</h2>

Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments. Rather than spend your time writing the comments that explain the mess you’ve made, spend it cleaning that mess.

**Very Bad**

        // check the color, version and the operating
        system of the device

       if (device.color="black" && device.version
          ==1.2 && device.operatingSystem=="android")

> > What if you will add `screen size` and `memory` in the future and you have 50 `checks` like this in your program? You will change both `comments` & `checks` 50 times.

**Good**

       // check the characteristics of the device
       if (device.hasCharacteristics
         (color,version,operatingSsystem))

**Super**

    if (device.hasCharacteristics (characteristics))

<h2 style="font-size:20px;font-weight:bold">Good Comments</h2>

Some comments are necessary or beneﬁcial.

<h2 style="font-size:17px;font-weight:bold">Legal Comments</h2>

Sometimes our corporate coding standards force us to write certain comments for legal reasons. For example, copyright and authorship statements are necessary and reasonable things to put into a comment at the start of each source ﬁle.

<h2 style="font-size:17px;font-weight:bold">Informative Comments</h2>

It is sometimes useful to provide basic information with a comment.

        // This method is deprecated in 1.2.6
        private void clone () {..}

         // This loop consume some memory
         // We're trying to optimize it
         for (index=0; index < clouds.length; index++) {..}

<h2 style="font-size:20px;font-weight:bold">Bad Comments</h2>

Most comments fall into this category. Usually, they are crutches or excuses for poor code or justiﬁcations for insufﬁcient decisions, amounting to little more than the programmer talking to himself.

<h2 style="font-size:17px;font-weight:bold">Redundant Comments</h2>

            public class Car {
            String color; // This is the color of a car
            }

            // return true if the device has memory
            and false if it has not
            private boolean hasMemory (Device device) {
             ...
            }

<h2 style="font-size:17px;font-weight:bold">Misleading Comments</h2>

          // return true if the board is blank
            and false if it's not
            private boolean isBlank () {
            if(board.size==0) return true;
            }

> > This method does not return `false`!

       /** The version of the device. */ private String operatingSystemVersion;

> > This is a version of an operating system not the version of a device!

<h2 style="font-size:17px;font-weight:bold">Noising Comments</h2>

Sometimes you see comments that are nothing but noise. They restate the obvious and provide no new information.

      /** * Default constructor. */
            public Paper () { }
      /** * Private method. */
            private void pin () { }

<a href="" style="font-size:24px;font-weight:bold">Objects & Data Structures</a>

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

We make our variables `private` because we don't anyone touch them but why we expose them through `getters` and `setters`?

<h2 style="font-size:20px;font-weight:bold">Data Abstraction</h2>

Concrete Shape :

      public class Rectangle {
      public double width;
      public double height;
      public double area () {
      return width * heigth;
      }
      }

Abstract Shape :

     public interface Shape {
      public double getWidth ();
      public double getHeigth ();
      public double area ();
      }

The beautiful thing about the `abstract` shape is you can not tell whether the implementation is **Rectangle**, **Square**, or a **Circle**. The interface represents only the data structure and it gives you the freedom to implement your shapes as possible as you can.

Many programmers think that hiding implementation is by using the keyword `private` but the real definition of hiding implementation is about abstraction! In other words a `class` without `getters` and `setters`

Stick on your head :

**Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.**

<a href="" style="font-size:24px;font-weight:bold">Error Handling</a>

<h2 style="font-size:20px;font-weight:bold">Use Exceptions Rather Than Return Code</h2>

**Bad**

            public void startGame (Player
