# Observability

Building observable systems enables development teams at CSE to measure how well the application is behaving.

## Goals

1. Provide holistic view on the health of the application.
2. Help measure business performance for the customer.
3. Measure operational performance of the system.
4. Identify and diagnose failures to get to the problem fast.

## Pillars of Observability

1. [Logging](pillars.md#Logging)
2. [Tracing](pillars.md#Tracing)
3. [Metrics](pillars.md#Metrics)

## Recommended Practices

1. **Correlation Id**: Include unique identifier at the start of the interaction to tie down aggregated data from various system components and provide a holistic view. Read more guidelines about using [correlation id](correlation-id.md).
2. Ensure health of the services are **monitored** and provide insights into system's performance and behavior.
3. **Faults, crashes, and failures** are logged as discrete events. This helps engineers identify problem area(s) during failures.
4. Ensure logging configuration (eg: setting logging to "verbose") can be controlled without code changes.
5. Ensure that **metrics** around latency and duration are collected and can be aggregated.
6. Don't attempt to monitor everything. If the data is not actionable, it is useless and becomes noise.
7. As a general rule, do not log any customer sensitive and Personal Identifiable Information (PII). Ensure any pertinent privacy regulations are followed regarding PII (Ex: GDPR etc.,)
8. Start small and add where there is customer impact.

## What is collected

1. **Latency**: Time taken to service a request.
2. **Traffic**: Measurement of how much demand is placed on the system, typically number of requests per second.
3. **Errors**: Errors, application faults and traces with adequate information on error messages.
4. Identify a unique value (correlation identifier) that will be consistently tagged with data.

In addition to above, engineers are encouraged to have conversations to understand other logs, metrics, data that adds value to the customer.

## Recommended Tools and Approaches

### Tools

1. [Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/overview) - Umbrella of services including system metrics, log analytics and more.
2. [Application Insights](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview) - An extensible Application Performance Management (APM) service used to monitor live applications, and a feature of inside Azure Monitor.
3. [Azure Log Analytics](https://docs.microsoft.com/en-us/azure/azure-monitor/log-query/log-query-overview) - Run advanced queries against the data collected via Azure Monitor Logs.

### Collection

There are many ways to collect data; here are three generally accepted methods:

#### 1. Agent:

In most cloud-oriented applications, logs and other types of telemetry data are treated as streams of data; sometimes, those streams might be accessible as files, or something else. Many times, it would be [`STDOUT`](https://en.wikipedia.org/wiki/Standard_streams). An agent collector is executed as a daemon, a standalone application, or a container, and consumes these streams and forwards them to the system of record.

Agents are an acceptable way of collecting data as they run in their own address space. They also hide away a lot of the configuration and implementation needed to make the logs available in the system of record and take care of things like buffering entries while the network is down or the system is unreachable, retries, circuit breaking, etc.

All of the above doesn't mean that using agents is flawless; the applications reporting data do not know the state of the agent, and if the data is forwarded correctly or not.

Some examples:

- Log Analytics Agent: runs as an app or as a container and forwards logs and metrics to Azure Monitor. Buffers data temporarily in case of network disconnection or if the service is down.
- Fluent Bit: runs as an app or as a container and forward logs (and other data) to other systems. Its plug-in architecture enables forwarding data to different systems of record.
- Logstash: ingest logs and forwards them to a system of record while enabling data transformations in the process.

#### 2. SDK:

An SDK collector is usually one that is included in the application for instrumentation and transmits the data (logs or telemetry) directly to the system of record. Given this nature, SDKs have more information about the context and state of the application that might not be available while using an agent as they are disconnected from each other.

SDKs are also easy to set up since there's no need to configure any other component, and since they can push data directly to the system of record. Given this nature, they are great to collect information from the edge, for example, from a website or a mobile app.

SDKs are usually distributed as libraries by vendors, which behind the scenes take care of handling all things related to IO, including retries, buffering of data in case there's a network failure, etc. Still, contrary to agents, SDKs share the same (limited) resources as the application (memory, CPU, network bandwidth). All the above means the footprint of using an SDK for telemetry might vary from one app to another based on the amount of data collected.

Some Examples:

- Application Insights SDK for .Net, Java, etc.
- Open Census SDK (soon to become Open Telemetry) an effort by multiple tech companies (including Microsoft) to create a standard for instrumenting applications.

#### 3. SDK-Agent:

This method is a hybrid approach that merges an SDK and an agent. The SDK is part of the application, and it enables the instrumentation of data as desired. This data is then exposed by the application, not sent directly to the system of record via an endpoint, a file, or another mechanism. In the background, an agent is consuming the exposed data and forwarding it to the system of record.

Some Examples:

- Prometheus SDK + Log Analytics Agent: the Prometheus SDK exposes an endpoint with metrics, and the Log Analytics Agent forward them to Azure Monitor.

## Recipes

Links to GitHub posts - Coming soon
