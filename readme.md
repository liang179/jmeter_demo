```
docker build jmeter -t jmeter


npm install @openapitools/openapi-generator-cli -g
mkdir test
cd test
openapi-generator-cli generate -i https://petstore.swagger.io/v2/swagger.json -g jmeter

cd ..
docker run --rm -it -p 8080:8080 -v ./test:/test jmeter


jmeter -n -t /path/to/your/test.jmx -l /path/to/save/results.csv
jmeter -p jmeter.properties -q user.properties

jmeter -p test.properties -n -t test/PetApi.jmx -l result.csv
```

