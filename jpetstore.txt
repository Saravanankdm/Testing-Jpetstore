package testNGFramework;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Test;

public class JpetSTORE {
	
	WebDriver driver;

	@Test(priority=1)
	public void pageLoad() {
		System.setProperty("webdriver.chrome.driver", "/home/rahul/Desktop/Selenium/chromedriver_linux64/chromedriver");
	    driver = new ChromeDriver();
		driver.get("https://petstore.octoperf.com/actions/Account.action?newAccountForm=");
		driver.manage().window().maximize();
	}
	
	@Test(priority=2)
	public void userIfo() {
		driver.findElement(By.xpath("//td[contains(text(),'User ID:')]/following::input[1]")).sendKeys("112334556");
		driver.findElement(By.name("password")).sendKeys("122233rdd");
		driver.findElement(By.name("repeatedPassword")).sendKeys("122233rdd");
	}
	
	@Test(priority=3)
	public void accountInfo() {
		driver.findElement(By.xpath("//td[contains(text(),'First')]/following::input[1]")).sendKeys("Rahul");
		driver.findElement(By.name("account.lastName")).sendKeys("vaada");
		driver.findElement(By.name("account.email")).sendKeys("vaayayenvera@gmail.com");
		driver.findElement(By.name("account.phone")).sendKeys("5678943278");
		driver.findElement(By.name("account.address1")).sendKeys("bftssgchhcyg");
		driver.findElement(By.name("account.address2")).sendKeys("jkkhdjbewbkc");
		driver.findElement(By.name("account.city")).sendKeys("chennai");
		driver.findElement(By.name("account.state")).sendKeys("tamil nadu");
		driver.findElement(By.name("account.zip")).sendKeys("600046");
		driver.findElement(By.name("account.country")).sendKeys("india");
	}
	
	@Test(priority=4)
	public void profileInfo() {
		Select abc = new Select (driver.findElement(By.xpath("//td[contains(text(),'Language')]/following::select[1]")));
		abc.selectByVisibleText("english");
		Select aaa = new Select (driver.findElement(By.xpath("//td[contains(text(),'Favourite')]/following::select[1]")));
		aaa.selectByIndex(3);
		WebElement bbb = driver.findElement(By.name("account.listOption"));
		bbb.click();
		driver.findElement(By.name("account.bannerOption")).click();
		driver.findElement(By.xpath("//td[contains(text(),'Enable MyBanner')]/following::input[2]")).click();
	}

}
