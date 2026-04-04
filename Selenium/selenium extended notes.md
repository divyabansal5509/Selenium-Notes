git add .
git commit -m "first commit"
git push



# **SELENIUM :**

->Selenium mad by google in **2008**
,it is a functional testing tool

-> It is an open source tool, supports different browsers like chrome, firefox, edge, safari; can use in window, mac n Linux

### **4 components:-**

**Selenium IDE** - Integrated development environment

**Selenium RC** - Remote Control (stopped after 3.0 release)

**Selenium webdriver** (2011 in version 2.0) very important

**Selenium Grid**

**Languages supported by selenium** - Java, python, perl, ruby, php, c#, etc

## **Selenium IDE**
 - It identify the application objects ie button, link, checkbox, etc using locators (basically html)

### *Types of locators:*
- ID 

- NAME

- CLASSNAME
- TAGNAME
- LINKTEST
- PARTIALLINKTEXT
- XPATH
- CSS SELECTOR

### Adding on browser:-

- It is a plugin tool for browser .
- Open edge browser or firefox .
- Type selenium ide edge.
- Click on selenium ide edge add-on.
- you need to add this plugin/add-on.
- Click on get and add Extension.
- you can find it in manage extentions on top right of the browser(puzzle emoji).
----

## **Record a new test in a new project**
- it will record the keyboard and mouse operation which we perform on an web application during testing and it will generate the test script

- To rec:-
click on record -> name -> ok -> url -> start rec

- it will open the website in recording mode 
register - put details,etc
u can stop rec from top right of the tab
once stopped u need to provide script name - ok
u can run current test, also it will start and run the browser enter details on its own
---

## **How does it work? - it uses locators**

- **Manual way** :-
create a new project - name - ok
command -type/click
Target -link/id
Value - data
---

### **Selenium ide drawbacks:**
- doesn't support all browsers like chrome, opera and safari
- we cannot implement programming logic(cannot run py or other programs here)
- it will record unnecessary actions also(maximise, new tab)
- we cannot implement retesting (data is static)
- cannot handle alerts or anything which has implemented logic
---

## **Selenium webdriver:**
- a core component of the open-source Selenium suite used for automating web browsers
- we can test web based application.
- we can implement programming logic - java,py,etc
supports all browser
- we can implement retesting
- we can handle the alerts and errors
- we can also perform parallel web testing
---

### **Software configuration is important:**

**making new maven project -** 
- file->new->maven project->name,checkbox(create simple project)->next
- group id -> Selenium
- Artifact id -> WebDriver->Finish
---

### **New maven project comes with:-**
- src/main/java - we do coding here

- src/main/resources - maintain all the data files

- src/test/java - selenium web driver script

- src/test/resources - if u want to maintain any test data 

pom.xml - configuration files - 10marks

- maven  repository -> mvnrepository.com -> selenium 4.41 version
mvnrepository.com ->  search selenium java-click ->latest version(4.41.0)

- click and scroll 
copy 
  <dependencies>
<!-- Source: https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java -->
<dependency>
    <groupId>org.seleniumhq.selenium</groupId>
    <artifactId>selenium-java</artifactId>
    <version>4.41.0</version>
    <scope>compile</scope>
</dependency>

</dependencies>

open pom.xml

before </project> write <dependencies>  </dependencies>
and copy that in dependencies
save
---

search testNG on mvnrepository.com 
click on the first one TestNG
click on version 7.12.0
scroll and copy 

<!-- Source: https://mvnrepository.com/artifact/org.testng/testng -->
<dependency>
    <groupId>org.testng</groupId>
    <artifactId>testng</artifactId>
    <version>7.12.0</version>
    <scope>test</scope>
</dependency>

**Paste** it in pom.xml
inside </depndencies>
----


## **Help**- eclipse marketplace - search - testNG and go button install(already)

project setup completed - imp for exam
-----

# Code:- 
### Task 1 how to launch application in 3 different browsers: chrome, firefox, edge

src/test/java - make a package(webdriverscripts) - make a class(launchbrowsers)

in the class:-

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
class{
	static WebDriver driver;
		(hover on WebDriver and click on import org.openqa.selenium.WebDriver;)
	public static void Chromebroswer(){

	driver = new ChromeDriver();
			(hover on ChromeDriver and click on import)
	driver.get("url link here");
	driver.manage.().window().maximize();
	driver.close();

in main{

Chromebrowser()
----

# **Selenium WebDriver:**



public class LaunchBrowsers {



static WebDriver driver;



// method for implementing launching the chrome browser



public static void Chromebrowser() {



driver new ChromeDriver();



driver.get("https://demowebshop.tricentis.com/");



driver.manage().window().maximize();



}



public static void firefox() {



driver=new FirefoxDriver();



driver.manage().window().maximize();



driver.get("https://www.facebook.com");



}

public static void Edge() {



driver = new EdgeDriver();



driver.manage().window().maximize();



driver.get("https://www.google.com");



}



public static void Browsernavigation() throws InterruptedException {



Chromebrowser();



Thread.sleep(3000);



driver.get("https://google.com");



Thread.sleep(3000);



driver.navigate().back();



Thread.sleep(3000);



driver.navigate().forward();



Thread.sleep(3000);



driver.navigate().refresh();



Thread.sleep(3000);



driver.quit();

}



public static void main(String\[] args) throws InterruptedException {



// TODO Auto-generated method stub



Chromebrowser();



firefox();



Edge();



Browsernavigation();



}



}





### **Task 2:create the test script for demo webshop application register page**



create new class = Demowebshopregister

Locators:

link =



**answer1**

package webdriverscripts;



import org.openqa.selenium. By;



import org.openqa.selenium.WebDriver;



import org.openqa.selenium.chrome.ChromeDriver;



public class Demowebshopregister (



static WebDriver driver;



public static void Launchbrowser() {



driverenew ChromeDriver();



driver.manage().window().maximize();



driver.get("https://demowebshop.tricentis.com/");



}



public static void Registerpage() {



driver.findElement(By.LinkText("Register")).click();



driver.findElement(By.id("gender-male")).click();



driver.findElement(By.name("FirstName")).sendKeys("Michael");



driver.findElement(By.name("LastName")).sendKeys("Hendry");



driver.findElement(By.id("Email")).sendKeys("nicheal.hendry3278@gmail.com");



driver.findElement(By.name("Password")).sendKeys("Mercury@123");



driver.findElement(By.name("Confirm Password")).sendKeys("Mercury@123");



driver.findElement(By.id("register-button")).click();



driver.findElement(By.LinkText("Log out")).click();



}



**answer2**



package webdriverscripts;



import org.openqa.selenium.By;

import org.openqa.selenium.WebDriver;

import org.openqa.selenium.chrome.ChromeDriver;



public class TestmeApp {

&#x09;

&#x09;static WebDriver driver;

&#x09;public static void LaunchBrowser() {

&#x09;	driver = new ChromeDriver();

&#x09;	driver.manage().window().maximize();

&#x09;	driver.get("https://lkmdemoaut.accenture.com/TestMeApp/login.htm");

&#x09;}

&#x09;public static void Registerpage() throws InterruptedException {

&#x09;	driver.findElement(By.linkText("New User?Register Here")).click();

&#x09;	driver.findElement(By.name("userName")).sendKeys("ram1233");

&#x09;	driver.findElement(By.name("firstName")).sendKeys("Ram");

&#x09;	driver.findElement(By.name("lastName")).sendKeys("Sharma");

&#x09;	driver.findElement(By.name("password")).sendKeys("Value123");

&#x09;	driver.findElement(By.name("confirmPassword")).sendKeys("Value123");

&#x09;	driver.findElement(By.xpath("//\*\[@value='Male']")).click();

&#x09;	driver.findElement(By.id("emailAddress")).sendKeys("ram1245@gmail.com");

&#x09;	driver.findElement(By.id("mobileNumber")).sendKeys("7854093513");

&#x09;	driver.findElement(By.name("dob")).sendKeys("03/26/2026");

&#x09;	driver.findElement(By.name("address")).sendKeys("Ram Nagar,Sodala");

&#x09;	Thread.sleep(3000);

&#x09;	driver.findElement(By.xpath("//\*\[@value='Register']")).click();

&#x09;

&#x09;}



&#x09;public static void main(String\[] args) throws InterruptedException {

&#x09;	LaunchBrowser();

&#x09;	Registerpage();



&#x09;}



}



## **Syntax(for web driver):**

### **Locators:**



driver.findelement (By.id ("id of the Object"));

driver.findelement (By.Name ("name of the Object");

driver.findelement (By.linkText ("visible text of the link");

driver.findelement (By.partialLinkText ("partial text of the link");

driver.findelement (By.xpath ("xpath of the object");

driver.findelement (By.cssSelector ("css of the object");

driver.findelement (By.className ("className of the object");

driver.findelement (By.tagName ("tagName of the object");



## **Web Driver Browser Commands:**



**1) get (URL);**

Syn:

driver.get (URL);

\--> The above command will open the URL.

**2)driver.manage ().window ().maximize ();** 

\--> The above command will maximize the browser.

**3) driver.navigate ().back ();**

\--> It will move back to browser history.

**4)driver.navigate ().forward();**

\--> It will move forward to browser history and does nothing, if that is the latest browser.

**5)driver.navigate().refresh();** 

\--> It will refresh the current page.

**6) driver.navigate().to(url);**

\--> It will load the new url in current page.

**7)close();**

Syn:

driver.close();

\--> It will close the browser.

**8)quit();** 

driver.quit();

\--> It will close the browser and kill the driver instance.get



## **Web Driver Interaction Commands:**

\--> Before Interacting with browser we need to create a web element object.

&#x20;

### **Syntax:**

&#x20;

WebElement element =driver.findelement (By.locatorname("locator");

\--> From above element we can inherit commands like below\*\*.\*\*



**1)element.clear();**

\--> It will clear the value in edit box.

**2) element.click();**

\--> It will click on clickable elements like Buttons ,

Images , Checkboxes , links and radio buttons etc.

**3)element.sendKeys("Value to be Enter");** 

\--> It will enter the value in to edit box.



## ***Task 3 : How to select option from dropdown ?***





***S***<i>elect select = new Select(driver.findElement(By.loacatorName(locator)));</i>

*****4.1)*** *select.selectByIndex(index);***

