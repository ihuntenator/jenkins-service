# Jenkins - automated setup with docker-compose and JCasC


## Start Jenkins 

```
docker compose up -d
```

## Access Jenkins

| URL | http://localhost:8080 |
| User | admin |
| Password | |

## Stop Jenkins

```
docker compose down
```

## List Plugins

```
JENKINS_HOST=username:password@localhost:8080
curl -sSL "http://$JENKINS_HOST/pluginManager/api/xml?depth=1&xpath=/*/*/shortName|/*/*/version&wrapper=plugins" | perl -pe 's/.*?<shortName>([\w-]+).*?<version>([^<]+)()(<\/\w+>)+/\1 \2\n/g'|sed 's/ /:/'
```


## References

 * https://www.digitalocean.com/community/tutorials/how-to-automate-jenkins-setup-with-docker-and-jenkins-configuration-as-code
 * https://www.jenkins.io/download/
 * https://github.com/jenkinsci/docker/blob/master/README.md
 * https://www.jenkins.io/doc/book/pipeline/
 * https://www.jenkins.io/doc/book/pipeline/pipeline-best-practices/
 * https://www.jenkins.io/doc/book/pipeline/syntax/ 
 * https://cloudacademy.com/course/jenkins-cicd/install-jenkins-docker-compose/
