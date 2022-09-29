# Project overview
- The code crawls Jumia website and extract the data of all products then add it to csv files which are products file and sellers file.

- Products file contains [Name, Price, General category, Sub category, Category, Brand, Specification, Rating, Reviews, Link, Seller, Seller score, Seller profile link]

- Sellers file contains [Name, Score, Profile link]

# Products file sample ![image](https://user-images.githubusercontent.com/107722015/192972205-4deeaaba-d9f9-4f7e-b55f-d383eb5c9e23.png)

# Products file sample [ Closer look ] ![image](https://user-images.githubusercontent.com/107722015/192972764-48a89295-8a42-4e5f-9ffc-b2e13774b5a5.png)

#Sellers file sample ![image](https://user-images.githubusercontent.com/107722015/192972886-e75e900f-a4d4-4800-8506-2ac783278913.png)

# Project flow![image](https://user-images.githubusercontent.com/107722015/192972952-2cc50e85-348c-4c83-b1d5-8fdf608dacbe.png)
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
1. Each category can have maximum 50 pages even if it contains more products
This problem was solved by creating a recursive function that keeps breaking the category into smaller categories until the category has less than 50 pages.
2. Some URL links are corrupted, sometimes it redirect me to the main website page and sometimes it doesn’t exist
- Those problem were solved to checking if the page exists or checking if it contains the elements it should contain before going on.