*--> It will select options based on Index like 0,1,2 ...*

&#x20;

*****4.2)*** *select.selectByValue(value);***

*--> It will select the option based on value. That is, when given "foo" this would select an option like:*

*<option value="foo">Bar</option>*



***4.3) select.selectByVisibleText(text);***

*--> It will select the option based on text.*

*That is, when given "Bar" this would select an option like?*

*<option value="foo">Bar</option>*



***4.4) select.deselectByIndex(index)***

*--> It will deselect options based on Index like 0,1,2 ...*



***4.5) select.deselectByValue(value);***

*--> It will deselect the option based on value.*

*That is, when given "foo" this would select an option like:*

*<option value="foo">Bar</option>*



**4.6) select.deselectByVisibleText(text);**

*--> It will deselect the option based on text.*

*That is, when given "Bar" this would select an option like:*

*<option value="foo">Bar</option>*



## ***Note:***



### ***Xpath:***



*driver.findElement(By.xpath("//\*\[@aria-label='Create new account']")).click(); //if linktext not work.*



***contains(syntax):***



*//\*\[contains(text(),'Day')]*

*driver.findElement(By.xpath("//\*\[contains(text(),'Day')]"))*



***text(syntax):***



*//\*\[text()='Day']")]*

*driver.findElement(By.xpath("//\*\[text()='Day']"))*

&#x20;



##### ***CODE:***



*package webdriverscripts;*



*import org.openqa.selenium.By;*

*import org.openqa.selenium.WebDriver;*

*import org.openqa.selenium.chrome.ChromeDriver;*

*import org.openqa.selenium.support.ui.Select;*





*public class DropdownScript {*

&#x09;*static WebDriver driver;*

&#x09;

&#x20; *public static void LaunchBrowser() {*

&#x09;  *driver = new ChromeDriver();*

&#x09;  *driver.get("https://demowebshop.tricentis.com/");*

&#x09;  *driver.manage().window().maximize();*

&#x20; *}*

&#x20;

&#x20; *public static void Dropdown() {*

&#x09;  *driver.findElement(By.linkText("Books")).click();*



&#x09;  *Select sortby=new Select(driver.findElement(By.id("products-orderby")));*

&#x09;  *sortby.selectByIndex(0);*



&#x09;  *Select display=new Select(driver.findElement(By.name("products-pagesize")));*

&#x09;  *display.selectByVisibleText("4");*



&#x09;  *Select view = new Select(driver.findElement(By.id("products-viewmode")));*

&#x09;  *view.selectByVisibleText("List");*

&#x20; *}*



&#x09;*public static void main(String\[] args) {*

&#x09;	*// TODO Auto-generated method stub*

&#x09;	*LaunchBrowser();*

&#x09;	*Dropdown();*



&#x09;*}*



*}*



***Count no. of options in dropdown***

***Retrive the each county name in oprtion***

***Create new class - Dropdownoptionscount()***



*package webdriverscripts;*



*import java.time.Duration;*

*import java.util.List;*



*import org.openqa.selenium.By;*

*import org.openqa.selenium.WebDriver;*

*import org.openqa.selenium.WebElement;*

*import org.openqa.selenium.chrome.ChromeDriver;*

*import org.openqa.selenium.support.ui.Select;*



*public class Dropdownoptionscount {*

&#x09;

&#x09;*static WebDriver driver;*

&#x09;*public static void LaunchBrowser() throws InterruptedException {*

&#x09;	*driver= new ChromeDriver();*

&#x09;	*driver.get("https://demo.guru99.com/test/newtours/");*

&#x09;	*driver.manage().window().maximize();*

&#x09;	*driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(40));*

&#x09;	*Thread.sleep(3000);*

&#x09;	*driver.findElement(By.linkText("REGISTER")).click();*

&#x09;	*Thread.sleep(2000);*

&#x09;	*Select country=new Select(driver.findElement(By.name("country")));*

&#x09;	*// Count no of options in dropdown*

&#x09;	*List<WebElement> optioncount= country.getOptions();*

&#x09;	*System.out.println("No. of options in dropdown are = "+optioncount.size());*

&#x09;	

&#x09;	*//retrieve the each country name*



&#x09;	*for(int i=0; i<optioncount.size();i++) {*

&#x09;		*WebElement countryname=optioncount.get(i);*

&#x09;		*System.out.println("Country "+ (i+1)+ ":" +countryname.getText());*

&#x09;		*if(countryname.getText().equalsIgnoreCase("India")) {*

&#x09;			*countryname.click();*

&#x09;		*}*

&#x09;	*}*

&#x09;*}*

&#x09;



&#x09;*public static void main(String\[] args) throws InterruptedException {*

&#x09;	*// TODO Auto-generated method stub*

&#x09;	*LaunchBrowser();*



&#x09;*}*

*}*



### XPATH Concept in Selenium:

### ===========================

*ID,NAME,CLASSNAME,LINKTXT,PARITALLINKTEXT*

&#x20;

*XPATH is a element locator to identify the application objects during run time.*



***how to go to abosolute xpath go to particular thing(like:Login) ->**

 inspect -> right-click on particular line->click copy->copy xpath*



&#x20;

##### **Two types of xpath in selenium:**

*===============================*

&#x20;

###### ***Absolute xpath:***

###### &#x20;

*The absolute xpath it starts from root element.*

*The absolute xpath it starts with single slash(/)*

&#x20;

*eg: xpath= /html/body/center/form/div/table\[2]/tbody/tr\[3]/td\[3]/input*

&#x20;

*driver.findElement(By.xpath("/html/body/center/form/div/table\[2]/tbody/tr\[3]/td\[3]/input")).click();*

&#x20;

*/html/body/div\[4]/div\[1]/div\[4]/div\[2]/div/div\[2]/div\[1]/div\[2]/div\[2]/form/div\[5]/input*

&#x20;

*/html/body/div\[4]/div\[1]/div\[4]/div\[2]/div/div\[2]/div\[1]/div\[2]/div\[2]/form/div\[5]/input*

&#x20;

&#x20;

###### ***Relative xpath:***

&#x20;

*The relative xpath it starts from current node.*

*The relative xpath it starts with double slash(//)*

&#x20;

*xpath=//\*\[@id="country"]*

&#x20;

*driver.findElement(By.xpath("//\*\[@id="country"]")).sendkeys();*

&#x20;

&#x20;

*xpath=//\*\[@name='Email']*

&#x20;

*driver.findElement(By.xpath("//\*\[@name='Email']")).sendkeys();*

&#x20;

*==========================================================================================================================*

&#x20;

###### ***Types of xpath Methods:***

*========================*

*1)single attribute method*

*2)Multiple attribute method*

*3)xpath using Boolean attribute method*

*4)contains method*

*5)Text method*

*6)starts-with method*

*7)following method*

&#x20;

&#x20;

***1) Single attribute method:***

*============================*

&#x20;

***syntax:***
&#x20;

&#x20;     *xpath=//\*\[@attributename='value']*

&#x20;

&#x20;        *name=txtUsername*

&#x20;

&#x20;    *xpath=//\*\[@name='txtUsername']*

&#x20;

&#x20;  *driver.findElement(By.xpath("//\*\[@name='txtUsername']")).sendkeys("Admin");*

&#x20;

&#x20;

***2)Multiple attribute method:***

&#x20;

&#x20;***syntax:***

&#x20;

&#x20;   *xpath=//\*\[@attributename='value']\[@attributename='value']*

&#x20;

&#x20;     *name='txtPassword'*

&#x20;      *id='txtPassword'*

&#x20;

&#x20;  *xpath=//\*\[@name='txtPassword']\[@id='txtPassword']*

&#x20;

&#x20;

&#x20; *driver.findElement(By.xpath("//\*\[@name='txtPassword']\[@id='txtPassword']")).sendkeys("admin123");*

&#x20;

&#x20;

***3) xpath using Boolean operator :***
&#x20;

&#x20;  *syntax:*

&#x20;

&#x20;   *xpath=//\*\[@attributename='value' or @attributename='value']*

&#x20;

&#x20;       *//\*\[@name='txtPassword' or @id='txtPassword']*

&#x20;

&#x20;

***4)contains Method :***

*==================*

&#x20;

*syntax:*

&#x20;

*xpath=//\*\[contains(@attributename,'value')]*

&#x20;

&#x20; *name='Submit'*

&#x20;

&#x20; *xpath=//\*\[contains(@name,'Submit')]*

&#x20;

&#x20;  *driver.findElement(By.xpath("//\*\[contains(@name,'Submit')]")).click();*

&#x20;

&#x20;

***5)Text Method :***

*==============*

&#x20;

***Syntax:***

&#x20;

