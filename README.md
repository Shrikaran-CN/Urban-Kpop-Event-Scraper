# Urban-Kpop-Event-Scraper
This project is a Python-based web scraper for extracting event details from the Urban Kpop website. It utilizes Selenium, BeautifulSoup, and pandas to collect, parse, and organize event information into a CSV file.

## Features
* Scrapes event details including:
  * Event titles
  * Dates and times
  * Prices
  * Availability
  * Event status
  * Venue addresses
  * Additional details and instructions
  * Automatically scrolls through and loads all events on the webpage.
  * Cleans and structures the data into a well-organized DataFrame.
  * Extracts and reformats date, time, and price fields for better usability.
  * Exports the data to a CSV file.

## Screenshots
### Web Page Screenshot
Below is an example of the webpage being scraped:
![Screenshot 2025-01-07 101547](https://github.com/user-attachments/assets/67e1edd2-3125-4779-9c19-0ca52cd4a561)

### DataFrame Output
Here is a snapshot of the cleaned and structured data in the DataFrame:
![Output Snapshot](https://github.com/user-attachments/assets/a47f1022-112a-4e41-a7e6-fd49fddb04c7)

   
## Technologies Used
* **Python**: The programming language used for scraping and processing data.
* **Selenium**: Automates the loading and interaction with dynamic web pages.
* **BeautifulSoup**: Parses the HTML content of the page.
* **pandas**: Structures and processes the scraped data for analysis and export.
* **Requests**: Fetches individual event pages for detailed information.

## Requirements
Before running the script, ensure the following dependencies are installed:
```
pip install selenium
pip install beautifulsoup4
pip install pandas
```
Additionally, download and install the appropriate ChromeDriver for your browser version.

## How It Works
**1. Load and Scroll Through Events:**  
* The script uses Selenium to open the Urban Kpop events page and click the "Show more..." button repeatedly to load all events.

**2. Scrape Event Data:**  
* Once all events are loaded, the script uses BeautifulSoup to parse the HTML and extract event links.  
* For each event, details like title, date, time, price, and more are scraped.

**3. Data Cleaning and Transformation:**  
* Extracts specific fields such as start and end times, days, and time zones.  
* Converts price data into a numeric format for further analysis.

**4. Export to CSV:**  
* The final dataset is saved as a CSV file for easy sharing and analysis.

## Usage
**1. Set Up Selenium WebDriver**  
Download the ChromeDriver binary and update the chromedriver_path in the script:  
`chromedriver_path = '/path/to/chromedriver'  # Update the path`  
**2. Run the Script**  
Open the Jupyter Notebook `Urban_kpop_web_scraper.ipynb` and execute the cells step-by-step to scrape the data.  
**3. Output**  
The script generates a CSV file named Urban_Kpop_event_list.csv, containing all the event details.

## File Structure
* `Urban_kpop_web_scraper.ipynb`: The main Jupyter Notebook for scraping the data.
* `Urban_Kpop_event_list.csv`: The exported dataset in CSV format (generated after running the script).

## Data Fields
The final dataset includes the following columns:
* Title:	Name of the event
* Date:	Event date (formatted as YYYY-MM-DD)
* Day:	Day of the week
* Start Time:	Event start time
* End Time:	Event end time
* Time Zone:	Time zone of the event
* Price (£):	Price in GBP (numeric, free events marked as 0)
* Availability: Event availability status
* Event Status: Whether the event is confirmed or cancelled
* Address:	Venue address
* Details:	Additional event details
* Instructions:	Event-specific instructions
  
## Known Limitations
* **Dynamic Content Loading:** Relies on the presence of the "Show more..." button. If this feature changes, the script may need adjustments.
* **Address Parsing:** Assumes the second `event_header_info` contains address details. May need refinement for different formatting.

## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.

## Author
Developed by **Shrikaran C N**. For questions or contributions, feel free to reach out or submit a pull request.
