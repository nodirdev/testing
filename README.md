# testing
### NuGet Packages for Selenium!
```Selenium.WebDriver```
```Selenium.Chrome.WebDriver```
### Sample selenium test
```c#
[Test]
public void Test1()
{
    string ActualResult;
    string ExpectedResult = "Google";

    IWebDriver driver = new ChromeDriver(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location));
    //IWebDriver driver = new ChromeDriver();
    driver.Navigate().GoToUrl("https://google.com");
    driver.Manage().Window.Maximize();
    ActualResult = driver.Title;
    driver.FindElement(By.Name("q")).SendKeys("Flowers");
    driver.FindElement(By.XPath(@"//*[@id=""tsf""]/div[2]/div[1]/div[3]/center/input[1]")).Click();

    if (ActualResult.Contains(ExpectedResult))
        Assert.IsTrue(true, "pass");
    else
        Assert.IsTrue(false, "false");

    driver.Close();
    driver.Quit();

    Assert.Pass();
}
```
