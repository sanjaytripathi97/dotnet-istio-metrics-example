# Create a new OpenShift project
$ oc new-project mydemo

# Add the .NET Core application
$ oc new-app dotnet:7.0-ubi8~https://gitlab.cee.redhat.com/milang/dotnet-metrics-app.git --context-dir PrometheusNetDemo

# Make the .NET Core application accessible externally and show the url
$ oc expose service s2i-dotnetcore-ex
$ oc get route s2i-dotnetcore-ex

# check the application

```
curl ${ROUTE}/WeatherForecast
curl ${ROUTE}/metrics
```
