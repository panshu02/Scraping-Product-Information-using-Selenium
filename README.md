# Scraping-Product-Information-using-Selenium
**Bonus 1:** An 'Open in Google Colab' button has been added in the Jupyter Notebook, however the last code cell for Bonus 2 for dumping the data into MySQL local server cannot be run on Google Colab.

To scrape Selenium library is used with Chrome browser driver. The chrome driver is installed and the webdriver instance for chrome with options is intialized. Now, the driver only needs the product URLs to scrape in HTML format. The required data (Title, Price, Image URL, Details) can then be processed using 'Selenium WebElement' methods.

The product URLs were present in a google sheets with the following link:

https://docs.google.com/spreadsheets/d/1BZSPhk1LDrx8ytywMHWVpCqbm8URTxTJrIRkD7PnGTM/edit?usp=sharing

Using pandas the sheet is read as a csv file to a dataframe. The URLs are then sent in a loop  to a scraping function 'prod_info' which scrapes the necessary data from the URLs. The data is stored as a list of dictionaries where each element of the list is one URL result. This data list is then dumped into a json file using the json python library.

Time taken to open and extract product information from all pages: **13m 24s**


**Important:** This part can only be run in a PC with MySQL server client installed. The code part can be run only using a local python compiler with the correct SQL server credentials.

As **Bonus 2**, a dataframe from the data processed is made. After this, using 'mysql-connector-python' library, a connection with the local MySQL server is made by passing on the server credentials. Using the connection, a cursor is made which can execute and commit SQL commands to the local server. The created dataframe is finally dumped to a table created using an execute statement.
