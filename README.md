[![🇺🇸 English](https://img.shields.io/badge/Language-English-blue?style=for-the-badge&logo=Google%20Translate)](README-EN.md)
---
# Extension LoiNguyen_Helper


## Tổng Quan
Extension LoiNguyen_Helper là một công cụ đa năng được thiết kế để hỗ trợ quản lý cài đặt proxy và user agent trực tiếp trong tệp `background.js` hoặc trong trong quá trình sử dụng bằng cách sử dụng các lệnh JavaScript. Công cụ này hỗ trợ tự động hóa bằng Selenium với cả C# và Python.

## Tính Năng
- Thay đổi cài đặt proxy trực tiếp trong `background.js`.
- Thay đổi cài đặt proxy trong trong quá trình sử dụng.
- Bật hoặc tắt proxy bằng các lệnh JavaScript.
- Cập nhật User-Agent và cài đặt Proxy động.
- Vô hiệu hóa Web RTC

## Sử Dụng

### Thay Đổi Cài Đặt Proxy trong `background.js`
Bạn có thể thay đổi trực tiếp cài đặt proxy trong tệp `background.js`.

### Thay Đổi Cài Đặt Proxy Trong trong quá trình sử dụng
Bạn có thể điều chỉnh cài đặt proxy khi tiện ích mở rộng đang chạy bằng các lệnh JavaScript sau:

#### Bật/Tắt Proxy
Để tắt proxy, sử dụng:
```js
localStorage.setItem('StopProxy', 'true');
```

Để bật proxy, sử dụng:
```js
localStorage.setItem('StopProxy', 'false');
```

#### Thay Đổi UserAgent
Để thay đổi UserAgent, sử dụng:
```js
localStorage.setItem('UserAgent', 'NEW_USERAGENT');
```

Để Xóa UserAgent, sử dụng:
```js
localStorage.setItem('UserAgent', '');
```

#### Thay Đổi Proxy
Để thay đổi Proxy, sử dụng:
```js
localStorage.setItem('SetProxy', 'NEW_PROXY');
```

## Tự Động Hóa với Selenium
---
### Selenium C#
Sử dụng đoạn mã C# sau để tương tác với tiện ích mở rộng:
```csharp
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;

class Program
{
    static void Main()
    {
        // Khởi tạo Chrome driver
        IWebDriver driver = new ChromeDriver();

        // Điều hướng đến trang tiện ích mở rộng hoặc bất kỳ trang nào mà tiện ích mở rộng đang hoạt động
        driver.Navigate().GoToUrl("chrome-extension://your-extension-id/popup.html");

        // Tắt proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('StopProxy', 'true');");

        // Bật proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('StopProxy', 'false');");

        // Thay đổi UserAgent
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('UserAgent', 'NEW_USERAGENT');");

        // UserAgent Mặc định
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('UserAgent', '');");

        // Thay đổi Proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('SetProxy', 'NEW_PROXY');");

        // Đóng trình duyệt
        driver.Quit();
    }
}
```
---
### Selenium Python
Sử dụng đoạn mã Python sau để tương tác với tiện ích mở rộng:
```python
from selenium import webdriver

# Khởi tạo Chrome driver
driver = webdriver.Chrome()

# Điều hướng đến trang tiện ích mở rộng hoặc bất kỳ trang nào mà tiện ích mở rộng đang hoạt động
driver.get("chrome-extension://your-extension-id/popup.html")

# Tắt proxy
driver.execute_script("localStorage.setItem('StopProxy', 'true');")

# Bật proxy
driver.execute_script("localStorage.setItem('StopProxy', 'false');")

# Thay đổi UserAgent
driver.execute_script("localStorage.setItem('UserAgent', 'NEW_USERAGENT');")

# UserAgent Mặc định
driver.execute_script("localStorage.setItem('UserAgent', '');")

# Thay đổi Proxy
driver.execute_script("localStorage.setItem('SetProxy', 'NEW_PROXY');")

# Đóng trình duyệt
driver.quit()
```
---
## 📌 **Liên Hệ**

Nếu bạn gặp phải bất kỳ vấn đề nào hoặc muốn đóng góp vào dự án, bạn có thể liên hệ với tôi qua:

- **SĐT**: 0963 159 294
- **Facebook**: [Lowji194](https://www.facebook.com/Lowji194/)

---

---

## ☕ Buy me a coffee

Nếu dự án này hữu ích với bạn, hãy mời mình một ly cà phê để ủng hộ việc duy trì và phát triển dự án. Cảm ơn bạn!

<p align="center">
  <a href="https://raw.githubusercontent.com/lowji194/lowji194/main/assets/donate-qr.svg"><img src="https://raw.githubusercontent.com/lowji194/lowji194/main/assets/donate-qr.svg" width="300" alt="Donate — scan the QR code"></a>
</p>
