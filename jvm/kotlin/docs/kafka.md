# kafka

## [Common Application Properties](https://docs.spring.io/spring-boot/docs/current/reference/html/application-properties.html)

| Name                                                  | Description                                                                                                                                                                  | Default Value                                |
|-------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| spring.kafka.admin.auto-create                        | Whether to automatically create topics during context initialization. When set to false, disables automatic topic creation during context initialization.                    | true                                         |
| spring.kafka.admin.client-id                          | ID to pass to the server when making requests. Used for server-side logging.                                                                                                 |                                              |
| spring.kafka.admin.close-timeout                      | Close timeout.                                                                                                                                                               |                                              |
| spring.kafka.admin.fail-fast                          | Whether to fail fast if the broker is not available on startup.                                                                                                              | false                                        |
| spring.kafka.admin.modify-topic-configs               | Whether to enable modification of existing topic configuration.                                                                                                              | false                                        |
| spring.kafka.admin.operation-timeout                  | Operation timeout.                                                                                                                                                           |                                              |
| spring.kafka.admin.properties.*                       | Additional admin-specific properties used to configure the client.                                                                                                           |                                              |
| spring.kafka.admin.security.protocol                  | Security protocol used to communicate with brokers.                                                                                                                          |                                              |
| spring.kafka.admin.ssl.key-password                   | Password of the private key in either key store key or key store file.                                                                                                       |                                              |
| spring.kafka.admin.ssl.key-store-certificate-chain    | Certificate chain in PEM format with a list of X.509 certificates.                                                                                                           |                                              |
| spring.kafka.admin.ssl.key-store-key                  | Private key in PEM format with PKCS#8 keys.                                                                                                                                  |                                              |
| spring.kafka.admin.ssl.key-store-location             | Location of the key store file.                                                                                                                                              |                                              |
| spring.kafka.admin.ssl.key-store-password             | Store password for the key store file.                                                                                                                                       |                                              |
| spring.kafka.admin.ssl.key-store-type                 | Type of the key store.                                                                                                                                                       |                                              |
| spring.kafka.admin.ssl.protocol                       | SSL protocol to use.                                                                                                                                                         |                                              |
| spring.kafka.admin.ssl.trust-store-certificates       | Trusted certificates in PEM format with X.509 certificates.                                                                                                                  |                                              |
| spring.kafka.admin.ssl.trust-store-location           | Location of the trust store file.                                                                                                                                            |                                              |
| spring.kafka.admin.ssl.trust-store-password           | Store password for the trust store file.                                                                                                                                     |                                              |
| spring.kafka.admin.ssl.trust-store-type               | Type of the trust store.                                                                                                                                                     |                                              |
| spring.kafka.bootstrap-servers                        | Comma-delimited list of host:port pairs to use for establishing the initial connections to the Kafka cluster. Applies to all components unless overridden.                   |                                              |
| spring.kafka.client-id                                | ID to pass to the server when making requests. Used for server-side logging.                                                                                                 |                                              |
| spring.kafka.consumer.auto-commit-interval            | Frequency with which the consumer offsets are auto-committed to Kafka if 'enable.auto.commit' is set to true.                                                                |                                              |
| spring.kafka.consumer.auto-offset-reset               | What to do when there is no initial offset in Kafka or if the current offset no longer exists on the server.                                                                 |                                              |
| spring.kafka.consumer.bootstrap-servers               | Comma-delimited list of host:port pairs to use for establishing the initial connections to the Kafka cluster. Overrides the global property, for consumers.                  |                                              |
| spring.kafka.consumer.client-id                       | ID to pass to the server when making requests. Used for server-side logging.                                                                                                 |                                              |
| spring.kafka.consumer.enable-auto-commit              | Whether the consumer's offset is periodically committed in the background.                                                                                                   |                                              |
| spring.kafka.consumer.fetch-max-wait                  | Maximum amount of time the server blocks before answering the fetch request if there isn't sufficient data to immediately satisfy the requirement given by "fetch-min-size". |                                              |
| spring.kafka.consumer.fetch-min-size                  | Minimum amount of data the server should return for a fetch request.                                                                                                         |                                              |
| spring.kafka.consumer.group-id                        | Unique string that identifies the consumer group to which this consumer belongs.                                                                                             |                                              |
| spring.kafka.consumer.heartbeat-interval              | Expected time between heartbeats to the consumer coordinator.                                                                                                                |                                              |
| spring.kafka.consumer.isolation-level                 | Isolation level for reading messages that have been written transactionally.                                                                                                 | read-uncommitted                             |
| spring.kafka.consumer.key-deserializer                | Deserializer class for keys.                                                                                                                                                 |                                              |
| spring.kafka.consumer.max-poll-records                | Maximum number of records returned in a single call to poll().                                                                                                               |                                              |
| spring.kafka.consumer.properties.*                    | Additional consumer-specific properties used to configure the client.                                                                                                        |                                              |
| spring.kafka.consumer.security.protocol               | Security protocol used to communicate with brokers.                                                                                                                          |                                              |
| spring.kafka.consumer.ssl.key-password                | Password of the private key in either key store key or key store file.                                                                                                       |                                              |
| spring.kafka.consumer.ssl.key-store-certificate-chain | Certificate chain in PEM format with a list of X.509 certificates.                                                                                                           |                                              |
| spring.kafka.consumer.ssl.key-store-key               | Private key in PEM format with PKCS#8 keys.                                                                                                                                  |                                              |
| spring.kafka.consumer.ssl.key-store-location          | Location of the key store file.                                                                                                                                              |                                              |
| spring.kafka.consumer.ssl.key-store-password          | Store password for the key store file.                                                                                                                                       |                                              |
| spring.kafka.consumer.ssl.key-store-type              | Type of the key store.                                                                                                                                                       |                                              |
| spring.kafka.consumer.ssl.protocol                    | SSL protocol to use.                                                                                                                                                         |                                              |
| spring.kafka.consumer.ssl.trust-store-certificates    | Trusted certificates in PEM format with X.509 certificates.                                                                                                                  |                                              |
| spring.kafka.consumer.ssl.trust-store-location        | Location of the trust store file.                                                                                                                                            |                                              |
| spring.kafka.consumer.ssl.trust-store-password        | Store password for the trust store file.                                                                                                                                     |                                              |
| spring.kafka.consumer.ssl.trust-store-type            | Type of the trust store.                                                                                                                                                     |                                              |
| spring.kafka.consumer.value-deserializer              | Deserializer class for values.                                                                                                                                               |                                              |
| spring.kafka.jaas.control-flag                        | Control flag for login configuration.                                                                                                                                        | required                                     |
| spring.kafka.jaas.enabled                             | Whether to enable JAAS configuration.                                                                                                                                        | false                                        |
| spring.kafka.jaas.login-module                        | Login module.                                                                                                                                                                | com.sun.security.auth.module.Krb5LoginModule |
| spring.kafka.jaas.options.*                           | Additional JAAS options.                                                                                                                                                     |                                              |
| spring.kafka.listener.ack-count                       | Number of records between offset commits when ackMode is "COUNT" or "COUNT_TIME".                                                                                            |                                              |
| spring.kafka.listener.ack-mode                        | Listener AckMode. See the spring-kafka documentation.                                                                                                                        |                                              |
| spring.kafka.listener.ack-time                        | Time between offset commits when ackMode is "TIME" or "COUNT_TIME".                                                                                                          |                                              |
| spring.kafka.listener.async-acks                      | Support for asynchronous record acknowledgements. Only applies when spring.kafka.listener.ack-mode is manual or manual-immediate.                                            |                                              |
| spring.kafka.listener.auto-startup                    | Whether to auto start the container.                                                                                                                                         | true                                         |
| spring.kafka.listener.client-id                       | Prefix for the listener's consumer client.id property.                                                                                                                       |                                              |
| spring.kafka.listener.concurrency                     | Number of threads to run in the listener containers.                                                                                                                         |                                              |
| spring.kafka.listener.idle-between-polls              | Sleep interval between Consumer.poll(Duration) calls.                                                                                                                        | 0                                            |
| spring.kafka.listener.idle-event-interval             | Time between publishing idle consumer events (no data received).                                                                                                             |                                              |
| spring.kafka.listener.idle-partition-event-interval   | Time between publishing idle partition consumer events (no data received for partition).                                                                                     |                                              |
| spring.kafka.listener.immediate-stop                  | Whether the container stops after the current record is processed or after all the records from the previous poll are processed.                                             | false                                        |
| spring.kafka.listener.log-container-config            | Whether to log the container configuration during initialization (INFO level).                                                                                               |                                              |
| spring.kafka.listener.missing-topics-fatal            | Whether the container should fail to start if at least one of the configured topics are not present on the broker.                                                           | false                                        |
| spring.kafka.listener.monitor-interval                | Time between checks for non-responsive consumers. If a duration suffix is not specified, seconds will be used.                                                               |                                              |
| spring.kafka.listener.no-poll-threshold               | Multiplier applied to "pollTimeout" to determine if a consumer is non-responsive.                                                                                            |                                              |
| spring.kafka.listener.poll-timeout                    | Timeout to use when polling the consumer.                                                                                                                                    |                                              |
| spring.kafka.listener.type                            | Listener type.                                                                                                                                                               | single                                       |
| spring.kafka.producer.acks                            | Number of acknowledgments the producer requires the leader to have received before considering a request complete.                                                           |                                              |
| spring.kafka.producer.batch-size                      | Default batch size. A small batch size will make batching less common and may reduce throughput (a batch size of zero disables batching entirely).                           |                                              |
| spring.kafka.producer.bootstrap-servers               | Comma-delimited list of host:port pairs to use for establishing the initial connections to the Kafka cluster. Overrides the global property, for producers.                  |                                              |
| spring.kafka.producer.buffer-memory                   | Total memory size the producer can use to buffer records waiting to be sent to the server.                                                                                   |                                              |
| spring.kafka.producer.client-id                       | ID to pass to the server when making requests. Used for server-side logging.                                                                                                 |                                              |
| spring.kafka.producer.compression-type                | Compression type for all data generated by the producer.                                                                                                                     |                                              |
| spring.kafka.producer.key-serializer                  | Serializer class for keys.                                                                                                                                                   |                                              |
| spring.kafka.producer.properties.*                    | Additional producer-specific properties used to configure the client.                                                                                                        |                                              |
| spring.kafka.producer.retries                         | When greater than zero, enables retrying of failed sends.                                                                                                                    |                                              |
| spring.kafka.producer.security.protocol               | Security protocol used to communicate with brokers.                                                                                                                          |                                              |
| spring.kafka.producer.ssl.key-password                | Password of the private key in either key store key or key store file.                                                                                                       |                                              |
| spring.kafka.producer.ssl.key-store-certificate-chain | Certificate chain in PEM format with a list of X.509 certificates.                                                                                                           |                                              |
| spring.kafka.producer.ssl.key-store-key               | Private key in PEM format with PKCS#8 keys.                                                                                                                                  |                                              |
| spring.kafka.producer.ssl.key-store-location          | Location of the key store file.                                                                                                                                              |                                              |
| spring.kafka.producer.ssl.key-store-password          | Store password for the key store file.                                                                                                                                       |                                              |
| spring.kafka.producer.ssl.key-store-type              | Type of the key store.                                                                                                                                                       |                                              |
| spring.kafka.producer.ssl.protocol                    | SSL protocol to use.                                                                                                                                                         |                                              |
| spring.kafka.producer.ssl.trust-store-certificates    | Trusted certificates in PEM format with X.509 certificates.                                                                                                                  |                                              |
| spring.kafka.producer.ssl.trust-store-location        | Location of the trust store file.                                                                                                                                            |                                              |
| spring.kafka.producer.ssl.trust-store-password        | Store password for the trust store file.                                                                                                                                     |                                              |
| spring.kafka.producer.ssl.trust-store-type            | Type of the trust store.                                                                                                                                                     |                                              |
| spring.kafka.producer.transaction-id-prefix           | When non empty, enables transaction support for producer.                                                                                                                    |                                              |
| spring.kafka.producer.value-serializer                | Serializer class for values.                                                                                                                                                 |                                              |
| spring.kafka.properties.*                             | Additional properties, common to producers and consumers, used to configure the client.                                                                                      |                                              |
| spring.kafka.retry.topic.attempts                     | Total number of processing attempts made before sending the message to the DLT.                                                                                              | 3                                            |
| spring.kafka.retry.topic.delay                        | Canonical backoff period. Used as an initial value in the exponential case, and as a minimum value in the uniform case.                                                      | 1s                                           |
| spring.kafka.retry.topic.enabled                      | Whether to enable topic-based non-blocking retries.                                                                                                                          | false                                        |
| spring.kafka.retry.topic.max-delay                    | Maximum wait between retries. If less than the delay then the default of 30 seconds is applied.                                                                              | 0                                            |
| spring.kafka.retry.topic.multiplier                   | Multiplier to use for generating the next backoff delay.                                                                                                                     | 0                                            |
| spring.kafka.retry.topic.random-back-off              | Whether to have the backoff delays.                                                                                                                                          | false                                        |
| spring.kafka.security.protocol                        | Security protocol used to communicate with brokers.                                                                                                                          |                                              |
| spring.kafka.ssl.key-password                         | Password of the private key in either key store key or key store file.                                                                                                       |                                              |
| spring.kafka.ssl.key-store-certificate-chain          | Certificate chain in PEM format with a list of X.509 certificates.                                                                                                           |                                              |
| spring.kafka.ssl.key-store-key                        | Private key in PEM format with PKCS#8 keys.                                                                                                                                  |                                              |
| spring.kafka.ssl.key-store-location                   | Location of the key store file.                                                                                                                                              |                                              |
| spring.kafka.ssl.key-store-password                   | Store password for the key store file.                                                                                                                                       |                                              |
| spring.kafka.ssl.key-store-type                       | Type of the key store.                                                                                                                                                       |                                              |
| spring.kafka.ssl.protocol                             | SSL protocol to use.                                                                                                                                                         |                                              |
| spring.kafka.ssl.trust-store-certificates             | Trusted certificates in PEM format with X.509 certificates.                                                                                                                  |                                              |
| spring.kafka.ssl.trust-store-location                 | Location of the trust store file.                                                                                                                                            |                                              |
| spring.kafka.ssl.trust-store-password                 | Store password for the trust store file.                                                                                                                                     |                                              |
| spring.kafka.ssl.trust-store-type                     | Type of the trust store.                                                                                                                                                     |                                              |
| spring.kafka.streams.application-id                   | Kafka streams application.id property; default spring.application.name.                                                                                                      |                                              |
| spring.kafka.streams.auto-startup                     | Whether to auto-start the streams factory bean.                                                                                                                              | true                                         |
| spring.kafka.streams.bootstrap-servers                | Comma-delimited list of host:port pairs to use for establishing the initial connections to the Kafka cluster. Overrides the global property, for streams.                    |                                              |
| spring.kafka.streams.cleanup.on-shutdown              | Cleanup the application’s local state directory on shutdown.                                                                                                                 | false                                        |
| spring.kafka.streams.cleanup.on-startup               | Cleanup the application’s local state directory on startup.                                                                                                                  | false                                        |
| spring.kafka.streams.client-id                        | ID to pass to the server when making requests. Used for server-side logging.                                                                                                 |                                              |
| spring.kafka.streams.properties.*                     | Additional Kafka properties used to configure the streams.                                                                                                                   |                                              |
| spring.kafka.streams.replication-factor               | The replication factor for change log topics and repartition topics created by the stream processing application.                                                            |                                              |
| spring.kafka.streams.security.protocol                | Security protocol used to communicate with brokers.                                                                                                                          |                                              |
| spring.kafka.streams.ssl.key-password                 | Password of the private key in either key store key or key store file.                                                                                                       |                                              |
| spring.kafka.streams.ssl.key-store-certificate-chain  | Certificate chain in PEM format with a list of X.509 certificates.                                                                                                           |                                              |
| spring.kafka.streams.ssl.key-store-key                | Private key in PEM format with PKCS#8 keys.                                                                                                                                  |                                              |
| spring.kafka.streams.ssl.key-store-location           | Location of the key store file.                                                                                                                                              |                                              |
| spring.kafka.streams.ssl.key-store-password           | Store password for the key store file.                                                                                                                                       |                                              |
| spring.kafka.streams.ssl.key-store-type               | Type of the key store.                                                                                                                                                       |                                              |
| spring.kafka.streams.ssl.protocol                     | SSL protocol to use.                                                                                                                                                         |                                              |
| spring.kafka.streams.ssl.trust-store-certificates     | Trusted certificates in PEM format with X.509 certificates.                                                                                                                  |                                              |
| spring.kafka.streams.ssl.trust-store-location         | Location of the trust store file.                                                                                                                                            |                                              |
| spring.kafka.streams.ssl.trust-store-password         | Store password for the trust store file.                                                                                                                                     |                                              |
| spring.kafka.streams.ssl.trust-store-type             | Type of the trust store.                                                                                                                                                     |                                              |
| spring.kafka.streams.state-dir                        | Directory location for the state store.                                                                                                                                      |                                              |
| spring.kafka.streams.state-store-cache-max-size       | Maximum size of the in-memory state store cache across all threads.                                                                                                          |                                              |
| spring.kafka.template.default-topic                   | Default topic to which messages are sent.                                                                                                                                    |                                              |
| spring.kafka.template.transaction-id-prefix           | Transaction id prefix, override the transaction id prefix in the producer factory.                                                                                           |