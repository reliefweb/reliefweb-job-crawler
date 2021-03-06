# reliefweb-job-crawler
ReliefWeb Job Crawler - A simple web crawler to grab jobs from a website
Uses reliefweb-job-assistant endpoint to tag the job information


## Structure

- main.py - *Main file* 
- setup.py - *Python setup for setuptools*

## Requirements

- python - Available from the [Python Homepage](https://www.python.org/)
- an endpoint with reliefweb-tag-assistant


- Modules required

```
$ sudo apt-get install python3-pip
$ pip install -r requirements.txt

```

- Main reliefweb-tag 

```
# if you install from your home path, there is no need to change the config file
$ git clone https://github.com/reliefweb/reliefweb-tagjob-crawler/
$ gedit config.py # configure the URL of the tagging endpoint 
$ sudo python3 setup.py install
$ python3 main.py &
```

## How to use the service

Parameters to the /web_crawl endpoint:

- url - *URL starting with http where the list of jobs is displayed*
- job_pattern - *String which is contained in **all the job URLs** so the crawler can identify what links refer to a 
job*
- org_id - *Organization ID opf the source in ReliefWeb to complete the job posting feed*
- format - *'html' or 'xml'* - If not present, default to html 

Once the backend is running you can use the following endpoints:

- OCHA http://localhost:5000/web_crawl?url=https://www.unocha.org/about-us/job-opportunities&job_pattern=jobdetail&org_id=1503
- WFP http://localhost:5000/web_crawl?url=http://www1.wfp.org/careers/job-openings&job_pattern=job_listing&org_id=1741
- RELIEF INTERNATIONAL http://localhost:5000/web_crawl?format=xml&org_id=2024&job_pattern=requisition.jsp&org_id=2024&url=https%3A%2F%2Fchp.tbe.taleo.net%2Fchp01%2Fats%2Fservlet%2FRss%3Forg%3DRI%26cws%3D4
- PALLADIUM GROUP http://localhost:5000/web_crawl?url=http://thepalladiumgroup.com/jobs&job_pattern=jobs/&org_id=25696

(Updated information and last names for the endpoints in the ```main.py``` file)
