# Project overview
- The code crawls Jumia website and extract the data of all products then add it to csv files which are products file and sellers file.

- Products file contains [Name, Price, General category, Sub category, Category, Brand, Specification, Rating, Reviews, Link, Seller, Seller score, Seller profile link]

- Sellers file contains [Name, Score, Profile link]

# Products file sample ![image](https://user-images.githubusercontent.com/107722015/192972205-4deeaaba-d9f9-4f7e-b55f-d383eb5c9e23.png)

# Products file sample [ Closer look ] ![image](https://user-images.githubusercontent.com/107722015/192973964-dd47570e-b1de-45a6-926a-c28b13006095.png)


#Sellers file sample ![image](https://user-images.githubusercontent.com/107722015/192972886-e75e900f-a4d4-4800-8506-2ac783278913.png)

# Project flow
1. The first step is creating the main 3 files which are products file, sellers file and done file ( this file will be explained later ).
2. Open the website and start storing the links of its main categories.
3. Loop on the main categories links and pass the links to a function that breaks them into smaller categories.
4. Keep breaking the categories into smaller ones until it is possible to crawl them.
5. Create a csv file to the category then start crawling each category by crawling each product in it and add it to the file.
6. When the category crawling is done, the program writes its name in the done file, append all products it the file to the products file then delete it.
7. The programs keeps going until all the main products are crawled, if the internet connection went down the code will stop, it will continue from where it stopped if you run it again.

# Flowchart of the project
### Note: Break category is a recursive function so it’s hard to represent.
![image](https://user-images.githubusercontent.com/107722015/192973376-0b8e045c-ef95-4624-9c1d-a71bdd934ad6.png)

# Main problems and their solutions

**1. Each category can have maximum 50 pages even if it contains more products**

- This problem was solved by creating a recursive function that keeps breaking the category into smaller categories until the category has less than 50 pages.

**2. Some URL links are corrupted, sometimes it redirect me to the main website page and sometimes it doesn’t exist**

- Those problem were solved to checking if the page exists or checking if it contains the elements it should contain before going on.

**3. Sometimes the internet connection goes down so the program stops**

- This problem was solved by creating Done.csv file to store the crawled categories so they won’t be crawled again.

**4. When the program stops during a category crawling, when I run it again it start the same category again because it’s not yet added to the done file because it’s not entirely crawled yet and this caused some products to be duplicated in the products file.**

- This was solved by creating a separated file for each product when it’s crawling starts and when it’s done, the data is appended to the products file the delete this category file.

**5. Sometimes the categories names were not at all clear**

- This was solved by crawling 3 categories for each product which made it clearer and more specific.

# Functions and what they do
Check if needed files exist and create them if not:
- check_files_exist()
- create_products_file()
- create_done_file()
- create_sellers_file()
- create_sub_category_file()

Write to files:
- append_products_file()
- write_to_done_file()
- write_to_sellers_file()
- write_to_sub_category_file()

Get a page if it exists and working:
- get_this_page()
- page_exists()
- max_pages_exceeded()
- get_next_page()

Recursively breaks the category until it contains less than 50 pages:
- break_category()

Crawl categories, category page and product:
- crawl_category()
- crawl_page()
- crawl_product_page()


## Thank You!! <3
