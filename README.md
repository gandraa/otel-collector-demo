# OpenTelemetry Collector Contributions Demo 

*IMPORTANT:* GOOGLE_APPLICATION_CREDENTIALS has to be set in docker-compose file.

This demo presents the typical flow of observability data with multiple
OpenTelemetry Collectors deployed:

- Applications send data directly to a Collector ;
- The Collector sends the data to the appropriate backend, in this demo
 Jaeger, Zipkin, and Cloud Trace;

 The goal is to show how opentelemetry uses different app (Go, Java), receivers and exporters.

This demo uses `docker-compose` and by default runs against the 
`otel/opentelemetry-collector-contrib` image. To run the demo, switch
to the `examples/demo` folder and run:

```shell
docker-compose up -d
```

The demo exposes the following backends:

- Java at http://localhost:8081
- Golang - traces generated using jaeger-emitter and zipkin-emitter
- Jaeger at http://localhost:16686
- Zipkin at http://localhost:9411
- Cloud Trace https://console.cloud.google.com/traces

Notes:

To clean up any docker container from the demo run `docker-compose down` from 
the root folder.