*xpath=//\*\[text()='value']*

&#x20;

*text=Forgot your password?*

&#x20;

*xpath=//\*\[text()='Forgot your password?']*

&#x20;

*driver.findElement(By.xpath("Forgot your password?")).click();*

&#x20;

&#x20;

***6) starts-with Method :***

*=======================*

&#x20;

***syntax:***

&#x20;

*xpath=//\*\[starts-with(@attributename,'value')]*

&#x20;

&#x20;

*name='DOB\_Day60f2e907'*

*name='DOB\_Dayed959e74'*

*name='DOB\_Daya21763ea'*

&#x20;

*xpath=//\*\[starts-with(@name,'DOB\_Day')]*

&#x20;

*driver.findElement(By.xpath("//\*\[starts-with(@name,'DOB\_Day')]")).click();*

&#x20;

&#x20;

*7)Following Method:*

*====================*

&#x20;

*Syntax:*

&#x20;

*xpath=//\*\[@attributename='value']//following::a\[@attributename='value']*

&#x20;

*value='Select Destination'*

&#x20;

*text='Bengaluru'*

&#x20;

*xpath=//\*\[@value='Select Destination']//following::a\[text()='Bengaluru']*

&#x20;

*driver.findElement(By.xpath("//\*\[@value='Select Destination']//following::a\[text()='Bengaluru']")).click();*


# 
###### ***USE OF DIFFERENT Xpaths(Snippet):***



*driver.findElement(By.xpath("/html/body/div\[4]/div\[1]/div\[5]/div\[2]/div/div\[2]/div\[1]/div\[2]/div\[2]/form/div\[5]/input")).click();*

&#x09;

&#x09;  *driver.findElement(By.xpath("//\*\[@name='Email']")).sendKeys("admin@gmail.com");*

&#x09;

&#x09;    	*// type = submit*

&#x09;

&#x09;  *driver.findElement(By.xpath("//\*\[@type='submit']")).click();*

&#x09;

&#x09;

&#x09;       *// value='Login'*

&#x09;

&#x09;  *driver.findElement(By.xpath("//\*\[@vlaue='Login']")).click();*

&#x09;

&#x09;     *// value='Google Search' name='btnK' -- NAME VALUE IS CHANGE btnG*

&#x09;

&#x09;  *driver.findElement(By.xpath("//\*\[@value='Google Search']\[@name='btnK']")).click(); // no use*

&#x09;

&#x09;    *// xpath using boolen operator*

&#x09;

&#x09;  *driver.findElement(By.xpath("//\*\[@value='Google Search' OR @name='btnK' OR @type='submit']")).click();*

&#x09;

&#x09;    *// contains method -- href -- links*

&#x09;

&#x09;    *// xpath=//\*\[contains(@href,'https://mail.google.com/mail/?authuser=0\&ogbl')]*

&#x09;

&#x09;    *driver.findElement(By.xpath("//\*\[contains(@href,'https://mail.google.com/mail/?authuser=0\&ogbl')]")).click();*

&#x09;

&#x09;      *//text='Wait...'*

&#x09;

&#x09;    *// xpath=//\*\[contains(text(),'Wait...')]*

&#x09;

&#x09;    *driver.findElement(By.xpath("//\*\[contains(text(),'Wait...')]")).click();*

&#x09;

&#x09;

&#x09;    *// value='Login'*

&#x09;

&#x09;        *// xpath=//\*\[contains(@value,'Login')]*

&#x09;

&#x09;

&#x09;

&#x09;    */\**

&#x09;     *\* Text Method*

*==============*

&#x20;

*Syntax:*

&#x20;

*xpath=//\*\[text()='value']*

&#x20;

*text=Forgot your password?*

&#x20;

*xpath=//\*\[text()='Forgot your password?']*

&#x20;

*driver.findElement(By.xpath("Forgot your password?")).click();*

&#x09;     *\*/*

&#x09;

&#x09;*// starts method*

&#x09;

&#x09;    *// DOB\_Dayecfe60cc  DOB\_Monthecfe60cc DOB\_Yearecfe60cc*

&#x09;

&#x09;    *driver.findElement(By.name("DOB\_Dayecfe60cc")).click();*

&#x09;

&#x09;    *// name= DOB\_Dayde847413  DOB\_Dayf587ec92*

&#x09;

&#x09;    *// syntax: xpath=//\*\[starts-with(@attributename,'value')]*

&#x09;

&#x09;    *// xpath=//\*\[starts-with(@name,'DOB\_Day')]*

&#x09;

&#x09;    *driver.findElement(By.xpath("//\*\[starts-with(@name,'DOB\_Day')]")).click();*

&#x09;

&#x09;

&#x09;  *// following method*

&#x09;

&#x09;    */\*     customer login mod                               Banker login module*

&#x09;     *\**

&#x09;     *\*    userid:                                              bankerid:*

&#x09;     *\*    password:                                            bankerpwd:*

&#x09;     *\**

&#x09;     *\*            signin  cancel                                           signin      cancel*

&#x09;     *\**

&#x09;     *\*  name='signin*

&#x09;     *\**

&#x09;     *\**

&#x09;     *\*/*

&#x09;

&#x09;         *driver.findElement(By.name("signin")).click();*

&#x09;

&#x09;       *// value='Select Destination' text='Goa'*

&#x09;

&#x09;      *// xpath=//\*\[@value='Select Destination']//following::div\[text()='Goa']*

&#x09;

&#x09;    	*driver.findElement(By.xpath("//\*\[@value='Select Destination']//following::div\[text()='Goa']")).click();*

&#x09;

&#x09;

&#x09;    *}*



##### ***SHORT NOTES:***



*xpath ?? only for links and text - its ideal for that*

*inspect - right click on highlighted part - copy - u can copy relative xpath from there*



**# ## *2 types of xpath :***


***absolute** - it what have tags from thr root(html/body......)*


***In relative we have:***

**Single atteribute** - this is shorter //\*\[@id ='name']*

**Multiple attribute method** - //\[@value='xyz']\[@name='xyz'], we can use or also - //\[@value='xyz' OR @name='xyz']*

*if we wanna click on the visible text or for a link have u use contains- //\[contains(@href,'link here')] , //(contains(text(),'text here')* 

*can also click on text like this - //\*(text()=' text here')*



*we can use contains with id,name too*



***start-with method** - as there is dynamic scripting we have to use starts with so we can access the static part of an id and use to locate the field*

*eg DOB\_Dayasdasd, DOB\_Dayihnas ..........*




**Example for Xpath:**

public static void Launchbrowser() {

driver new ChromeDriver():

driver.get("https://www.advantageonlineshopping.com/#/register");

driver.manage().window().maximize():

driver.manage().timeouts().implicitlyWait (Duration.ofSeconds(10));
}

public static void locatorsapp() throws InterruptedException (

driver.findElement(By.xpath("//*[@name='username RegisterPage']")).sendKeys("Sanskrut1234");

driver.findElement(By.xpath("//*[@name'emailRegisterPage']")).sendKeys("saner34@gmail.com");

Thread.sleep(2000): driver.findElement(By.xpath("//*[name='passwordRegisterPage']")).sendKeys("San1234");

driver.findElement(By.xpath("//*[@name 'confirm passwordRegisterPage']")).sendKeys("San1234");

Thread.sleep (2000);
driver.findElement(By.xpath("//*[@name="first nameRegisterPage']")).sendKeys("Divya");

driver.findElement(By.xpath("//*[@name='last nameRegisterPage']")).sendKeys ("Sahoo"):

Thread.sleep (2000);

driver.findElement(By.xpath("//*[@name='phone numberRegisterPage']")).sendKeys("7008913117");

Thread.sleep(2000);

WebElement countryDropdown = driver.findElement(By.name("countryListboxRegisterPage"));

((org.openqa.selenium. JavascriptExecutor) driver).executeScript ("arguments[0].click();", countryDropdown);
Thread.sleep(1000);

WebElement brazil = driver.findElement(By.xpath("//span [contains(text(), 'Brazil')]"));

((org.openqa.selentum, JavascriptExecutor) driver).executeScript("arguments[0].click();", brazil);

Select country=new Select(driver.findElement(By.xpath("//*[@name,'country']"));
 
     country.selectByVisibleText("ARGENTINA")

}

public static void main(String[] args) throws InterruptedException{

Launchbrowser();
Locatorsapp();
}
}

# **CSS Selector concept in Selenium:**
 
- css selector is a element locator in selenium, By using css selector we can identify the application objects during run time.
- css selector is faster then xpath in terms of identifying objects.
 
 
    **attributename**       &             **symbol used**

        id                          #
        classname                   .
        contains                    *
        starts-with                 $
        Ends-with                   ^
        single attribute            tagname[attributename='value']
        Multiple attribute          tagname[atttributename='value'][attributename='value']
 
 
examples for css selector:
 
id='firstname'
 
css=#firstname
 
driver.findElement(By.cssselector('#firstname')).sendkeys("   ");
 
css = #txtUsername
 
driver.findElement(By.cssselector("#txtUsername")).sendkeys("  ");
 
name='txtPassword'
 
css=input[name='txtPassword']
 
driver.findElement(By.cssselector("input[name='txtPassword']").sendkeys("   ");
 
id=txtusername
 
css=input[id*='txtusername']
 
name='DOB_Day3849494'
 
css=input[name$='DOB_Day']
 
id='forgot my password'
id='lost my password'
 
css=input[id^='my password']


# **Wait Commands:**

**1)Implicit**

**2)Explicit** - provide better control **

Explicit code:(for month)

package webdriverscripts;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class Explicitwaitstatement {
	
	static WebDriver driver;
	public static void Dropdown() throws InterruptedException
	{
		driver = new ChromeDriver();
		driver.get("https://www.facebook.com/");
		
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		Thread.sleep(10000);
		
		driver.findElement(By.linkText("Create new account")).click();
		
		
		WebElement month =driver.findElement(By.id("_r_9_"));
		month.click();
		
		//Explicit wait
		 WebDriverWait monthwait = new WebDriverWait(driver,Duration.ofSeconds(5));
		 monthwait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//*[text()='September']")));
		 

		driver.findElement(By.xpath("//*[text()='September']")).click();	
		
	}
	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		Dropdown();

	}

}

