
# Web Scrapping
Simple Web scrapper to scrap images from github using Requests and Beautifulsoup. This is a minor project for the an elective course Python And Scientific Python-18ECE201J-E. 


## What is Web Scraping?

Web scraping, also known as web harvesting or web data extraction, is a type of data scraping that is used to extract information from websites. Using the Hypertext Transfer Protocol or a web browser, the web scraping software can directly access the World Wide Web.
## Install dependencies:
Install BeautifulSoup | bs4 (for Python 3.x) and requests
```
pip install bs4
```
```
pip install requests 
```
or
<ul>
	<li>clone or download it from <a href="https://github.com/Kanishk-K-U/web-scrapping" target="_blank" rel="noopener">here</a></li>
	<li>install dependencies.txt file</li>
 </ul>
 
```
pip install -r dependencies.txt
```

## How the code runs:
* importing libraries `requests` and `BeautifulSoup`

```python
  import requests
  from bs4 import BeautifulSoup as bs
```
         
* now input the username 
```python
github_user = input("Enter GitHub User:")
```
Now that we have the github user that the user entered, let's say my username, Kanishk-K-U, it will be saved in this `variable`.

* setting the website's URL for data scrapping
```python
url = "https://github.com/"+github_user
```
now dynamically `url` contain website link with user name  
* sending request to website
```python
r = requests.get(url)
```
Sending a request to that url is the first step in performing web scraping. Since we already know that the url will contain the user's username and other input, we'll send the request to that page and wait for a response.

* reading all html data using `BeautifulSoup`
```python
soup = bs(r.content,"html.parser")
```
Now that we have all of the HTML on this page, we have it saved in this soup variable. This basically represents the HTML source code for every piece of content on that page.

* getting specific data from website
```python
profile_image = soup.find('img',{'alt':'Avatar'})["src"]
print(profile_image)
```
Now, `soup.find` denotes that we must locate a certain element with a specific class, specification, or other attribute from this HTML code. we know that it will be in a specific HTML tag that need to do is just print or obtain that particular image.

* Run the code now, and then click the `link` printed in the output console window.

## Output
<p >
  <div align="center" >
 <img width="640" height="400" src="https://github.com/Kanishk-K-U/web-scrapping/blob/master/output.jpeg">
    </div>
</p>

## Conclusion
In conclusion we had direct access to a data from a website and collected data. There are a few libraries that can perform the same task as scrapy, which may be used to create a bot to automatically crawl data, but beautiful soup is recommended since it is more user-friendly for novices and enables programmers to extract specific webpage elements (for example, a list of images).



