Technologies/APIs used:
- [x] Flask
- [x] PostgreSQL
- [x] TailwindCSS
- [x] Bash (for automation)
- [x] Reddit API
- [x] TMDB API
---

**Introduction**: The core objective of our research is to gain insights into the dynamic landscape of movie trends and identify what makes a movie popular at any given time. We focus on key aspects such as trending topics, audience ratings, and discussions on platforms like TMDb and Reddit.

Our goal is to uncover the factors contributing to a movie's popularity, revealing emerging patterns in the industry. Our findings will provide valuable insights into audience preferences and the crucial role of social media in determining a movie's success today.

This exploration offers valuable insights for film industry professionals, filmmakers, and movie enthusiasts who want to better understand and navigate the evolving trends in movie popularity.

The Reddit and TMDB Data Crawler is a script developed to collect data from Reddit and The Movie Database (TMDB). This tool extracts vital information related to movies and TV shows, including their popularity and relevant discussions on Reddit, storing the data in a database for later analysis.


--- 
### Run the Web Application to view the trends

1. Create Virtual Environment using virtualenv package
```
virtualenv -p python3 env
```
2. 5. Create postgres database 
```
systemctl restart postgresql@16-main.service
```
3. Install the required libraries
```
source env/bin/activate
pip install flask psycopg2 pandas matplotlib seaborn
```
4. Locate Apache configuration file and edit it to point to the virtual environment and flask app
5. Restart Apache
```
sudo systemctl restart apache2
```
6. Modify the app.wsgi field to add flask app to your PATH
```
project_home = '/home/user/foldername'
```
8. Run the Flask App
```
   python3 app.py
```


### Run the scraper: 

Run the python file directly by creating python virtual environment(myenv) or run the bash script.

1. Create Virtual Environment using virtualenv package
```
virtualenv -p python3 env
```
2. Create postgres database and keep it open for connection
```
systemctl restart postgresql@16-main.service
```

3. Activate the virtual environment

```
 source env/bin/activate
```

4. Run the python script 
```
python3 scraper.py
```

_OPTIONAL_:   
5. You can automate the crawler using the shell scripts we have provided in `crawler_script.sh` and `test.sh`

```
bash test.sh
```

6. We have sent it to the background process to continuously collect data using the following command

```
nohup {HOME_FOLDER}/test.sh > results.out 2>&1 &
```