**Drawbacks of selenium webdriver:**

detailed test report it wont generate

we cannot perform parallel test execution

we cannot perform batch testing.

# **Testng framework:**

Testng framework -> it will generate detailed test reports

we can perform parallel test execution

we can perform batch testing process.

**Note:** we don't use main method concept in testng framework:

The methods in a class it will execute by using testng annotations.

# ## **Types of testng annotations:**

@Test

@BeforeTest

@AfterTest

@BeforeMethod

@AfterMethod

@Beforeclass

@Afterclass

@Beforesuite

@Aftersuite

@Parameters

@DataProvider



**@Test:** This annotation it will execute a single method in a class:
 
public class ABCD() {
 
   public void 12() {
------------------
------------------
 
}
 
@Test
public void 23() {   --  1
------------------
------------------
}
 
public void 45() {
 
------------------
------------------
 
}
 
 
}
 
**@BeforeTest** : This annotation method it will execute before executing @Test method.
 
 
**@AfterTest** : This Annotation method it will execute after executing @Test method.
 
 
public class ABCD() {
 
@BeforeTest
public void 12() {   -- 1
------------------
------------------
 
}
 
@Test
public void 23() {   --   2
------------------
------------------
}
 
@AfterTest
public void 45() {  -- 3
 
------------------
------------------
 
}
 
===========================================================================================================
 
public class ABCD() {
 
@Test(priority=3)
public void 12() {   -- 4
------------------
------------------
 
}
 
@Test(priority=1)
public void 23() {   --   2
------------------
------------------
}
 
@Test(priority=2
public void 45() {  -- 3
 
------------------
------------------
 
}
 
@Test(priority=0)
public void 56() {  -- 1
 
------------------
------------------
 
}
 
@Test(priority=4)
public void 75() {  -- 5
 
------------------
------------------
 
}
 
}

@BeforeMethod:

TC1: check book functionality

@BeforeMethod
step1: launch browser and enter the url and then login credential
@Test(priority - 0)
step 2 :
click on book link and select the book orders then click on add to cart
@AfterMethod
step3:click on logout


TC2: check search functionality

step 1:launch browser and enter the url and then login credential

@Test(priority = 1)
step 2: check search functionality and add book to add to cart

step 3: click on logout


(You can check testing on website TestNG Documentation)

**task2:
https://lkmdemoaut.accenture.com/AccenSportz/#

TC1:check the functionality Book tickets of accensportz
 
@BeforeMethod
step1: Launch browser
@Test(priority=0)
step2: click on book tickets and buy it then enter the require details
@AfterMethod
step3: close the browser
 
TC2: Check the functionality of Sportz coaching
 
step1: Launch browser
@Test(priority=1)
step2: click on sportz coaching and enter required details
step3: close the browser
**
Code for this:

package testngscripts;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class AccenSportsTest {
	
	static WebDriver driver;
	
	@BeforeMethod
	public void Chromebrowser() {
		
		driver = new ChromeDriver();
		driver.get("https://lkmdemoaut.accenture.com/AccenSportz/#");
		driver.manage().window().maximize();
		
	}
	@Test(priority = 0)
	public static void BookTickets() throws InterruptedException {
		driver.findElement(By.linkText("Book Tickets")).click();
		driver.findElement(By.xpath("//*[@value = 'India vs Pakistan']")).click();		
		Thread.sleep(2000);

		// enter name
		driver.findElement(By.id("name")).sendKeys("Divya");
		//driver.findElement(By.xpath("//input[@placeholder='name']")).sendKeys("Divya")
		Thread.sleep(2000);

		driver.findElement(By.id("next1")).click();
		Thread.sleep(2000);
		
		// enter phone number
		driver.findElement(By.name("phonenumber")).sendKeys("8595623258");
		Thread.sleep(2000);
		driver.findElement(By.id("next2")).click();
		

		// enter email
		driver.findElement(By.xpath("//input[@placeholder='Ex. john@abc.com']")).sendKeys("divya12@test.com");
		Thread.sleep(2000);
		driver.findElement(By.id("next3")).click();
		
		Thread.sleep(2000);
		// Quantity
		Thread.sleep(4000);
		
		driver.findElement(By.id("mat-select-value-1")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.xpath("//*[text()=' 2 ']")).click();
		Thread.sleep(3000);

		// Submit
		driver.findElement(By.name("submitbutton")).click();


		Thread.sleep(2000);
		//Click OK
		driver.findElement(By.id("okbutton")).click();

		}

		@Test(priority = 1)
		public static void sportzCoachingTest() throws InterruptedException {

		Thread.sleep(2000);
		driver.findElement(By.xpath("//*[contains(@href,'#/widgets/sportscoaching')]")).click();
		Thread.sleep(2000);

		Thread.sleep(2000);
        driver.findElement(By.name("trainingschedulebutton")).click();
        
		// bookslot button
		driver.findElement(By.id("bookslot")).click();
		
		// Select sport
		WebElement sports=  driver.findElement(By.xpath("//*[@placeholder='Select any sport']"));
        sports.click();
        sports.sendKeys("Football");
		Thread.sleep(4000);
		
		driver.findElement(By.id("Date")).sendKeys("10/07/2005");
		Thread.sleep(3000);
 
		driver.findElement(By.id("mat-select-value-1")).click();
		
		Thread.sleep(3000);
		
		driver.findElement(By.xpath("//*[@id=\"mat-option-10\"]/span")).click();
		
		Thread.sleep(5000);
		

		// Submit
		driver.findElement(By.name("submitbutton")).click();

		}

		@AfterMethod
		public static void closeBrowser() {

		driver.quit();

		}


}



package TestNgScripts;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class AccenSportz {
	static WebDriver driver;
@BeforeMethod
	public static void Launch() throws InterruptedException
	{
		driver=new ChromeDriver();
		driver.get("https://lkmdemoaut.accenture.com/AccenSportz/#");
		driver.manage().window().maximize();
		Thread.sleep(3000);
	}
@Test(priority=0) 
	public static void BookTickets() throws InterruptedException
	{
		Thread.sleep(1000);
		driver.findElement(By.name("booktickets")).click();
		driver.findElement(By.xpath("//*[@value='India vs Pakistan']")).click();
		Thread.sleep(1000);
		driver.findElement(By.id("name")).sendKeys("Abhishek");
		driver.findElement(By.id("next1")).click();
		Thread.sleep(1000);
		driver.findElement(By.name("phonenumber")).sendKeys("8789965356");
		driver.findElement(By.id("next2")).click();
		Thread.sleep(1000);
		driver.findElement(By.id("mat-input-2")).sendKeys("Abhishek@gmail.com");
		driver.findElement(By.id("next3")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.xpath("//mat-select")).click();
		Thread.sleep(1000);
		driver.findElement(By.id("mat-option-2")).click();
		Thread.sleep(1000);
		driver.findElement(By.name("submitbutton")).click();
	}
@Test(priority=1)
	public static void sports_coaching() throws InterruptedException{
		{
			driver.findElement(By.className("sportscoaching")).click();
			driver.findElement(By.name("trainingschedulebutton")).click();
			driver.findElement(By.id("bookslot")).click();
			Thread.sleep(1000);
			
			WebElement sports = driver.findElement(By.xpath("//*[@placeholder='Select any sport']"));
			sports.click();
			sports.sendKeys("Football");
			//driver.findElement(By.id("mat-input-8")).click();
			//driver.findElement(By.id("mat-option-32")).sendKeys("Football");
			driver.findElement(By.xpath("//*[@placeholder='Select Slot Date']")).sendKeys("03/31/2026");
			Thread.sleep(3000);
			driver.findElement(By.xpath("//mat-select")).click();
			Thread.sleep(2000);

			driver.findElement(By.xpath("//*[@id=\"mat-option-10\"]/span")).click();
			//driver.findElement(By.xpath("//*[@id=\"mat-option-67\"]/span")).click();
			
			
			Thread.sleep(1000);
			driver.findElement(By.name("submitbutton")).click();
			Thread.sleep(3000);
		}
	}
@AfterMethod
	public static void close() throws InterruptedException
	{
	Thread.sleep(3000);
		driver.quit();
	}
}

**NOTE:**
for creating testing.xml file = Right click on project-testng-convert testng -next-finish

After creating testng.xml file - to run multiple programs together
you add your class name in the file
<class name="package.classname"></class>

Parameters Annotations():This annotation it will read the test data from external xml file.


# **TASK():**
public class ParametersAnnotations {
	
	static WebDriver driver;

	@Parameters({"emailid","password"})
	
