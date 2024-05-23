import requests
from bs4 import BeautifulSoup
url = "https://www.pinterestcareers.com/"
response = requests.get(url)
if response.status_code == 200:
    page_content = response.content
    soup = BeautifulSoup(page_content, 'html.parser')
    paragraphs = soup.find_all('p') 
        	text = paragraph.text     
#2nd part of code
links = soup.find_all('a')
    for link in links:
        text = link.text
        href = link.get('href')
        print(f"Text: {text}, Href: {href}
#3rd part of code
images = soup.find_all('img')
    for image in images:
        src = image.get('src')
        print(f"Src: {src}")
