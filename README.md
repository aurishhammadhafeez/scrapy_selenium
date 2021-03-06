## Scrapy Cloud & Selenium integration using Custom Image

Sample Scrapy project demonstrating integration with Selenium using Firefox and its geckodriver.
This project is ready to deploy to Scrapy Cloud using a custom Docker image.

Based on [this KB](https://support.scrapinghub.com/support/solutions/articles/22000240310-deploying-custom-docker-image-with-selenium-on-scrapy-cloud)


### Usage

Install [shub](https://shub.readthedocs.io/en/stable/index.html)

```bash
pip install shub
``` 

Modify the *scrappinghub.yml* file and change `<YOU PROJECT ID>` with ypu actual project ID
```yaml
project: <YOU PROJECT ID>
requirements_file: ./requirements.txt
image: true
```

Deploy your project to Scrapy Cloud
```bash
$ shub login

Enter your API key from https://app.scrapinghub.com/account/apikey
API key: ********************************
Validating API key...
API key is OK, you are logged in now.

$ shub deploy

Building images.scrapinghub.com/project/<YOU PROJECT ID>:1.0.
Steps: 100%|█████████████| 12/12
The image images.scrapinghub.com/project/<YOU PROJECT ID>:1.0 build is completed.
Login to images.scrapinghub.com succeeded.
Pushing images.scrapinghub.com/project/<YOU PROJECT ID>:1.0 to the registry.
b58632e02b0f: 100%|█████████████| 53.8k/53.8k [2.55kB/s]
9cf43d5c0161: 100%|█████████████| 33.8k/33.8k [1.61kB/s]
The image images.scrapinghub.com/project/<YOU PROJECT ID>:1.0 pushed successfully.                                                                                                                                                    | 512/15.2k [?B/s]
Deploying images.scrapinghub.com/project/<YOU PROJECT ID>:1.0
You can check deploy results later with 'shub image check --id 1'.
Progress: 100%|█████████████| 100/100
Deploy results:
{'status': 'ok', 'project': <YOU PROJECT ID>, 'version': '1.0', 'spiders': 1}
``` 