	@Test
	public void demoblaze (String emailid, String password) throws InterruptedException {

		driver=new ChromeDriver();
		Thread.sleep(3000);

		driver.get("https://www.demoblaze.com/");

		driver.manage().window().maximize();
		Thread.sleep(4000);
		driver.findElement(By.linkText("Log in")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.id("loginusername")).sendKeys(emailid);
		
		driver.findElement(By.id("loginpassword")).sendKeys(password);
		//copying detailed xpath
		////*[@id="logInModal"]/div/div/div[3]/button[2]
		driver.findElement(By.xpath("//*[@id=\"logInModal\"]/div/div/div[3]/button[2]")).click();
		Thread.sleep(3000);

		String actualemailid = driver.findElement(By.id("nameofuser")).getText();

		System.out.println(actualemailid);

		if(actualemailid.equalsIgnoreCase("Welcome divya1234@gmail.com")) {

		Reporter.log("login successfully into demowaze",true);

		}
		else {
			Reporter.log("Unable to login into demowaze",true);
		}

	}
    
}

**@BeforeClass:** The annotated method will be run before the first test method in the current clays is invoked.

**@AfterClass:** The annotated method will be run after all the test methods in the current class have been run.

Eg. 

public class A {     // parent class
 
@Beforeclass
public void 12() {    // 1
 
----------------
-----------------
 
 
}
 
@AfterClass
public void 34() {
 
------------------
-------------------
 
}
 
 
}
 
public class B extends class A {   // sub class
 
public void 45() {  // 2
---------------
---------------
}
 
public void 65() { // 3
--------------
---------------
}

**Eg:**

A:
Demo
package testngscripts;

import org.testng.annotations.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;

public class DemoExtends extends CommonFun {

    @Test(priority = 0)
    public void Bookfunctionality() throws InterruptedException {

        Thread.sleep(3000);
        driver.findElement(By.xpath("//*[contains(@href,'/books')]")).click();
        Thread.sleep(3000);

        Select sortby = new Select(driver.findElement(By.id("products-orderby")));
        sortby.selectByVisibleText("Price: High to Low");

        Select display = new Select(driver.findElement(By.name("products-pagesize")));
        display.selectByVisibleText("12");

        Select view = new Select(driver.findElement(By.id("products-viewmode")));
        view.selectByVisibleText("List");

        Thread.sleep(3000);

        driver.findElement(By.xpath("//*[@value='Add to cart']")).click();
        

}
    @Test(priority = 1)
    public void Searchfunctionality() throws InterruptedException {

        WebElement searchfield = driver.findElement(By.id("small-searchterms"));

        searchfield.click();
        searchfield.sendKeys("Health Book");
        searchfield.click();

        driver.findElement(By.xpath("//*[@type='submit']")).click();

        Thread.sleep(3000);

        driver.findElement(By.xpath("//*[@value='Add to cart']")).click();
    }
}

B:
CommonFun
package testngscripts;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.edge.EdgeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.testng.Reporter;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Parameters;


public class CommonFun {
	
	static WebDriver driver;
	@Parameters({"Browsername","url","email","password"})

	@BeforeClass
	public static void launch(String Browsername,String url, String email, String password) throws InterruptedException {
		
		if(Browsername.equalsIgnoreCase("chrome")){
			Reporter.log("Launch in "+Browsername,true);
			driver=new ChromeDriver();
			}

		else if(Browsername.equalsIgnoreCase("firefox")){
			Reporter.log("Launch in "+Browsername,true);
			driver=new FirefoxDriver();
			}

		else if(Browsername.equalsIgnoreCase("edge")){
			Reporter.log("Launch in "+Browsername,true);
			driver=new EdgeDriver();
			}
		else {
			Reporter.log("launching in default browser");
			driver=new ChromeDriver();

		}
		driver.get(url);	
		driver.manage().window().maximize();
		driver.findElement(By.linkText("Log in")).click();
		driver.findElement(By.cssSelector("#Email")).sendKeys(email);
		driver.findElement(By.xpath("//*[@type='password']")).sendKeys(password);
		driver.findElement(By.xpath("//*[@value='Log in']")).click();
		
		
}
	@AfterClass
	public void CloseBrowser() throws InterruptedException {

	    Thread.sleep(5000);

	    driver.quit();
	}
}

C:
pom.xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Suite">
  <test thread-count="3" name="Testing demo web app in chrome" parallel="true">
	<parameter name="Browsername" value="chrome"></parameter>
	<parameter name="url" value="https://demowebshop.tricentis.com/"></parameter>
	<parameter name="email" value="harry.potter566@gmail.com"></parameter>
	<parameter name="password" value="Sriyansh@123"></parameter>
	
    <classes>
      <class name="testngscripts.DemoExtends"/>
   
    </classes>
  </test> <!-- Test -->
  
  
    <test thread-count="3" name="Testing demo web app in Edge" parallel="true">
	<parameter name="Browsername" value="Edge"></parameter>
	<parameter name="url" value="https://demowebshop.tricentis.com/"></parameter>
	<parameter name="email" value="harry.potter566@gmail.com"></parameter>
	<parameter name="password" value="Sriyansh@123"></parameter>
	
    <classes>
      <class name="testngscripts.DemoExtends"/>
   
    </classes>
  </test> <!-- Test -->
  
  
      <test thread-count="3" name="Testing demo web app in firefox" parallel="true">
	<parameter name="Browsername" value="firefox"></parameter>
	<parameter name="url" value="https://demowebshop.tricentis.com/"></parameter>
	<parameter name="email" value="harry.potter566@gmail.com"></parameter>
	<parameter name="password" value="Sriyansh@123"></parameter>
	
    <classes>
      <class name="testngscripts.DemoExtends"/>
   
    </classes>
  </test> <!-- Test -->
  
  
</suite> <!-- Suite -->
------


$$
LEVEL OF EXECUTING:

Suite->Test->Class->Method
$$

@BeforeSuite
@AftereSuite


## **@DATAPROVIDER:**

->DataProvider in TestNG allows you to run a test method multiple times with different sets of data. 
->This is useful for data-driven testing, where the same test needs to be executed with different input values to validate various scenarios. 

Ex.

public class DataProviderAnnotations {
	
	static WebDriver driver;
	@Test(dataProvider="logindata")
	public void Orangehrmloginf(String url,String username,String password ) throws InterruptedException {
		
		driver=new ChromeDriver();

		driver.get(url);

		driver.manage().window().maximize();

		Thread.sleep(3000);
		driver.findElement(By.xpath("//*[@placeholder='Username']")).sendKeys("Admin");
		driver.findElement(By.xpath("//*[@type='password']")).sendKeys("admin123");
		Thread.sleep(3000);

		driver.findElement(By.xpath("//*[@type='submit']")).click();
		Thread.sleep(4000);
		
		driver.findElement(By.xpath("//*[text()='Dhari Almutairi']")).click();
		Thread.sleep(5000);

		String actualtext= driver.findElement(By.linkText("Logout")).getText();
		Thread.sleep(4000);
		String expectedtext="Logout";

		Assert.assertEquals (actualtext, expectedtext, "expected text is not matching with actualtext");
	}
	
	@DataProvider(name="logindata")
	public String[][] Getdata() {

		String[][] data=new String[3][3];

		data[0][0]="https://opensource-demo.orangehrmlive.com/web/index.php/auth/login";

		data[0][1]="Admin";

		data[0][2]="admin123";

		data[1][0]="https://opensource-demo.orangehrmlive.com/web/index.php/auth/login";

		data[1][1]="Admin2";

		data[1][2]="admin123";

		data[2][0]="https://opensource-demo.orangehrmlive.com/web/index.php/auth/login";

		data[2][1]="divya";

		data[2][2]="Mercury123";

		return data;

		}


## **CONDITIONAL STATEMENT:
**It will verify whether expected value is matching to actual value.

We can use Assertion in place of conditional statements.

Assertion: It will verify whether the expected value is matching with actual value or not .
 
If expected value is matching with actual value -- Then assert will be pass.
If expected value is not matching with actual value -- assert will be fail.
 
**## Types of Asserts:**
==================
 
**1) Hard Assert:**
 
  In Hard assert if assert is failed then it will terminate the method execution process.

**Ex:**
public class HardAssetAssertion (
	
	static WebDriver driver;
	
	
	@Parameters({"emailid","password"})
	@Test
	public void demoblaze (String emailid, String password) throws InterruptedException {

		driver=new ChromeDriver();
		Thread.sleep(3000);

		driver.get("https://www.demoblaze.com/");

		driver.manage().window().maximize();
		Thread.sleep(4000);
		driver.findElement(By.linkText("Log in")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.id("loginusername")).sendKeys(emailid);
		
		driver.findElement(By.id("loginpassword")).sendKeys(password);
		//copying detailed xpath
		////*[@id="logInModal"]/div/div/div[3]/button[2]
		driver.findElement(By.xpath("//*[@id=\"logInModal\"]/div/div/div[3]/button[2]")).click();
		Thread.sleep(2000);

		String actualemailid = driver.findElement(By.id("nameofuser")).getText();

		System.out.println(actualemailid);
		
		String expectedmailid = "divya1234@gmail.com";
		
		Assert.assertEquals(actualemailid, expectedmailid,"asset value is not matching with actual value");
		driver.findElement(By.linkText("Log out")).click();
		
		}


}

XML FIle:

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Suite">
  <test thread-count="5" name="Testing" parallel="true">
	  <parameter name="emailid" value="divya1234@gmail.com"></parameter>
	  <parameter name="password" value="divya123"></parameter>
    <classes>
      <class name="testngscripts.HardAssetAssertion"/>
      
