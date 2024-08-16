# Chrome Options Form
Here is a guide to list all possible options for our Chrome driver.

## Coding Guide
The structure of the code is always the same:
- Create an instance of Chrome options:

    `chrome_options = Options()`
- Define the Chrome options:

    `chrome_options.add_argument(...)`
- Create a new instance of the Chrome browser with the specified options:

    `driver = webdriver.Chrome(options=chrome_options)`
- Set the URL you want to scrape and inject it into the driver:

    `url = "https://professeur-layton.fandom.com/fr/wiki/"`

    `driver.get(url)`

Note:
- `webdriver.Chrome` initializes the Chrome browser via Selenium's WebDriver.
- `options=chrome_options` allows passing the previously defined options to this Chrome instance.

Here are the different possible options:

## --- GENERAL OPTIONS ---

#### Disable the search engine selection prompt on the first launch
    chrome_options.add_argument('--disable-search-engine-choice-screen')

#### Run Chrome in headless mode (no graphical interface)
    chrome_options.add_argument('--headless')

#### Disable GPU hardware acceleration (often necessary in headless mode)
    chrome_options.add_argument('--disable-gpu')

#### Start Chrome with a specific window size
    chrome_options.add_argument('--window-size=1920,1080')

#### Start Chrome maximized
    chrome_options.add_argument('--start-maximized')

#### Open Chrome in incognito mode (private browsing)
    chrome_options.add_argument('--incognito')

#### Disable Chrome's sandbox for specific environments (less secure)
    chrome_options.add_argument('--no-sandbox')

#### Use a custom user profile (allows retaining cookies, history, etc., associated with the profile)
    chrome_options.add_argument('--user-data-dir=/path/to/your/custom/profile')

## --- SECURITY AND PRIVACY ---

#### Disable web security, for example, to access pages with SSL errors
    chrome_options.add_argument('--disable-web-security')

#### Disable site isolation (may improve performance but reduces security)
    chrome_options.add_argument('--disable-site-isolation-trials')

#### Disable infobars such as "Chrome is being controlled by automated test software"
    chrome_options.add_argument('--disable-infobars')

#### Disable installed Chrome extensions
    chrome_options.add_argument('--disable-extensions')

#### Block unwanted popups, such as ads and other intrusive windows
    chrome_options.add_argument("--disable-popup-blocking")

#### Disable browser notifications
    chrome_options.add_argument('--disable-notifications')

#### Enable safe browsing to block malicious content
    chrome_options.add_argument('--safebrowsing-disable-download-protection')

## --- PERFORMANCE AND EFFICIENCY ---

#### Disable specific Chrome features to improve performance
    chrome_options.add_argument('--disable-features=NetworkService,Notifications')

#### Disable DNS prefetching to speed up page loading
    chrome_options.add_argument('--disable-dns-prefetch')

#### Disable the network service (reduces network resource usage)
    chrome_options.add_argument('--disable-network-service')

#### Enable or disable Brotli compression (may affect network performance)
    chrome_options.add_argument('--disable-brotli')

## --- DISPLAY AND RENDERING ---

#### Disable WebGL to avoid certain heavy animations or graphics
    chrome_options.add_argument('--disable-webgl')

#### Disable software rendering, which can improve graphical performance
    chrome_options.add_argument('--disable-software-rasterizer')

#### Disable image loading to speed up page loading
    chrome_options.add_argument('--blink-settings=imagesEnabled=false')

#### Open a port for remote debugging
    chrome_options.add_argument('--remote-debugging-port=9222')

## --- AUTOMATION DETECTION ---

#### Disable features that reveal the browser is being controlled by automation tools
    chrome_options.add_argument('--disable-blink-features=AutomationControlled')

#### Prevent the use of Chrome's default automation extension
    chrome_options.add_experimental_option("useAutomationExtension", False)

#### Exclude certain switches (like 'enable-automation') that reveal the browser is automated
    chrome_options.add_experimental_option("excludeSwitches", ["enable-automation"])

#### Disable infobars that appear at the top of the browser
    chrome_options.add_argument('disable-infobars')

#### Enable certain automation settings (may be redundant with other options)
    chrome_options.add_argument('enable-automation')

## --- OTHER USEFUL OPTIONS ---

#### Specify a custom User-Agent
    chrome_options.add_argument('--user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.212 Safari/537.36"')

#### Disable Chrome's crash reporting
    chrome_options.add_argument('--disable-crash-reporter')

#### Disable automatic bookmark (favorites) management
    chrome_options.add_argument('--disable-bookmark-autocomplete')

#### Disable print confirmation popups
    chrome_options.add_argument('--kiosk-printing')

#### Disable script loading to speed up page loading times
    chrome_options.add_argument('--disable-javascript')

#### Disable audio to avoid sounds during automation
    chrome_options.add_argument('--mute-audio')
