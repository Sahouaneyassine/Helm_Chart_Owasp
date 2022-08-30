# OWASP ZAP Helm Chart

## Introduction

OWASP ZAP Helm Chart is an owasp zap scan solution for Kubernetes. It allows you to perform a vulnerability analysis on a host using Kubernetes as the platform. It creates a CronJob who creates jobs on a repeating schedule and each job will deploy a pod that will scan the host for any vulnerabilities.

## Setup

The following shows how to perform an owasp zap scan using Kubernetes. There are two ways to deploy. Either use this Github project (Option A) or use a Helm repository (Option B) which is a little easier.


### Prequisite



# owasp1

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cronjob | object | `{"schedule":"* * * * *"}` | To schedule ou scan to run in a spesific time . |
| cronjob.schedule | string | `"* * * * *"` | The Cron value . |
| zapcli.cookies | object | `{"enabled":true,"key":null,"type":null,"value":"btn qkd"}` | To pass the cookies poop up if there is in our Login Page |
| zapcli.cookies.enabled | bool | `true` | enabled : if the login page have a pop up |
| zapcli.cookies.key | string | `nil` | key : get the button/input by ? < type value,id,name.. = value / > |
| zapcli.cookies.type | string | `nil` | type : to pass the pop up by < button,input key = value / > |
| zapcli.cookies.value | string | `"btn qkd"` | value : value of the key ? < type key = value / > |
| zapcli.cred | object | `{"password":"20112012","username":"ysahouane"}` | Login Credentials |
| zapcli.cred.password | string | `"20112012"` | pass : Password of the login page |
| zapcli.cred.username | string | `"ysahouane"` | user : Username of the login page |
| zapcli.duree | object | `{"value":"5"}` | Set A Max time for our scan  |
| zapcli.duree.value | string | `"5"` | Value of the Max time for our scan |
| zapcli.email | object | `{"password":"20112012Aa","receiver":"sahouaneyassine1999@gmail.com","sender":"sahouane.ensa@uhp.ac.ma"}` | Send Report as an Email |
| zapcli.email.password | string | `"20112012Aa"` | password : The password of SMTP server mail |
| zapcli.email.receiver | string | `"sahouaneyassine1999@gmail.com"` | receiver : The mail receiver of the Report |
| zapcli.email.sender | string | `"sahouane.ensa@uhp.ac.ma"` | sender : The SMTP User server mail |
| zapcli.fields | object | `{"key_field_password":"name","key_field_username":"name","value_field_password":"password","value_field_username":"email"}` | Get Fields of the Login page |
| zapcli.fields.key_field_password | string | `"name"` | key_field_password : < input key_field_password = value_field_password / > |
| zapcli.fields.key_field_username | string | `"name"` | key_field_username : < input key_field_username = value_field_username / >  |
| zapcli.fields.value_field_password | string | `"password"` | value_field_password : < input key_field_password = value_field_password / > |
| zapcli.fields.value_field_username | string | `"email"` | value_field_username : < input key_field_username = value_field_username / > |
| zapcli.image.pullPolicy | string | `"IfNotPresent"` | pullPolicy |
| zapcli.image.repository | string | `"yasssahouane/owasp_test"` | Repository  |
| zapcli.image.tag | string | `"finalmail0"` | Tag |
| zapcli.steps | object | `{"enabled":true,"key":null,"value":"btn slfl"}` | If the login page have 2-step login |
| zapcli.steps.enabled | bool | `true` | enabled : true/fasle if the login have 2 steps . |
| zapcli.steps.key | string | `nil` | key : get the button/input of the first page by ? < type  value,id,name.. = value / > . |
| zapcli.steps.value | string | `"btn slfl"` | value : < type key = value / >. |
| zapcli.submit | object | `{"key_field_submit":"class","submit_button_input":"input","value_field_submit":"btn btn-lg btn-primary float-right"}` | Get the Button to submit the form and log in |
| zapcli.submit.key_field_submit | string | `"class"` | key_field_submit : < button,input  key_field_submit = value_field_submit / > |
| zapcli.submit.submit_button_input | string | `"input"` | submit_button_input : < button,input key_field_submit = value_field_submit / > |
| zapcli.submit.value_field_submit | string | `"btn btn-lg btn-primary float-right"` | value_field_submit : < button,input  key_field_submit = value_field_submit / > |
| zapcli.target | object | `{"home":"https://authenticationtest.com/","loginpage":"https://authenticationtest.com/simpleFormAuth/"}` | information about The Target. |
| zapcli.target.home | string | `"https://authenticationtest.com/"` | home : URL of the Home page of website |
| zapcli.target.loginpage | string | `"https://authenticationtest.com/simpleFormAuth/"` | loginpage : URL of the Login page |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