    </classes>
  </test> <!-- Test -->
</suite> <!-- Suite -->

 
**2) Soft Assert:**
 
  In soft assert if assert is failed then it will continue the method execution process.

**Ex:**
public class SoftAssertAssertion {
	
	
static WebDriver driver;
	
	
	@Parameters({"emailid","password"})
	@Test
	public void demoblaze (String emailid, String password) throws InterruptedException {

		driver=new ChromeDriver();
		Thread.sleep(3000);

		driver.get("https://www.demoblaze.com/");

		driver.manage().window().maximize();
		Thread.sleep(4000);
		driver.findElement(By.linkText("Log in")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.id("loginusername")).sendKeys(emailid);
		
		driver.findElement(By.id("loginpassword")).sendKeys(password);
		//copying detailed xpath
		////*[@id="logInModal"]/div/div/div[3]/button[2]
		driver.findElement(By.xpath("//*[@id=\"logInModal\"]/div/div/div[3]/button[2]")).click();
		Thread.sleep(2000);
		
		SoftAssert obj = new SoftAssert();
		

		String actualemailid = driver.findElement(By.id("nameofuser")).getText();

		System.out.println(actualemailid);
		Thread.sleep(2000);

		
		String expectedmailid = "Welcome divya1234@gmail.com";
		
		obj.assertEquals(actualemailid, expectedmailid,"asset value is not matching with actual value");
		
		Thread.sleep(2000);

		
		driver.findElement(By.linkText("Log out")).click();
		System.out.println("Hello Divya!");
		System.out.println("Done with Soft Assertion!");
		
		obj.assertAll();
	}

}

**XML File:**

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Suite">
  <test thread-count="5" name="Testing" parallel="true">
	  <parameter name="emailid" value="divya1234@gmail.com"></parameter>
	  <parameter name="password" value="divya123"></parameter>
    <classes>
      <class name="testngscripts.SoftAssertAssertion"/>
      
    </classes>
  </test> <!-- Test -->
</suite> <!-- Suite -->



**ACTION:**

To handle the scenario explained in earlier slides, we can use Actions class in Selenium WebDriver

The first step is to create object of an Actions class by passing the WebDriver instance as the argument in Actions constructor
Syntax:

Actions actions = new Actions(driver);

actions.xxxx.xxxx.xxxx.build().perform();

1)build() is required only when there are sequence of actions to be compiled in single step

2)build() is not required when there is only single action

3)perform() is mandatory to execute the actions.


Actions class provide the commonly used methods to handle mouse events as shown below:

# Method Name             Method Description


doubleClick()          Helps to carry out a double-click at the current mouse location or element



clickAndHold()         Press (without releasing) at the current mouse location or element



release()               Releases the depressed left mouse button at the current mouse location or element

contextClick()          Carry out a right-click at the current mouse location or element.


dragAndDrop(source, target)   Carry out press-and-hold at the source element location, shift to the target element location, then release the mouse.

dragAndDropBy(source, x-offset, y-offset)         
Carry out press-and-hold at the source element location, shift to the target offset, then release the mouse.

moveByOffset(x-offset, y-offset)   Moves the mouse from its current position (or 0,0) by the given offset.


moveToElement(toElement)     
Hovers/Shifts the mouse to the center of the element.


**# Automate Keyboard Events:**


Actions class provide the commonly used methods to handle keyboard events as shown below:

# Method Name                Method Description



keyDown(key)            Performs key press on a key from keyboard



keyDown(target, key)    Performs key press after focusing an element and select a key from keyboard



keyUp(key)              Performs key release on a key from keyboard


keyUp(target, key)      Performs key release after focusing an element and select a key from keyboard



sendKeys(on Element, Charsequence) Communicates a series of keystrokes onto the element.

**ex.**

@Test
public void Keyboard() {

driver.get("https://keycode.info"); driver.manage().window().maximize();

Actions obj=new Actions (driver);

obj.sendKeys(Keys.ENTER).build().perform();

obj.pause(Duration.ofSeconds(5));

obj.sendKeys(Keys.TAB).build().perform();

obj.pause(Duration.ofSeconds(5));

obj.sendKeys (Keys.BACK_SPACE).build().perform();

obj.pause(Duration.ofSeconds(5));

obj.sendKeys (Keys.Grond Keys.CONTROL, "a"));


**ex.**

@Test
	public void keybaord() {
		
		Actions act = new Actions(driver);
		act.sendKeys(Keys.ENTER).build().perform();
		act.pause(Duration.ofSeconds(4));
		 
		driver.findElement(By.id("APjFqb")).sendKeys("Keystroke");
		act.sendKeys(Keys.ARROW_DOWN).build().perform();
		act.pause(Duration.ofSeconds(4));
		
		act.sendKeys(Keys.ARROW_UP).build().perform();
		act.pause(Duration.ofSeconds(4));
		
		act.sendKeys (Keys.chord (Keys.CONTROL,"a")).build().perform();
	    act.pause (Duration.ofSeconds(5));
	    
	    act.sendKeys(Keys.ENTER).build().perform();
		act.pause(Duration.ofSeconds(4));
		
		for(int i = 0;i<=4;i++) {
			
			act.sendKeys(Keys.ARROW_DOWN).build().perform();
			act.pause(Duration.ofSeconds(4));
			
		}
		
		act.sendKeys(Keys.ENTER).build().perform();
		act.pause(Duration.ofSeconds(4));
		
		
		


		act.sendKeys (Keys.BACK_SPACE).build().perform();
		act.pause(Duration.ofSeconds(5));
		
		act.sendKeys(Keys.chord(Keys.SHIFT, "r")).build().perform();
		act.pause (Duration.ofSeconds(5));
		
	}


# **CAPTURE SCREENSHOT:**

**1) If Passed:**
Ex.
public class CaptureScreenshot_passed extends CommonfunctionClass{
	@Test
	public void Orangehrmlogin() throws InterruptedException, IOException {
		Thread.sleep(3000);
		driver.findElement(By.xpath("//*[@placeholder='Username']")).sendKeys("Admin");
		driver.findElement(By.xpath("//*[@type='password']")).sendKeys("admin123");
		Thread.sleep(3000);
		
		driver.findElement(By.xpath("//*[@type='submit']")).click();
		Thread.sleep(3000);
		
		String actualurl= driver.getCurrentUrl();
		Reporter.log("The URL of page is ="+actualurl);
		
		String expectedurl="https://opensource-demo.orangehrmlive.com/web/index.php/dashboard/index";
		
		Assert.assertEquals(actualurl,expectedurl,"expectedurl is not matching with actualurl");
		System.out.println("Passed");
		
		//Capture ss of application
		
		TakesScreenshot obj= (TakesScreenshot)driver;
		
		File Source= obj.getScreenshotAs(OutputType.FILE);
		
		Files.copy(Source,new File("C:\\Users\\lkmuser\\Desktop\\Selenium Project\\WebDriver\\Screenshots//accb.png"));
		
		driver.findElement(By.xpath("//*[text()='Test2 user']")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.linkText("Logout")).click();
	}



**2) If Failed:**

Ex.

public class CaptureScreenshot_Failed extends CommonfunctionClass {
    @Test
	public void Orangehrmloginf() throws InterruptedException {

		Thread.sleep(3000);
		driver.findElement(By.xpath("//*[@placeholder='Username']")).sendKeys("Admin");
		driver.findElement(By.xpath("//*[@type='password']")).sendKeys("admin123");
		Thread.sleep(3000);

		driver.findElement(By.xpath("//*[@type='submit']")).click();
		Thread.sleep(3000);

		SoftAssert obj = new SoftAssert();

		String actualurl = driver.getCurrentUrl();

		Reporter.log("The URL of page is =" + actualurl);

		String expectedurl = "https://opensource-demo.orangehrmlive.com/web/index.php/dashboard/index123";

		obj.assertEquals(actualurl, expectedurl, "expectedurl is not matching with actualurl");

		driver.findElement(By.xpath("//*[text()='manda user']")).click();
		Thread.sleep(3000);

		driver.findElement(By.linkText("Logout")).click();

		obj.assertAll();

	}

	@AfterMethod
	public void Screenshot(ITestResult result) {
		try {

			if (ITestResult.FAILURE == result.getStatus()) {
				TakesScreenshot obj = (TakesScreenshot) driver;

				File Source = obj.getScreenshotAs(OutputType.FILE);

				Files.copy(Source.toPath(), new File("C:\\Users\\lkmuser\\Desktop\\Selenium Project\\WebDriver\\Screenshots\\aphb.png").toPath());
			}
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
	}

**# Commonfunction Class:**

public class CommonfunctionClass {
	
			
			static WebDriver driver;
			@Parameters({"Browsername","url"})

			@BeforeClass
			public void launch(String Browsername,String url) throws InterruptedException {
				
				if(Browsername.equalsIgnoreCase("chrome")) {
					Reporter.log("Launch in "+Browsername,true);
					driver=new ChromeDriver();
					}

				else if(Browsername.equalsIgnoreCase("firefox")){
					Reporter.log("Launch in "+Browsername,true);
					driver=new FirefoxDriver();
					}

				else if(Browsername.equalsIgnoreCase("edge")){
					Reporter.log("Launch in "+Browsername,true);
					driver=new EdgeDriver();
					}
				else {
					Reporter.log("launching in default browser");
					driver=new ChromeDriver();

				}
				driver.get(url);	
				driver.manage().window().maximize();
				/*
				driver.findElement(By.linkText("Log in")).click();
				driver.findElement(By.cssSelector("#Email")).sendKeys(email);
				driver.findElement(By.xpath("//*[@type='password']")).sendKeys(password);
				driver.findElement(By.xpath("//*[@value='Log in']")).click();*/
				
				
		}
			//@AfterClass
			public void CloseBrowser() throws InterruptedException {

			    Thread.sleep(5000);

			    driver.quit();
			}
			{

		/*driver=new ChromeDriver();
		Thread.sleep(3000);

		driver.get("https://www.demoblaze.com/");

		driver.manage().window().maximize();
		Thread.sleep(4000);
		driver.findElement(By.linkText("Log in")).click();
		Thread.sleep(3000);
		
		driver.findElement(By.id("loginusername")).sendKeys(emailid);
		
		driver.findElement(By.id("loginpassword")).sendKeys(password);
		//copying detailed xpath
		////*[@id="logInModal"]/div/div/div[3]/button[2]
		driver.findElement(By.xpath("//*[@id=\"logInModal\"]/div/div/div[3]/button[2]")).click();
		Thread.sleep(3000); */
	}


**Working with Frames:**
 
--> We can switch between frames by using below commands.
 
1)driver.switchTo().frame(index);
 
--> Index means, if we have 3 frames in a page to identify those frames 
   index will be - 0,1,2 .
 
2)driver.switchTo().frame(nameOrId);
 
--> Name property or ID property of the frame . Name is the suggested one .
 
3)driver.switchTo().frame(frameElement);
 
