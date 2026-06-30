from bs4 import BeautifulSoup
import requests

html_content=requests.get('https://books.toscrape.com/').text
soup=BeautifulSoup(html_content, 'lxml')
def find_book():
    books= soup.find_all('li',class_="col-xs-6 col-sm-4 col-md-3 col-lg-3")
    for index,book in enumerate(books):
        name= book.find('h3').find('a')['title']
        price=book.find('p', class_='price_color').text
        info_link= book.find('h3').find('a')['href']
        more_info= 'https://books.toscrape.com/'+ info_link
        with open(f"BookScraped/{index}.txt", 'w') as f:
            f.write(f'Name:{name}\n')
            f.write(f'Price: {price}\n')
            f.write(f'More Info: {more_info}\n')
        
find_book()