```

CRUMB=$(curl -s "http://${USER}:${TOKEN}@localhost:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,\":\",//crumb)")

# to update the job
curl -X POST -H "$CRUMB" \
    "http://${USER}:${TOKEN}@localhost:8080/job/NewJob/config.xml" \
    -d @jenkins.xml \
    -H "Content-Type:application/xml"

# to create the job 
curl -X POST -H "$CRUMB" \
    "http://${USER}:${TOKEN}@localhost:8080/createItem?name=NewJob2" \
    -d @jenkins.xml \
    -H "Content-Type:application/xml"

# to start the job
curl -X POST -H "$CRUMB" -u ${USER}:${TOKEN} \
    http://localhost:8080/job/NewJob/buildWithParameters?PASSWORD=123
