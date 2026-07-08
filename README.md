# Postman API Automation Intergration with Github Actions #

This repositoru is a demonstartion for Poc for integrating postman tests with github actions. The tests are written in postman and they are executed on the VM with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch. You can also execute the project manually using workflow_dispatch. 
The project runs on a scheduled time with cron jobs.

The HTML report is archieved and kept in the artifact section for the team to download it. Along with that they can view the report directly from the githib page : https://kumarankeerthana.github.io/Phoenix-Inwarranty-Flow/


## Tech Stack ##
1. postman
2. nodejs 24v
3. Newman
4. Newman-reporter-htmlextra
5. Github actions
6. Github pages
7. Csv for data testing
8. AWS EC2 instance for self hosted runner

## Testing Coverage ## 

1. Happy Flow testing
2. Negative Testing and edge case testing
3. Token Testing
4. Data driven testing
5. Schema Validation
6. Secret management with Github Secrets



## HTML Report ##
The report will be created in the newman folder 
![Postman Report](https://github.com/kumarankeerthana/Phoenix-Inwarranty-Flow/blob/static-content/HTML%20report%20-%20postman.png) 

## Project Structure ##

Postman
├─ Inwarranty-flow-Collection API Req.postman_collection.json
├─ QA.postman_environment.json
├─ README.md
└─ testdata.csv


## How to run the project ##
You can run the project on your local system.

1.Clone the project on your local system https://github.com/kumarankeerthana/Phoenix-Inwarranty-Flow
2. Install Nodejs and Npm
3. Install newman : npm install newman -g newman 
4. install newman html-reporter : npm install -g newman-reporter-htmlextra
5. Run the newman command : 

```
          newman run 'Inwarranty-flow-Collection API Req.postman_collection.json' \
                      -e QA.postman_environment.json \
                      -d testdata.csv \
                      -r cli,html-extra \
                      --reporter-htmlextra-export ./newman/index.html
```


