```

CRUMB=$(curl -s 'http://${USER}:${TOKEN}@localhost:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)')

curl -X PUT -H "$CRUMB" "http://${USER}:${TOKEN}@localhost:8080/job/NewJob/config.xml" -d @config.xml -H "Content-Type:application/xml"

curl -X POST -H "$CRUMB" "http://${USER}:${TOKEN}@localhost:8080/createItem?name=NewJob" -d @config.xml -H "Content-Type:application/xml"
