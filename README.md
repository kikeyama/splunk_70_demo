# splunk_70_demo

## Dashboards
**Metrics Performance (`metrics_performance`)**  
**Splunk 7.0 Visualizations (`splunk_70_visualizations`)**

## Indexes
**metrics**  
Index for Metric Store which doesn't have `splitByIndexKeys` parameter.

**metrics_hash**  
Index for Metric Store with `splitByIndexKeys` parameter. It enables bucket split by specified field(s).  
See http://docs.splunk.com/Documentation/Splunk/latest/Admin/indexesconf

**collectd_event**  
Index for Event Store. This is used  for performance comparison to Metric Store in `metrics_performance` dashboard.

## Sourcetypes
**collectd_json**  
Sourcetype for collectd as Event Store. It should be used with `collectd_event` index.

## How to use?
`metrics_performance` shows metric search performance that is obtained from collectd. To enable dashboard, collectd is installed and configured in other servers. Since Splunk aggregate metrics from collectd via HTTP Event Collector (HEC), enable HEC and create HEC data inputs with specifying index and sourcetype.

`splunk_70_visualizations` shows Event Annotations and Compare Series. To enable Event Annotation, install Universal Forwarder into the server which generates metrics from collectd. Otherwise, Event Annotation by internal logs is available.

