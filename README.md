package Flipkart;

import java.util.ArrayList;
import java.util.Set;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class search {


	public static void main(String[] args) throws InterruptedException {
	// TODO Auto-generated method stub
     	System.setProperty("webdriver.chrome.driver", "C:\\selenium setting\\chromedriver\\paish\\chromedriver.exe");
     	WebDriver driver = new ChromeDriver();
	driver.get("https://www.flipkart.com/");
	driver.manage().window().maximize();
	Thread.sleep(2000);
	driver.findElement(By.className("_2doB4z")).click(); 
	driver.findElement(By.name("q")).sendKeys("iphone 12 mini");
	//driver.findElement(By.name("q")).sendKeys("iphone 12" + Keys.ENTER);
	driver.findElement(By.className("L0Z3Pu")).click();
	//driver.findElement(By.className("_4rR01T")).click();
	Thread.sleep(2000);
	driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[2]/div[3]/div/div/div/a/div[2]/div[1]/div[1]")).click();
	//driver.findElement(By.cssSelector("[alt=\"APPLE iPhone 12 Mini (Black, 64 GB)\"]")).click();
		
		
	Set<String> paish=driver.getWindowHandles();
	//System.ouStringtln(paish);
	ArrayList<String> h = new ArrayList<String>(paish);
	driver.switchTo().window(h.get(1));	
	String price =	driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[2]/div[2]/div/div[4]/div[1]/div/div[1]")).getText();
	System.out.println("price Of the one product="+price);
	Thread.sleep(2000);
	//driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[1]/div[2]/div/ul/li[1]/button")).click();
	driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[1]/div[2]/div/ul/li[1]/button")).click();
	Thread.sleep(5000);
	driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[2]/div/div/div[1]/div/div[2]/div/div[3]/div[1]/div/button[2]")).click();
	Thread.sleep(3000);
	String price1 =driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[2]/div/div/div[1]/div/div[2]/div/div[1]/div[1]/span[1]/text()[2]")).getText();
	System.out.println("price after adding one more product="+price1);
	}
	
	
}
