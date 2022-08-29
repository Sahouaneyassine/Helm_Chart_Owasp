# owasp1

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| cronjob | object | `{"schedule":"* * * * *"}` | To schedule ou scan to run in a spesific time . |
| cronjob.schedule | string | `"* * * * *"` | The Cron value . |
| fullnameOverride | string | `"owasp-chart"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"nginx"` |  |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts | list | `[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | kubernetes.io/tls-acme: "true" |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `"owasp-app"` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| pv.accessmode | string | `"ReadWriteOnce"` |  |
| pv.name | string | `"task-pv-volume"` |  |
| pv.path | string | `"/mnt/data"` |  |
| pv.storage | string | `"1Gi"` |  |
| pv.storageClassName | string | `"manual"` |  |
| pvc.accessmode | string | `"ReadWriteOnce"` |  |
| pvc.capacity | string | `"1Gi"` |  |
| pvc.name | string | `"task-pv-claim"` |  |
| pvc.storageClassName | string | `"manual"` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |
| zapcli.configfile.name | string | `"gen.conf"` |  |
| zapcli.cookies | object | `{"enabled":true,"key":null,"type":null,"value":"btn qkd"}` | If the login page have a cookies pop up |
| zapcli.cookies.enabled | bool | `true` | enabled : if the login have a pop up |
| zapcli.cookies.key | string | `nil` | key : get the button/input by ? value,id,name... |
| zapcli.cookies.type | string | `nil` | type : to pass the pop up by <type> ? button,input |
| zapcli.cookies.value | string | `"btn qkd"` | value : <type key=value> |
| zapcli.cred | object | `{"password":"20112012","username":"ysahouane"}` | Login Credentials |
| zapcli.cred.password | string | `"20112012"` | pass : Password of the login page |
| zapcli.cred.username | string | `"ysahouane"` | user : Username of the login page |
| zapcli.debug.enabled | bool | `false` |  |
| zapcli.duree | object | `{"value":"5"}` | Set A Max time for our scan  |
| zapcli.duree.value | string | `"5"` | Value of the Max time for our scan |
| zapcli.email | object | `{"password":"20112012Aa","receiver":"sahouaneyassine1999@gmail.com","sender":"sahouane.ensa@uhp.ac.ma"}` | Send Report as an Email |
| zapcli.email.password | string | `"20112012Aa"` | password : The password of SMTP server mail |
| zapcli.email.receiver | string | `"sahouaneyassine1999@gmail.com"` | receiver : The mail receiver of the Report |
| zapcli.email.sender | string | `"sahouane.ensa@uhp.ac.ma"` | sender : The SMTP User server mail |
| zapcli.fields | object | `{"key_field_password":"name","key_field_username":"name","value_field_password":"password","value_field_username":"email"}` | Get Fields of the Login page |
| zapcli.fields.key_field_password | string | `"name"` | key_field_password  : <input key=value> |
| zapcli.fields.key_field_username | string | `"name"` | key_field_username  : <input key=value> |
| zapcli.fields.value_field_password | string | `"password"` | value_field_password  : <input key=value> |
| zapcli.fields.value_field_username | string | `"email"` | value_field_username  : <input key=value> |
| zapcli.image | object | `{"pullPolicy":"IfNotPresent","repository":"yasssahouane/owasp_test","tag":"finalmail0"}` | Image to use for OWASP ZAP Scan container |
| zapcli.image.pullPolicy | string | `"IfNotPresent"` | pullPolicy |
| zapcli.image.repository | string | `"yasssahouane/owasp_test"` | Repository  |
| zapcli.image.tag | string | `"finalmail0"` | Tag |
| zapcli.report.name | string | `"report.html"` |  |
| zapcli.steps | object | `{"enabled":true,"key":null,"value":"btn slfl"}` | If the login page have 2-step login |
| zapcli.steps.enabled | bool | `true` | enabled : if the login have 2 steps |
| zapcli.steps.key | string | `nil` | key : get the button/input of the first page by ? value,id,name... |
| zapcli.steps.value | string | `"btn slfl"` | value : <type key=value> |
| zapcli.submit | object | `{"key_field_submit":"class","submit_button_input":"input","value_field_submit":"btn btn-lg btn-primary float-right"}` | Get the Button to submit the form and log in |
| zapcli.submit.key_field_submit | string | `"class"` | key_field_submit : <button/input  key_field_submit=value_field_submit/> |
| zapcli.submit.submit_button_input | string | `"input"` | submit_button_input : button?input , <input> or <button> |
| zapcli.submit.value_field_submit | string | `"btn btn-lg btn-primary float-right"` | value_field_submit : <button/input  key_field_submit=value_field_submit/> |
| zapcli.target | object | `{"home":"https://authenticationtest.com/","loginpage":"https://authenticationtest.com/simpleFormAuth/"}` | information about a scan. |
| zapcli.target.home | string | `"https://authenticationtest.com/"` | home : URL of the Home page of website |
| zapcli.target.loginpage | string | `"https://authenticationtest.com/simpleFormAuth/"` | loginpage : URL of the Login page |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
