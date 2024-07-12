## Installing app in new project teama without permissions

### E1
InvalidSpecError
application destination server 'https://kubernetes.default.svc' and namespace 'webapp-appset' do not match any of the allowed destinations in project 'teama'

*Resolution*
Grant permissions at the project "teama" level

### E2
InvalidSpecError
application repo https://github.com/devopsjourney1/helm-webapp.git is not permitted in project 'teama'

*Resolution*
Add the github repo in the argocd project source repo section.

### E3
SharedResourceWarning
Deployment/myhelmapp is part of applications argocd-customer/webapp1 and webapp

*Resolution*
https://github.com/argoproj/argo-cd/issues/11838


### E4
Failed sync attempt to 76633fe8488da6f7d7cc4774d35e9c2316fe0a2e: InvalidSpecError: application destination server 'https://kubernetes.default.svc' and namespace 'webapp-appset' do not match any of the allowed destinations in project 'teama';InvalidSpecError: application repo https://github.com/devopsjourney1/helm-webapp.git is not permitted in project 'teama'

*Resolution*


### E5
Unable to edit project: invalid policy rule 'p, proj:teama:test, applications, get, teama/*, allow': policy subject must be: 'proj:teama:viewOnly', not 'proj:teama:test'

*Resolution*
It worked on argo-server restart

