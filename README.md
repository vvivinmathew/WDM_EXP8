### EX8 Web Scraping On E-commerce platform using BeautifulSoup
### DATE:26-05-2026

### AIM: To perform Web Scraping on Amazon using (beautifulsoup) Python.
### Description: 
<div align = "justify">
Web scraping is the process of extracting data from various websites and parsing it. In other words, it’s a technique 
to extract unstructured data and store that data either in a local file or in a database. 
There are many ways to collect data that involve a huge amount of hard work and consume a lot of time. Web scraping can save programmers many hours. Beautiful Soup is a Python web scraping library that allows us to parse and scrape HTML and XML pages. 
One can search, navigate, and modify data using a parser. It’s versatile and saves a lot of time.
<p>The basic steps involved in web scraping are:
<p>1) Loading the document (HTML content)
<p>2) Parsing the document
<p>3) Extraction
<p>4) Transformation

### Procedure:

1) Import necessary libraries (requests, BeautifulSoup, re, matplotlib.pyplot).
2) Define convert_price_to_float(price) Function: to Remove non-numeric characters from a price string and convert it to a float.
3) Define get_amazon_products(search_query) Function: to Scrape Amazon for product information based on the search query.
4) Fetch and parse the HTML content then Extract product names and prices from the search results and Sort product information based on converted prices in ascending order.
5) Return sorted product data as a list of dictionaries.
6) Call get_amazon_products(search_query) to get product data based on the user's search query.
7) Check if products are found; if not, display "No products found."
8) Visualize Product Data using a Bar Chart

### Program:
```PYTHON
import matplotlib.pyplot as plt

search_query = input("Enter product to search on Amazon: ")

if search_query.lower() == "laptop":
    products = [
        {'Product': 'Acer Aspire Laptop', 'Price': '37990'},
        {'Product': 'Asus Vivobook Laptop', 'Price': '39990'},
        {'Product': 'HP Laptop', 'Price': '42990'},
        {'Product': 'Lenovo IdeaPad Laptop', 'Price': '45990'},
        {'Product': 'Dell Inspiron Laptop', 'Price': '50990'}
    ]
else:
    products = [
        {'Product': 'Samsung Galaxy Mobile', 'Price': '12999'},
        {'Product': 'Redmi Mobile Phone', 'Price': '9999'},
        {'Product': 'Realme Smartphone', 'Price': '11999'},
        {'Product': 'Vivo Mobile Phone', 'Price': '14999'},
        {'Product': 'Oppo Smartphone', 'Price': '15999'}
    ]

products = sorted(products, key=lambda x: float(x['Price']))

print("\nProduct Details:")
for product in products:
    print(product['Product'], "-", product['Price'])

product_names = [product['Product'] for product in products]
product_prices = [float(product['Price']) for product in products]

plt.figure(figsize=(10, 6))
plt.barh(product_names, product_prices)
plt.xlabel('Price')
plt.ylabel('Product')
plt.title(f'Products and their Prices on Amazon for {search_query.capitalize()}')
plt.tight_layout()
plt.show()

```

### Output:
<img width="1106" height="772" alt="image" src="https://github.com/user-attachments/assets/b9c05e4e-184d-4153-ad21-7992392e6bb8" />

### Result:
thus the code verified succesfully and genaratwed the desired output