syntax:
 
Webelement element =driver.findelement(By.name("locator");
 
   driver.switchTo().frame(element);
 
4)driver.switchTo().frame("frameName.0.child");
 
--> For selecting subframes , we can use above command.
 
--> here framename is mainframe and child is the subframe name.
 
 
5)driver.switchTo().defaultContent();
 
--> To come out of that frame , we can use above command.



**Ex.**

public class HandlingFrames extends CommonfunctionClass {
	@Test
	public void FrameMethod() throws InterruptedException {

		// count no of frames in web page

		List<WebElement> frames= driver.findElements (By.tagName("iframe"));

		int framecount=frames.size();

		System.out.println("no of frames in web page is="+framecount);

		for(int i=0;i<framecount;i++) {
			
			String framename = frames.get(i).getAttribute("class");

			System.out.println("name of frame is="+framename);
		}
		
		Thread.sleep(3000);
	;
		
		// driver.switchTo().frame("packageListFrame");

		//driver.findElement(By.linkText("java.awt.color")).click();

		//driver.switchTo().defaultContent();

	}


**HANDLING ALERTS:

Types of Alerts:**

1). Simple Alert
2). Confirmation Alert
3). Prompt alert
 
**Syntax:**
 
Alert alert=driver.switchTo().alert();
 
1)alert.accept();
 
-> It will accept the alert.
 
2)alert.getText();
 
-> It will get the text from alerts.
 
syntax:
 
String alertMessage=alert.getText();
 
System.out.println(alertMessage);
 
3)alert.dismiss();	
 
-> It will dismiss the alert.
 
4)alert.sendkeys("enter text");
 
-> It will enter text into Prompt.

**Ex.** 

public class HandlingAlerts extends CommonfunctionClass {
		
	
    @Test(priority=0)
	public void confalertmethod() throws InterruptedException, IOException {
    	
    	
    	driver.findElement(By.xpath("//*[contains(@href,'#/actions/playerandteamstrategy')]")).click();
		Thread.sleep(3000);

		WebElement league = driver.findElement(By.linkText("Premier League"));
		Actions ob = new Actions(driver);

		ob.moveToElement(league).build().perform();
		Thread.sleep(3000);

		Thread.sleep(1000);

		driver.findElement(By.name("chelsea")).click();

		Thread.sleep(4000);

		if (IsAlertpresent1()) {

			Reporter.log("confirmation alert is present in application", true);

			Alert confrmalert = driver.switchTo().alert();

			String altmessage = confrmalert.getText();

			Reporter.log(altmessage);

			Thread.sleep(3000);
			confrmalert.accept();
		}

		else {

			Reporter.log("No Confirmation Alert Present", true);

		}
		
		TakesScreenshot obj= (TakesScreenshot)driver;
		
		File Source= obj.getScreenshotAs(OutputType.FILE);
		
		Files.copy(Source,new File("C:\\Users\\lkmuser\\Desktop\\Selenium Project\\WebDriver\\Screenshots//accb.png"));
		
	}
	
		//implementing the method for IsAlertpresent()
        @Test(priority=1)
		public boolean IsAlertpresent1() {

			try {
				driver.switchTo().alert();
				return true;
			}
			catch(NoAlertPresentException e){

				e.printStackTrace();
				return false;

			}
		}
	

**VALIDATION COMMANDS:**

--> validation commands will return boolean values . That is, true or false.
 
Webelement element= driver.findElement(By.name("q"));
 
 
1)element.isDisplayed();
 
--> It will verify whether that element exists or not and return true or false.
 
syn:
 
if( element.isDispalyed()){
 
  ------
  ------  statements
  ------ 
  ------
}
 
else{
 
  ---- do something
 
}
 
 
2) element.isEnabled();
 
--> It will verify whether that edit box enabled or not and return true or false.
 
 
syn:
 
if(element.isEnabled()){
 
  ------
  ------  statements
  ------ 
  ------
}
 
else{
 
  ---- do something
 
}
 
3)element.isSelected();
 
--> It will verify whether checkboxes, options in a select and radio buttons selected
or not and return true or false.
syn:
 
if(element.isSelected()){
 
  ------
  ------  statements
  ------ 
  ------
}
 
else{
 
  ---- do something
 
}
 
4)Select select = new Select(driver.findElement(By.loacatorName(locator)));
4.1) select.isMultiple();
 
--> It will verify whether that dropdown is enabled for
multiple selection or not and return true or false.
syn:
 
if(select.isMultiple()){
 
  ------
  ------  statements
  ------ 
  ------
}
 
else{
 
  ---- do something
 
}


**FILE UPLOADING:
**
	

**1)SINGLE FILE UPLOADING ->**

public class Singlefileuploading extends Commonfunctionclass {

@Test

Run | Debug

public void singlefile() {

WebElement file=driver.findElement(By.id("singleFileInput"));

file.sendKeys("C:\\Users\\ganesh.gajula\\OneDrive Accenture\\Desktop\\Attendence report.txt");

WebElement button=driver.findElement(By.xpath("//*[@type='submit']"));

if(button.isEnabled()) {

driver.findElement(By.xpath("//*[@type='submit']")).click();

Reporter.Log("file uploaded successfully", true);

}

else {

Reporter.Log("upload file button is disabled mode", true);

}

}

**2)MULTIPLE FILE UPLOADING:**

public class Multiplefilesuploading extends Commonfunctionclass{

@Test

Run Debug

public void Multiplefile() {

WebElement multiplefile= driver.findElement(By.id("multipleFilesInput"));

String file1="C:\\Users\\ganesh.gajula\\OneDrive Accenture\\Desktop\\Attendence report.txt";

String file2="C:\\Users\\ganesh.gajula\\OneDrive Accenture\\Desktop\\BDD Approch-Cucumber.txt";

multiplefile.sendKeys(file1 +"\n" +file2);

WebElement button=driver.findElement(By.xpath("//*[text()='Upload Multiple Files']"));

if(button.isEnabled()) {

}

driver.findElement(By.xpath("//*[text()='Upload Multiple Files']")).click();

Reporter.Log("file uploaded successfully", true);

else {
Reporter.Log("UPLOAD MODE IS DISABLED", true);
     }
}


APACHE POI

Add two dependencies from Maven depositary->search bar (Apache POi)->click on first link ->
scroll down ->copy the code


<!-- Source: https://mvnrepository.com/artifact/org.apache.poi/poi -->
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi</artifactId>
    <version>5.5.1</version>
    <scope>compile</scope>
</dependency>

<!-- Source: https://mvnrepository.com/artifact/org.apache.poi/poi-ooxml -->
<dependency>
<groupId>org.apache.poi</groupId>
<artifactId>poi-ooxml</artifactId>
<version>5.5.1</version>
<scope>compile</scope>
</dependency>


Ex.(reading data from excel file)

public class Datadriventesting_ApachePoi {
	
	static WebDriver driver;
	
	public void Demowebshopregister() throws IOException {

		File f = new File("C:\\Users\\Desktop\\testdata123.xlsx");

		FileInputStream fis=new FileInputStream(f);

		XSSFWorkbook wb= new XSSFWorkbook(fis);

		XSSFSheet ws = wb.getSheet("Sheet1");

		int rows_count = ws.getPhysicalNumberOfRows();

		Reporter.log("no of rows in excel sheet is="+rows_count,true);

		int cols_count = ws.getRow(0).getPhysicalNumberOfCells();

		Reporter.log("no of colums in excel sheet is="+cols_count,true);
		
		for(int i=1;i<rows_count;i++) {

			String firstname = ws.getRow(i).getCell(0).getStringCellValue();
			String lastname = ws.getRow(i).getCell(1).getStringCellValue();

			String emailid=ws.getRow(i).getCell(2).getStringCellValue(); 
			String pwd=ws.getRow(i).getCell(3).getStringCellValue();

			String cpwd=ws.getRow(i).getCell(4).getStringCellValue();

			driver = new ChromeDriver();

			driver.get("https://demowebshop.tricentis.com/");

			driver.manage().window().maximize();

			driver.findElement(By.linkText("Register")).click();
			
			driver.findElement(By.cssSelector("#gender-male")).click();

			driver.findElement(By.id("FirstName")).sendKeys(firstname);

			driver.findElement(By.name("LastName")).sendKeys(lastname);

			driver.findElement(By.id("Email")).sendKeys(emailid);

			driver.findElement(By.name("Password")).sendKeys(pwd);

			driver.findElement(By.name("Confirm Password")).sendKeys(cpwd);

			driver.findElement(By.name("register-button")).click();
		}
	}


HOW TO HANDLE DIFFERENT WINDOWS(WINDOWS HANDLING):


--> Windows are two types
 
1) Static windows:
 
--> Name of the window will be always constant.
 
driver.switchTo().window("nameOrHandle")
 
 
Switch the focus to the window with the given name/handle.
 
ex:
 
driver.switchTo().window("Login");
 
2) Dynamic windows:
 
