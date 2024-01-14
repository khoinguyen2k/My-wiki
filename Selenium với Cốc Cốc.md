
Vì Cốc Cốc sử dụng nhân Chromium nên có thể sử dụng [Chrome Driver](https://chromedriver.chromium.org/downloads) để khởi chạy Cốc Cốc trong Selenium.

Vấn đề là phải tìm đúng phiên bản Chrome Driver cho Cốc Cốc.

Đầu tiên kiểm tra phiên bản hiện tại của Cốc Cốc. Vào Cài đặt -> Giới thiệu về Cốc Cốc. Ví dụ phiên bản là 115.0.132

Chọn phiên bản Chrome Driver thấp hơn một tẹo, tầm 112.0.5615.49

Viết ít code chạy thử, so với khi sử Chrome thì thêm câu lệnh về ChromeOptions 

(Lưu ý: chỗ options.setBinary(path) thay thế 'path' thành đường dẫn đến file Cốc Cốc.exe của bạn
Đơn giản thì phải chuột vào Cốc Cốc Shortcut -> open file location

Chỗ System.setProperty() cũng cần thay thế đường dẫn hợp lý
)

Code ví dụ:

    import org.openqa.selenium.WebDriver; 
    import org.openqa.selenium.chrome.ChromeDriver; 
    import org.openqa.selenium.chrome.ChromeOptions;

    public class AutoCocCoc {
       public static void main(String[] args) {

    //replace with your path
		System.setProperty("webdriver.chrome.driver", "D:/Downloads/chromedriver.exe");

		ChromeOptions options = new ChromeOptions();

    //replace with your path
		options.setBinary("C:/Users/Admin/AppData/Local/CocCoc/Browser/Application/browser.exe");
		
		WebDriver driver = new ChromeDriver(options);
		
		driver.get("https://www.google.com");
		
		driver.quit();

       }
    }

Selenium sẽ tự tìm phiên bản driver gần nhất để khớp với Cốc Cốc
