# OWASP ZAP Helm Chart

## Introduction

zzzOWASP ZAP Helm Chart is an owasp zap scan solution for Kubernetes. It allows you to perform a vulnerability analysis on a host using Kubernetes as the platform. It creates a CronJob who creates jobs on a repeating schedule and each job will deploy a pod that will scan the host for any vulnerabilities.

## Setup

The following shows how to perform an owasp zap scan using Kubernetes. There are two ways to deploy. Either use this Github project (Option A) or use a Helm repository (Option B) which is a little easier.


### Prequisite

### Option A - Deploy With GibHub Project

* Deploy the kube-owasp-zap chart with the values set for type of scan and target host.

```bash
> helm install owaspzap ./Helm_Chart_Owasp \
    --set cronjob.schedule="* * * * *" \
    --set zapcli.target.home="https://authenticationtest.com/" \
    --set zapcli.target.loginpage="https://authenticationtest.com/simpleFormAuth/" \
    --set zapcli.cred.username="simpleForm@authenticationtest.com" \
    --set zapcli.cred.password="pa$$w0rd" \
    --set zapcli.duree.value="5" \
    --set zapcli.fields.key_field_password="name" \
    --set zapcli.fields.key_field_username="name" \
    --set zapcli.fields.value_field_password="password" \
    --set zapcli.fields.value_field_username="email" \
    --set zapcli.submit.key_field_submit="class" \
    --set zapcli.submit.submit_button_input="input" \
    --set zapcli.submit.value_field_submit="btn btn-lg btn-primary float-right" \
    --set zapcli.steps.enabled=false \
    --set zapcli.steps.key= \
    --set zapcli.steps.value="btin" \
    --set zapcli.cookies.enabled=false \
    --set zapcli.cookies.key= \
    --set zapcli.cookies.type= \
    --set zapcli.cookies.value="sdf" \
    --set zapcli.email.sender="sahouane.ensa@uhp.ac.ma" \
    --set zapcli.email.password="20112012Aa" \
    --set zapcli.email.receiver="sahouaneyassine1999@gmail.com"
```


### Option B - Using Using Helm

* Add the Helm repository. Then install the chart.

```bash
> helm repo add owaspzap https://sahouaneyassine.github.io/Helm_Chart_Owasp

> helm install owaspzap owaspzap/owasp1 \
    --set cronjob.schedule="* * * * *" \
    --set zapcli.target.home="https://authenticationtest.com/" \
    --set zapcli.target.loginpage="https://authenticationtest.com/simpleFormAuth/" \
    --set zapcli.cred.username="simpleForm@authenticationtest.com" \
    --set zapcli.cred.password="pa$$w0rd" \
    --set zapcli.duree.value="5" \
    --set zapcli.fields.key_field_password="name" \
    --set zapcli.fields.key_field_username="name" \
    --set zapcli.fields.value_field_password="password" \
    --set zapcli.fields.value_field_username="email" \
    --set zapcli.submit.key_field_submit="class" \
    --set zapcli.submit.submit_button_input="input" \
    --set zapcli.submit.value_field_submit="btn btn-lg btn-primary float-right" \
    --set zapcli.steps.enabled=false \
    --set zapcli.steps.key= \
    --set zapcli.steps.value="btin" \
    --set zapcli.cookies.enabled=false \
    --set zapcli.cookies.key= \
    --set zapcli.cookies.type= \
    --set zapcli.cookies.value="sdf" \
    --set zapcli.email.sender="sahouane.ensa@uhp.ac.ma" \
    --set zapcli.email.password="20112012Aa" \
    --set zapcli.email.receiver="sahouaneyassine1999@gmail.com"
```

# owasp1

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Description | Default |
|-----|------|---------|-------------|
| cronjob | object | To schedule ou scan to run in a spesific time . | `{"schedule":?}` |
| cronjob.schedule | string | The Cron value . | `"* * * * *"` |
| zapcli.target | object | information about The Target site. | `{"home":?,"loginpage":?}` | 
| zapcli.target.home | string | home : URL of the Home page of website | `"https://authenticationtest.com/"` | 
| zapcli.target.loginpage | string | loginpage : URL of the Login page | `"https://authenticationtest.com/simpleFormAuth/"` | 
| zapcli.cred | object | Login Credentials | `{"password":?,"username":?}` |
| zapcli.cred.password | string | password : Password of the login page | `"20112012"` |
| zapcli.cred.username | string | username : Username of the login page | `"ysahouane"` | 
| zapcli.duree | object | Set A Max time for our scan  | `{"value":?}` | 
| zapcli.duree.value | string | Value of the Max time for our scan | `"5"` |
| zapcli.fields | object | Get Fields of the Login page | `{"key_field_password":?,"key_field_username":?,"value_field_password":?,"value_field_username":?}` | 
| zapcli.fields.key_field_password | string | __key_field_password__ : < input __key_field_password__ = value_field_password / > | `"name"` |
| zapcli.fields.key_field_username | string | __key_field_username__ : < input __key_field_username__ = value_field_username / >  | `"name"` | 
| zapcli.fields.value_field_password | string | __value_field_password__ : < input key_field_password = __value_field_password__ / > | `"password"` |
| zapcli.fields.value_field_username | string | __value_field_username__ : < input key_field_username = __value_field_username__ / > | `"email"` |
| zapcli.submit | object | Get the Button to submit the form and log in | `{"key_field_submit":?,"submit_button_input":?,"value_field_submit":?}` | 
| zapcli.submit.key_field_submit | string | __key_field_submit__ : < button,input  __key_field_submit__ = value_field_submit / > | `"class"` | 
| zapcli.submit.submit_button_input | string | __submit_button_input__ : < __button,input__  key_field_submit = value_field_submit / > | `"input"` |
| zapcli.submit.value_field_submit | string | __value_field_submit__ : < button,input  key_field_submit = __value_field_submit__ / > | `"btn btn-lg btn-primary float-right"` |
| zapcli.steps | object | If the login page have 2-step(pages) one for user other for pass | `{"enabled":?,"key":?,"value":?}` |
| zapcli.steps.enabled | bool | enabled : true/fasle if the login have 2 steps . | `true` |
| zapcli.steps.key | string | __key__ : get the button/input of the first page by ? < type  __value,id,name..__ = value / > . | `nil` |
| zapcli.steps.value | string | __value__ : < type key = __value__ / >. | `"btn slfl"` |
| zapcli.cookies | object | To pass the cookies poop up if there is one in our Login Page | `{"enabled":?,"key":?,"type":?,"value":?}` |
| zapcli.cookies.enabled | bool | enabled : if the login page have a pop up | `true` |
| zapcli.cookies.key | string | __key__ : get the button/input by ? < type __value,id,name..__ = value / > | `nil` |
| zapcli.cookies.type | string | __type__ : to pass the pop up by < __button,input__ key = value / > | `nil` |
| zapcli.cookies.value | string | __value__ : value of the key ? < type key = __value__ / > | `"btn qkd"` | 
| zapcli.email | object | Send Report as an Email | `{"sender":?,"password":?,"receiver":?}` | 
| zapcli.email.sender | string | sender : The SMTP server mail | `"sahouane.ensa@uhp.ac.ma"` | 
| zapcli.email.password | string | password : The password of SMTP server mail | `"20112012Aa"` | 
| zapcli.email.receiver | string | receiver : The mail of who will receive the report | `"sahouaneyassine1999@gmail.com"` |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
