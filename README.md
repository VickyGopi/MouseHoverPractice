package week4.day1;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

import io.github.bonigarcia.wdm.WebDriverManager;

public class MouseHoverPractice {

	public static void main(String[] args) {
		WebDriverManager.chromedriver().setup();
		ChromeDriver driver = new ChromeDriver();
				driver.get("https://demoqa.com/menu/");
				driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
				driver.manage().window().maximize();
				WebElement ele1 = driver.findElement(By.xpath("(//a[@href='#'])[2]"));
				WebElement ele2 = driver.findElement(By.xpath("(//a[@href='#'])[5]"));
				WebElement ele3 = driver.findElement(By.xpath("(//a[@href='#'])[6]"));
				//System.out.println(ele2.getText());
				//System.out.println(ele1.getText());
				Actions Build = new Actions(driver);
				Build.moveToElement(ele1).moveToElement(ele2).moveToElement(ele3).perform();
	}

}
