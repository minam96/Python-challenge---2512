import requests
from bs4 import BeautifulSoup

url = "https://berlinstartupjobs.com/engineering/"

headers = {
    "User-Agent":
    "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36"
}

response = requests.get(url, headers=headers)

soup = BeautifulSoup(response.content, "html.parser")

response.content

jobs = soup.find_all("li", class_="bjs-jlid")[1:-1]

for job in jobs:
  title = job.find("h4", class_="bjs-jlid__h").text
  company = job.find("a", class_="bjs-jlid__b").text

  #--skils area  추출
  skill = job.find_all("a", class_="bjs-bl bjs-bl-whisper")
  skills = []

  for sk in skill:
    skills.append(sk.text)

  skills_str = ",".join(skills)

  print(f"title: {title}")
  print(f"company: {company}")
  print(f"skill: {skills_str}")
  print("--------------------------")
