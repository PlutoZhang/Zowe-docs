# Verifying API Mediation Installation

Use your preferred REST API client to check the value of the status variable of the API Catalog service that is routed through the API Gateway on the following URL:  

```
https://hostName:basePort/api/v1/caapicatalog/application/state
```
The hostName is set during install, and basePort is set as the gatewayHttpsPort parameter.

In the following example, the curl tool utility is used to invoke API Mediation Layer endpoint and grep utility to parse out the responce status variable value:

```
$ curl -v -k --silent https://hostName:basePort/api/v1/caapicatalog/application/state 2>&1 | grep -Po '(?<=\"status\"\:\")[^\"]+'
UP
```
The "UP" reposponce confirms that API Mediation Layer runs properly.