# Extension LoiNguyen_Helper

## Overview
Extension LoiNguyen_Helper is a versatile tool designed to assist with managing proxy settings and user agents directly within the `background.js` file or during runtime using JavaScript commands. This tool supports automation using Selenium with both C# and Python.

## Features
- Change proxy settings directly within `background.js`.
- Modify proxy settings during runtime.
- Enable or disable proxy using JavaScript commands.
- Update User-Agent and Proxy settings dynamically.

## Usage

### Change Proxy Settings in `background.js`
You can directly modify the proxy settings within the `background.js` file.

### Change Proxy Settings During Runtime
You can adjust the proxy settings while the extension is running using the following JavaScript commands:

#### Enable/Disable Proxy
To disable the proxy, use:
```js
localStorage.setItem('StopProxy', 'true');
```

To enable the proxy, use:
```js
localStorage.setItem('StopProxy', 'false');
```

#### Change UserAgent
To change the UserAgent, use:
```js
localStorage.setItem('UserAgent', 'NEW_USERAGENT');
```

#### Change Proxy
To change the Proxy, use:
```js
localStorage.setItem('SetProxy', 'NEW_PROXY');
```

## Automation with Selenium

### Selenium C#
Use the following C# snippet to interact with the extension:
```csharp
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;

class Program
{
    static void Main()
    {
        // Initialize the Chrome driver
        IWebDriver driver = new ChromeDriver();

        // Navigate to the extension page or any page where the extension is active
        driver.Navigate().GoToUrl("chrome-extension://your-extension-id/popup.html");

        // Disable the proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('StopProxy', 'true');");

        // Enable the proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('StopProxy', 'false');");

        // Change UserAgent
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('UserAgent', 'NEW_USERAGENT');");

        // Change Proxy
        ((IJavaScriptExecutor)driver).ExecuteScript("localStorage.setItem('SetProxy', 'NEW_PROXY');");

        // Close the browser
        driver.Quit();
    }
}
```

### Selenium Python
Use the following Python snippet to interact with the extension:
```python
from selenium import webdriver

# Initialize the Chrome driver
driver = webdriver.Chrome()

# Navigate to the extension page or any page where the extension is active
driver.get("chrome-extension://your-extension-id/popup.html")

# Disable the proxy
driver.execute_script("localStorage.setItem('StopProxy', 'true');")

# Enable the proxy
driver.execute_script("localStorage.setItem('StopProxy', 'false');")

# Change UserAgent
driver.execute_script("localStorage.setItem('UserAgent', 'NEW_USERAGENT');")

# Change Proxy
driver.execute_script("localStorage.setItem('SetProxy', 'NEW_PROXY');")

# Close the browser
driver.quit()
```

## Contributions
We welcome contributions! Please feel free to submit a pull request or open an issue for any bugs or feature requests.