--> Name of the windows will change dynamically,means everytime 
when we load page name will change like
 
fisrstTime:name=login123 
SecoundTime:name=login0987
 
--> To overcome such situations , we can use below concept
 
getWindowHandles();
 
syn:
 
set<String> pageHandles=driver.getWindowHandles();
 
--> It will return handles of all opened windows.
 
for(String a:all_windows)
 
for(int i=1;i<=count;i++)
 
 
--> If we wants to come back to main window , we can use below command.
 
driver.switchTo().defaultContent();


EX:

public class HandlingWindows {
	
	
	static WebDriver driver;
	@Test
	public void multipletabs() throws InterruptedException {
		
		driver = new ChromeDriver();
		driver.get("https://opensource-demo.orangehrmlive.com/");
		driver.manage().window().maximize();
		Thread.sleep(3000);
		
		driver.findElement(By.xpath("//*[text()='OrangeHRM, Inc']")).click();
		Thread.sleep(3000);
		
		switchtotab(1);		
		System.out.println("Title of 2nd Tab is"+driver.getTitle());
		Thread.sleep(4000);
		driver.findElement(By.xpath("//*[text()='Contact Sales']")).click();
		
		switchtotab(0);
		System.out.println("Title of 1st Tab is"+driver.getTitle());
		Thread.sleep(3000);
		driver.findElement(By.xpath("//*[@placeholder='Username']")).sendKeys("Admin");
		driver.findElement(By.xpath("//*[@type='password']")).sendKeys("admin123");
		Thread.sleep(3000);
		driver.findElement(By.xpath("//*[@type='submit']")).click();
		Thread.sleep(4000);
		
		switchtotab(1);
		System.out.println("Title of 2nd Tab is"+driver.getTitle());
		Thread.sleep(3000);

		driver.findElement(By.xpath("//*[text()='Contact Sales']")).click();
		driver.findElement(By.id("Form_getForm_FullName")).sendKeys("John Doe");
		driver.findElement(By.id("Form_getForm_Email")).sendKeys("doe.john12@gmail.com");
		Thread.sleep(3000);
	
		switchtotab(0);
		System.out.println("Title of 1st Tab is"+driver.getTitle());
		Thread.sleep(3000);
		
		
	}
	
	public void switchtotab(int index) { 

		String windowtab=null;

		Set<String> tabs= driver.getWindowHandles();

		Iterator<String> obj= tabs.iterator();

		for(int i=0;i<=index;i++) {
			
			windowtab= obj.next();
		}
		driver.switchTo().window(windowtab);

		}

# **PAGE OBJECT MODEL(POM):**

- POM is a design pattern used in test automation.

- It is the framework in which one can create Object Repository for web Ul elements like buttons, links, texts using locator information.

- We also provide information about the actions to be done like Sendkeys, Select, click etc.

- We need to create the page class for each webpage in the application.

- It becomes useful to create abstraction for the webpage called page object.

- These page objects represent the things being filled in or clicked for examination context.

### ** WHY POM :**
- Reusability
- Eliminate Duplicity

## Advantages of Page object model

**Key Advantages**

- Separation between code for Test automation and web page-specific code like locators and their layout.

- It can reduce or eliminate duplicity in the test code -Reusability of code is more

- Well-ordered and organized code structure -improves readability and gives interactive documentation

- Maintenance of test script is easy.

- Easy to understand

## **POM IMPLEMENTATION:**

- With Page Factory
- Without Page Factory

### **1) With Page Factory**

*Page Class:*

package packageobjectmodel;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

//POM
public class POM_WithoutPageFactory {
	
	WebDriver driver;
	
	public POM_WithoutPageFactory(WebDriver driver) {
		
		this.driver = driver;
		
	}
	
	//Locators:
	
	By reglink = By.linkText("Register");
	By gender = By.id("gender-male");
	By fname = By.name("FirstName");
	By lname = By.id("LastName");
	By emailid = By.id("Email");
	By pwd = By.id("Password");
	By cpwd = By.name("ConfirmPassword");
	By regbutton = By.name("register-button");
	
	//Login Locators:
	
	By loginlink = By.linkText("Log in");
	By email = By.id("Email");
	By pass = By.id("Password");
	By lognbtn = By.xpath("//*[@value='Log in']");
	
	//Logout locators:
	
	By logout = By.linkText("Log out");
	
	
	//Implement the method for register functionality
	
	public void Register() {
		
		driver.findElement(reglink).click();
		driver.findElement(gender).click();
		driver.findElement(fname).sendKeys("Divya");
		driver.findElement(lname).sendKeys("Ban");
		
		driver.findElement(emailid).sendKeys("Ram567@gmail.co");
		driver.findElement(pwd).sendKeys("5768rty");
		driver.findElement(cpwd).sendKeys("5768rty");
		driver.findElement(regbutton).click();
		driver.findElement(logout).click();
		
	}
	
	public void login() {
		
		driver.findElement(loginlink).click();
		driver.findElement(email).sendKeys("Ram567@gmail.co");
		driver.findElement(pass).sendKeys("5768rty");
		driver.findElement(lognbtn).click();
		
	}
	
	public void Logout() {
		
		driver.findElement(logout).click();
		
	}

}

*Test Execution Class:*

package packageobjectmodel;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class ExecultionClass {
	
	
	static WebDriver driver;
	@BeforeTest
	public void LaunchBrowser() {
		
		driver = new ChromeDriver();
		
		driver.get("https://demowebshop.tricentis.com/");
		driver.manage().window().maximize();
	}
	@Test
	public void Actionsmethod() {
		
		POM_WithoutPageFactory obj = new POM_WithoutPageFactory(driver);
		obj.Register();
		obj.login();
		obj.Logout();
		
	}
	
	@AfterTest
	public void closebrowser() throws InterruptedException {
		
		Thread.sleep(4000);
		driver.quit();
	}
}

## **2) Without Page Factory**

## *(Page class)*

package packageobjectmodel;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.How;
import org.openqa.selenium.support.PageFactory;

//POM
public class POM_WithPageFactory {
	
	WebDriver driver;

	public POM_WithPageFactory(WebDriver driver) {

		this.driver = driver;
		PageFactory.initElements(driver, this);

	}
	
	//LOCATORS:
	
	@FindBy(how = How.LINK_TEXT, using = "Register")
	WebElement register;

	@FindBy(id = "gender-male")
	WebElement gender;

	@FindBy(name = "FirstName")
	WebElement fname;

	@FindBy(name = "LastName")
	WebElement lname;

	@FindBy(id = "Email")
	WebElement emailid;

	@FindBy(id = "Password")
	WebElement pwd;

	@FindBy(name = "ConfirmPassword")
	WebElement cpwd;

	@FindBy(name = "register-button")
	WebElement regbutton;

	// Login Page

	@FindBy(how = How.LINK_TEXT, using = "Log in")
	WebElement login;

	@FindBy(xpath = "//*[@name='Email']")
	WebElement email;

	@FindBy(id = "Password")
	WebElement password;

	@FindBy(xpath = "//*[@value='Log in']")
	WebElement loginbutton;

	// search

	@FindBy(id = "small-searchterms")
	WebElement search;

	@FindBy(xpath = "//*[@value='Search']")
	WebElement button;

	// Logout

	@FindBy(how = How.LINK_TEXT, using = "Log out")
	WebElement logout;

	**================= METHODS =================**

	public void Registerpage() {

		register.click();
		gender.click();
		fname.sendKeys("Mahdvi");
		lname.sendKeys("Odel");
		emailid.sendKeys("madhvi56@gmail.com");
		pwd.sendKeys("Mercury903");
		cpwd.sendKeys("Mercury903");
		regbutton.click();
		logout.click();
	}

	public void Loginmethod() {

		login.click();
		emailid.sendKeys("john.parker3421@gmail.com");
		password.sendKeys("Mercury@123");
		loginbutton.click();
	}

	public void searchbtn() {

		search.click();
		search.sendKeys("Health Book");
		search.click();
		button.click();
	}
	
}

## *(Test execution class)*

package packageobjectmodel;

import java.time.Duration;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class Execution_withpage {
	
	static WebDriver driver;
    @BeforeTest
	public void LaunchBrowser() {

		driver = new ChromeDriver();

		driver.get("https://demowebshop.tricentis.com/");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
	}
    @Test
	public void Actionsmethod() {

		POM_WithPageFactory obj = new POM_WithPageFactory(driver);
		obj.Registerpage();
		obj.Loginmethod();
		obj.searchbtn();
		
	}
	
    @AfterTest
	public void closebrowser() throws InterruptedException {
		
		Thread.sleep(4000);
		driver.quit();
	}
	
}
