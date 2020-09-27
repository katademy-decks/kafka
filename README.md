# kafka-faq

<details>
<summary>When a _____ detects a quota violation, it computes and returns the amount of delay needed to bring the violating client under its quota. It then _____ to the client, refusing to process requests from it until the delay is over. The client will also refrain from sending further requests to the broker during the delay.&nbsp;</summary>
broker&nbsp;
mutes the channel bi-directionally
<br></details>

<details>
<summary>For any Linux filesystem used for data directories, enabling the _____ option is recommended, as it disables updating of a file's atime (last access time) attribute when the file is read. This can eliminate a significant number of filesystem writes, as Kafka does not rely on the atime attributes at all.</summary>
noatime
<br></details>

<details>
<summary>Could you use an asynchronous workflow to do expensive work (such as periodic data aggregation) in advance?</summary>
Yes
<br></details>

<details>
<summary>Can message queues receive messages?</summary>
Yes
<br></details>

<details>
<summary>Can message queues hold messages?</summary>
Yes
<br></details>

<details>
<summary>Can message queues deliver messages?</summary>
Yes
<br></details>

<details>
<summary>Can Redis be used as a message broker?</summary>
Yes
<br></details>

<details>
<summary>Can messages be lost in a Redis message broker?</summary>
Yes
<br></details>

<details>
<summary>An application publishes a job to a message queue, then notifies the user of the job status. A _____ picks up the job from the queue, processes it, then signals its completion.</summary>
worker
<br></details>

<details>
<summary>In asynchronous workflows, jobs are processed in the _____ without blocking the user. For example, a tweet can instantly appear on your timeline, but could take some time before it is actually delivered to followers.</summary>
background
<br></details>

<details>
<summary>Can queues add delays to operations?</summary>
Yes
<br></details>

<details>
<summary>When dealing with many inexpensive or realtime operations, are queues a good use case?</summary>
They can be, but they can introduce delay and complexity compared to synchronous execution.
<br></details>

<details>
<summary>A queue has grown significantly, becoming larger than available memory. What are some problems that may appear?</summary>
Cache misses, disk reads, slower performance
<br></details>

<details>
<summary>_____ pressure limits queue sizes, allowing for good throughput / latency for jobs already in the queue. Once filled, the queue's clients are asked to try again later.</summary>
Back pressure
<br></details>

<details>
<summary>What protocol is used in RabbitMQ message queues?</summary>
AMQP
<br></details>

<details>
<summary>Scheduled _____ queues receive tasks, run them and deliver the results.</summary>
Task queues
<br></details>

<details>
<summary>Are real-time payments and financial transactions a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Is real-time shipment/logistics monitoring&nbsp;a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Is real-time IoT device monitoring&nbsp;a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Is user interaction telemetry a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Is microservice implementation a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Kafka's three key capabilities are:
To _____/_____ to streams of events
To _____ streams of events durably, reliably and indefinitely.
To _____ streams of events, as they occur or retrospectively.</summary>
publish / subscribe
store
process
<br></details>

<details>
<summary>Can Kafka implement continous import/export of your data from/to other systems?</summary>
Yes
<br></details>

<details>
<summary>Kafka is run as a cluster of one or more servers that can span multiple datacenters or cloud regions. Some of these servers form the storage layer, called the _____.&nbsp;</summary>
brokers
<br></details>

<details>
<summary>If a Kafka server fails, the other servers will _____ to ensure continuous operations without any data loss.</summary>
take over its work
<br></details>

<details>
<summary>Reading / writing data to Kafka is done in the form of _____.&nbsp;</summary>
events
<br></details>

<details>
<summary>An event consists of:<ul><li>_____: "Alice"</li><li>_____: "Made a payment of $200 to Bob"</li><li>_____: "Jun. 25, 2020 at 2:06 p.m."</li><li>_____ (optional)</li></ul></summary>
a key
a value
a timestamp

metadata (optional)
<br></details>

<details>
<summary><b>_____&nbsp;</b>are client applications that publish (write) events to Kafka</summary>
Producers.
<br></details>

<details>
<summary>_____ are clients that subscribe to (read and process) Kafka events.</summary>
<strong>consumers</strong>
<br></details>

<details>
<summary>Do produces sometimes need to wait for consumers by design?</summary>
No - they are fully decoupled
<br></details>

<details>
<summary>Does Kafka provide the ability to process an event exactly once?</summary>
Yes -&nbsp;<a href="https://kafka.apache.org/documentation/#intro_guarantees">guarantees</a>&nbsp;it.
<br></details>

<details>
<summary>Events are organized and durably stored in <b>_____</b>, similar to files stored in a folder.</summary>
<strong>topics</strong>
<br></details>

<details>
<summary>An example _____ name could be "payments".&nbsp;</summary>
topic
<br></details>

<details>
<summary>_____ in Kafka are always multi-producer and multi-subscriber: each can always have zero, one, or many producers that write events to it, as well as zero, one, or many consumers that subscribe to these events.</summary>
Topics
<br></details>

<details>
<summary>A Kafka event has been consumed. What happens to it?</summary>
It is retained for as long as it is defined to be retained, configured per topic.
<br></details>

<details>
<summary>Topics are&nbsp;<strong>partitioned</strong>, meaning a topic is spread over a number of "_____" located on different Kafka brokers.</summary>
buckets
<br></details>

<details>
<summary>Topics are distributed via partitioning (buckets). This improves scalability because it allows client applications to both read and write the data from/to many _____ at the same time.&nbsp;</summary>
brokers
<br></details>

<details>
<summary>Kafka&nbsp;<a href="https://kafka.apache.org/documentation/#intro_guarantees">guarantees</a>&nbsp;that any consumer of a given topic-partition will always read that partition's events in exactly the same order as _____.</summary>
they were written
<br></details>

<details>
<summary>When a new event is published to a topic, it is actually appended to one of the topic's _____. Events with the same event key (such as ID) are all written to the same one.</summary>
partitions
<br></details>

<details>
<summary>Can Kafka replace a traditional message broker?</summary>
Yes
<br></details>

<details>
<summary>Can Kafka be used for log aggregation?</summary>
Yes
<br></details>

<details>
<summary>Can Kafka process data in multiple-stage pipelines, where raw input data is consumed from Topics, then aggregated/enriched/transformed into new topics for further consumptions and processing?</summary>
Yes
<br></details>

<details>
<summary>Can an event represent a payment transaction?</summary>
Yes
<br></details>

<details>
<summary>Can an event represent a geolocation update?</summary>
Yes
<br></details>

<details>
<summary>Can an event represent a shipping order?</summary>
Yes
<br></details>

<details>
<summary>Can Kafka support log aggregation?</summary>
Yes
<br></details>

<details>
<summary>Does Kafka support large data backlogs?</summary>
Yes
<br></details>

<details>
<summary>In Kafka, can you process feeds to create new, derived feeds?</summary>
Yes - implemented by partitioning and the consumer model.
<br></details>

<details>
<summary>Kafka relies heavily on the _____ for storing and caching messages.&nbsp;</summary>
filesystem
<br></details>

<details>
<summary>In Kafka, using the filesystem and relying on _____ is superior to maintaining an in-memory cache or other structure�we at least double the available cache by having automatic access to all free memory, and likely double again by storing a compact byte structure rather than individual objects.&nbsp;</summary>
pagecache
<br></details>

<details>
<summary>Kafka protocol is built around a "_____" abstraction where network requests group messages together and amortize the overhead of the network roundtrip rather than sending a single message at a time. The server in turn appends chunks of messages to its log in one go, and the consumer fetches large linear chunks at a time.</summary>
message set
<br></details>

<details>
<summary>Byte copying can be an inefficiency while under large load. To avoid this we employ a standardized binary message format that is shared by the _____, the _____ and the _____ (so data chunks can be transferred without modification between them).</summary>
producer, broker and consumer
<br></details>

<details>
<summary>The _____ maintained by the broker is itself just a directory of files, each populated by a sequence of message sets that have been written to disk in the same format used by the producer and consumer.</summary>
message log&nbsp;
<br></details>

<details>
<summary>The producer sends data directly to the broker that is the _____ for the partition. To help the producer do this all Kafka nodes can answer a request for metadata about which servers are alive and where the leaders for the partitions of a topic are at any given time to allow the producer to appropriately direct its requests.</summary>
leader
<br></details>

<details>
<summary>The Kafka _____ works by issuing "fetch" requests to the brokers leading the partitions it wants to consume.&nbsp;
It specifies its offset in the log with each request and receives back a chunk of log beginning from that position, with possibility to rewind it to re-consume data as needed.</summary>
consumer
<br></details>

<details>
<summary>In Kafka, data is pushed from the _____ to the _____.&nbsp;&nbsp;</summary>
producer
broker
<br></details>

<details>
<summary>In Kafka, data is pulled from the _____ by the _____.&nbsp;</summary>
broker
consumer
<br></details>

<details>
<summary>A _____-based system like Kafka has the nicer property that the consumer simply falls behind and catches up when it can. This can be mitigated with some kind of backoff protocol by which the consumer can indicate it is overwhelmed, but getting the rate of transfer to fully utilize (but never over-utilize) the consumer is trickier than it seems.</summary>
pull
<br></details>

<details>
<summary>A consumer can deliberately <i>_____</i>&nbsp;back to an old offset and re-consume data. This violates the common contract of a queue, but turns out to be an essential feature for many consumers. For example, if the consumer code has a bug and is discovered after some messages are consumed, the consumer can re-consume those messages once the bug is fixed.</summary>
rewind
<br></details>

<details>
<summary>The position of a consumer in each partition is a single integer: the _____ of the next message to consume.&nbsp;
This makes the state about what has been consumed very small, just one number for each partition. This state can be periodically checkpointed. This makes the equivalent of message acknowledgements very cheap.</summary>
offset
<br></details>

<details>
<summary>"_____" delivery means messages may be lost but are never redelivered.</summary>
At most once
<br></details>

<details>
<summary>"_____" delivery means messages are never lost but may be redelivered.</summary>
At least once
<br></details>

<details>
<summary>"_____" delivery means messages are delivered once and only once. This is what Kafka implements.</summary>
Exactly once
<br></details>

<details>
<summary>When publishing a message Kafka has a notion of the message being "_____" to the log. It will not be lost as long as one broker that replicates the partition to which this message was written remains "alive".&nbsp;
If a producer attempts to publish a message and experiences a network error it cannot be sure if this error happened before or after the message was committed. This is similar to the semantics of inserting into a database table with an autogenerated key.</summary>
commited
<br></details>

<details>
<summary>Kafka replicates the log for each topic's partitions across a configurable number of servers. Can you set this replication factor per topic?</summary>
Yes
<br></details>

<details>
<summary>Kafka replicates the _____ for each topic's partitions across a configurable number of servers.</summary>
log
<br></details>

<details>
<summary>Kafka is meant to be used with replication by default�in fact we implement un-replicated topics as replicated topics where the replication factor is one. The unit of replication is the topic _____.&nbsp;</summary>
partition
<br></details>

<details>
<summary>Under non-failure conditions, each partition in Kafka has a single _____ and zero or more _____.&nbsp;</summary>
leader
followers
<br></details>

<details>
<summary>The total number of (partition?) replicas including the leader constitute the replication factor. All reads and writes go to the _____ of the partition.&nbsp;</summary>
leader
<br></details>

<details>
<summary>Typically, there are many more partitions than _____ and the leaders are evenly distributed among _____.&nbsp;</summary>
brokers
<br></details>

<details>
<summary>The logs on the _____ are identical to the leader's log�all have the same offsets and messages in the same order (though, of course, at any given time the leader may have a few as-yet unreplicated messages at the end of its log).</summary>
followers
<br></details>

<details>
<summary>Followers consume messages from the _____ just as a normal Kafka consumer would and apply them to their own log.</summary>
leader
<br></details>

<details>
<summary>A Kafka node is "in sync" if it meets 2 conditions:
1. A node must be able to maintain its session with _____2. If it is a follower, it must _____ writes happening on the leader without falling too far behind.</summary>
ZooKeeper
replicate
<br></details>

<details>
<summary>The _____ keeps track of the set of "in sync" nodes.</summary>
leader
<br></details>

<details>
<summary>The determination of _____ replicas is controlled by the replica.lag.time.max.ms configuration.</summary>
stuck and lagging
<br></details>

<details>
<summary>If a follower dies, gets stuck, or falls behind, the _____ will remove it from the list of in sync replicas.&nbsp;</summary>
leader
<br></details>

<details>
<summary>A message is considered committed when all _____ for that partition have applied it to their log.</summary>
in sync replicas
<br></details>

<details>
<summary>A _____ message will not be lost, as long as there is at least one in sync replica alive, at all times.</summary>
committed
<br></details>

<details>
<summary>_____ have the option of waiting for the message to be committed, depending on their preference for tradeoff between latency and durability. This preference is controlled by the acks setting that the producer uses.&nbsp;</summary>
Producers
<br></details>

<details>
<summary>Topics have a setting for the "minimum number" of in-sync replicas that is checked when the _____ requests acknowledgment that a message has been written to the full set of in-sync replicas.&nbsp;
If a less stringent acknowledgement is requested by the _____, then the message can be committed, and consumed, even if the number of in-sync replicas is lower than the minimum (e.g. it can be as low as just the leader).</summary>
producer
<br></details>

<details>
<summary>A Kafka partition is a replicated _____ which models the process of coming into consensus on the order of a series of values (generally numbering the log entries 0, 1, 2, ...).&nbsp;
A leader chooses the ordering of values provided to it. As long as the leader remains alive, all followers need to only copy the values and ordering the leader chooses.</summary>
log
<br></details>

<details>
<summary>To choose its quorum set, Kafka dynamically maintains a set of _____ that are caught-up to the leader. Only members of this set are eligible for election as leader.</summary>
in-sync replicas (ISR)
<br></details>

<details>
<summary>A write to a Kafka partition is not considered committed until <i>_____</i>&nbsp;have received the write.</summary>
<i>all</i>&nbsp;in-sync replicas
<br></details>

<details>
<summary>Kafka does not require that crashed nodes recover with all their data intact. Before being allowed to join the _____, a replica must fully re-sync again even if it lost unflushed data in its crash.</summary>
ISR
<br></details>

<details>
<summary>Kafka's guarantee with respect to data loss is predicated on _____ remaining in sync.</summary>
at least one replica
<br></details>

<details>
<summary>Systems must do something when all the replicas die - usually choosing between availability and consistency:<ol><li><b>DEFAULT</b>: Wait for a replica in the _____ to come back to life and choose this replica as the leader (hopefully it still has all its data). Kafka will remain unavailable as long as those replicas are down. If they or their data are gone, it is lost.</li><li>Choose the first replica (not necessarily in the _____) that comes back to life as the leader. If a non-in-sync replica comes back to life and we allow it to become leader, then its log becomes the source of truth even though it is not guaranteed to have every committed message.&nbsp;</li></ol></summary>
ISR
<br></details>

<details>
<summary>When writing to Kafka, _____ can choose whether they wait for the message to be acknowledged by replicas. Note that "acknowledgement by all replicas" does not guarantee that the full set of assigned replicas have received the message.</summary>
producers
<br></details>

<details>
<summary>If a topic is configured with only two replicas and one fails (i.e., only one in sync replica remains), then writes that specify _____ will succeed. However, these writes could be lost if the remaining replica also fails. Although this ensures maximum availability of the partition, this behavior may be undesirable to some users who prefer durability over availability.&nbsp;</summary>
acks=all
<br></details>

<details>
<summary>A topic can disable _____ - if all replicas become unavailable, then the partition will remain unavailable until the most recent leader becomes available again. This prefers unavailability over the risk of message loss.&nbsp;</summary>
unclean leader election
<br></details>

<details>
<summary>A topic can specify a minimum _____ - the partition will only accept writes if the size of the ISR is above a certain minimum, in order to prevent the loss of messages that were written to just a single replica, which subsequently becomes unavailable. This setting only takes effect if the producer uses acks=all and guarantees that the message will be acknowledged by at least this many in-sync replicas. This setting offers a trade-off between consistency and availability. A higher setting for minimum ISR size guarantees better consistency since the message is guaranteed to be written to more replicas which reduces the probability that it will be lost. However, it reduces availability since the partition will be unavailable for writes if the number of in-sync replicas drops below the minimum threshold.</summary>
ISR size
<br></details>

<details>
<summary>Partitions A Kafka cluster will manage thousands of topic partitions, balanced within a cluster in a _____ fashion to avoid clustering all partitions for high-volume topics on a small number of nodes.&nbsp;</summary>
round-robin
<br></details>

<details>
<summary>Kafka balances leadership so that each _____ is the leader for a proportional share of its partitions.</summary>
node
<br></details>

<details>
<summary>Log _____ ensures that Kafka will always retain at least the last known value for each message key within the log of data for a single topic partition.&nbsp;
Use cases:&nbsp;- restoring state after application crashes or system failure- reloading caches after application restarts during operational maintenance</summary>
compaction
<br></details>

<details>
<summary>Log _____ gives us a more granular retention mechanism so that we are guaranteed to retain at least the last update for each primary key (e.g.&nbsp;<code>bill@gmail.com</code>). By doing this we guarantee that the log contains a full snapshot of the final value for every key not just keys that changed recently. This means downstream consumers can restore their own state off this topic without us having to retain a complete log of all changes.</summary>
compaction
<br></details>

<details>
<summary>Log compaction can be useful for _____. This is a style of application design which co-locates query processing with application design and uses a log of changes as the primary store for the application.</summary>
Event sourcing
<br></details>

<details>
<summary>Log _____ is useful when you have a data set in multiple data systems, and one of these systems is a database.&nbsp;
For example you might have a database, a cache, a search cluster, and a Hadoop cluster. Each change to the database will need to be reflected in the cache, the search cluster, and eventually in Hadoop. In the case that one is only handling the real-time updates you only need recent log. But if you want to be able to reload the cache or restore a failed search node you may need a complete data set.</summary>
compaction
<br></details>

<details>
<summary>Log _____ is useful with a process that does local computation can be made fault-tolerant by logging out changes that it makes to its local state so another process can reload these changes and carry on if it should fail. A concrete example of this is handling counts, aggregations, and other "group by"-like processing in a stream query system. Samza, a real-time stream-processing framework,&nbsp;<a href="http://samza.apache.org/learn/documentation/0.7.0/container/state-management.html">uses this feature</a>&nbsp;for exactly this purpose.</summary>
compaction
<br></details>

<details>
<summary>Any _____ that stays caught-up to within the head of the log will see every message that is written; these messages will have sequential offsets.&nbsp;
- The topic's&nbsp;<code>min.compaction.lag.ms</code>&nbsp;can be used to guarantee the minimum length of time must pass after a message is written before it could be compacted. I.e. it provides a lower bound on how long each message will remain in the (uncompacted) head.&nbsp;- The topic's&nbsp;<code>max.compaction.lag.ms</code>&nbsp;can be used to guarantee the maximum delay between the time a message is written and the time the message becomes eligible for compaction.</summary>
consumer
<br></details>

<details>
<summary>Ordering of messages is always maintained. Log compaction will never re-order messages, just _____ some.</summary>
remove
<br></details>

<details>
<summary>With log compaction, the offset for a message never changes. It is the permanent _____ for a position in the log.</summary>
identifier
<br></details>

<details>
<summary>Log _____ guarantees that any consumer progressing from the start of the log will see at least the final state of all records in the order they were written. Additionally, all delete markers for deleted records will be seen, provided the consumer reaches the head of the log in a time period less than the topic's&nbsp;<code>delete.retention.ms</code>&nbsp;setting (the default is 24 hours). In other words: since the removal of delete markers happens concurrently with reads, it is possible for a consumer to miss delete markers if it lags by more than&nbsp;<code>delete.retention.ms</code>.</summary>
compaction
<br></details>

<details>
<summary>Log compaction is handled by the _____, a pool of background threads that recopy log segment files, removing records whose key appears in the head of the log.&nbsp;</summary>
log cleaner
<br></details>

<details>
<summary>Can log cleaning be enabled per-topic?</summary>
Yes
<br></details>

<details>
<summary>Kafka cluster has the ability to enforce _____ on requests to control the broker resources used by clients.&nbsp;</summary>
quotas
<br></details>

<details>
<summary>Two types of client quotas can be enforced by Kafka brokers for each group of clients sharing a quota:<ol><li>_____ quotas define byte-rate thresholds (since 0.9)</li><li>_____ quotas define CPU utilization thresholds as a percentage of network and I/O threads (since 0.11)</li></ol></summary>
Network bandwidth
Request rate
<br></details>

<details>
<summary>Modern unix operating systems offer a highly optimized code path for transferring data out of pagecache to a socket; in Linux this is done with the _____ system call.</summary>
<a href="http://man7.org/linux/man-pages/man2/sendfile.2.html">sendfile system call</a>
<br></details>

<details>
<summary>When a machine crashes or data needs to be re-loaded or re-processed, one needs to do a full load. _____ allows feeding both of these use cases off the same backing topic.&nbsp;</summary>
Log compaction. This style of usage of a log is described in more detail in&nbsp;<a href="http://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying">this blog post</a>.
<br></details>

<details>
<summary>All connections of a quota group share the quota configured for the group. For example, if (user="test-user", client-id="test-client") has a produce quota of 10MB/sec, this is shared across all _____ instances of user "test-user" with the client-id "test-client".</summary>
producer
<br></details>

<details>
<summary>Quotas can be applied to (user, client-id), user or client-id groups. For a given connection, the _____ quota matching the connection is applied.&nbsp;</summary>
most specific
<br></details>

<details>
<summary>The identity of Kafka clients is the _____ which represents an authenticated user in a secure cluster.&nbsp;</summary>
user principal
<br></details>

<details>
<summary>The tuple (_____, _____) defines a secure logical group of clients that share both user principal and client-id.</summary>
user, client-id
<br></details>

<details>
<summary>In a cluster that supports unauthenticated clients, _____ is a grouping of unauthenticated users chosen by the broker using a configurable&nbsp;<code>PrincipalBuilder</code>.&nbsp;</summary>
user principal
<br></details>

<details>
<summary>_____ is a logical grouping of clients with a meaningful name chosen by the client application.&nbsp;</summary>
Client-id
<br></details>

<details>
<summary>By default, each unique client group receives a fixed quota as configured by the cluster. This quota is defined and utilized by clients on a per-_____ basis before getting throttled.</summary>
broker
<br></details>

<details>
<summary>Messages consist of the variable-length items:
- _____- opaque _____ byte array&nbsp;- opaque _____ byte array</summary>
header
key

value
<br></details>

<details>
<summary>Messages are also known as...</summary>
records
<br></details>

<details>
<summary>Messages are always written in _____.&nbsp;</summary>
batches
<br></details>

<details>
<summary>Kafka consumer tracks the maximum offset it has consumed in each partition and has the capability to _____ offsets so that it can resume from those offsets in the event of a restart.&nbsp;</summary>
commit
<br></details>

<details>
<summary>Kafka provides the option to store all the offsets for a given consumer group in a designated broker (for that group) called the _____.&nbsp;
Any consumer instance in that consumer group should send its offset commits and fetches to that group coordinator (broker). Consumer groups are assigned to coordinators based on their group names.&nbsp;</summary>
group coordinator
<br></details>

<details>
<summary>You have the option of either adding topics manually or having them be created automatically when data is first published to _____.</summary>
a non-existent topic
<br></details>

<details>
<summary>The Kafka cluster will automatically detect any broker shutdown or failure and elect new _____ for the partitions on that machine.</summary>
leaders
<br></details>

<details>
<summary>We refer to the process of replicating data&nbsp;<i>between</i>&nbsp;Kafka clusters "_____" to avoid confusion with the replication that happens amongst the nodes in a single cluster.&nbsp;</summary>
mirroring
<br></details>

<details>
<summary>Does Kafka come with a tool for mirroring data between clusters?</summary>
Yes
<br></details>

<details>
<summary>Too add servers to a Kafka clusters, assign them a _____ and start up Kafka on them.</summary>
unique broker ID
<br></details>

<details>
<summary>New Kafka servers will not automatically be assigned any data partitions, so unless partitions are moved to them they won't be doing any work until new _____ are created.&nbsp;</summary>
topics
<br></details>

<details>
<summary>The partition reassignment tool can be used to move partitions across _____.&nbsp;</summary>
brokers
<br></details>

<details>
<summary>Kafka lets you apply a _____ to replication traffic, setting an upper bound on the bandwidth used to move replicas from machine to machine. This is useful when rebalancing a cluster, bootstrapping a new broker or adding or removing brokers, as it limits the impact these data-intensive operations will have on users.</summary>
throttle
<br></details>

<details>
<summary>The most important consumer configuration is the _____.</summary>
fetch size
<br></details>

<details>
<summary>Kafka always immediately writes all data to the filesystem and supports the ability to configure the _____ policy that controls when data is forced out of the OS cache and onto disk using the _____. It can force data to disk after a period of time or after a certain number of messages has been written.</summary>
flush
<br></details>

<details>
<summary>Kafka must eventually call _____ to know that data was flushed. When recovering from a crash for any log segment not known to be _____'d Kafka will check the integrity of each message by checking its CRC and also rebuild the accompanying offset index file as part of the recovery process executed on startup.</summary>
fsync
<br></details>

<details>
<summary>EXT4 has had more usage, but recent improvements to the _____ filesystem have shown it to have better performance characteristics for Kafka's workload with no compromise in stability.</summary>
XFS
<br></details>

<details>
<summary>_____ is the practice of capturing, storing, processing, routing and reacting to&nbsp;<b>streams of events</b>&nbsp;built from from&nbsp;<b>event sources</b>&nbsp;(databases, devices, software).</summary>
Event streaming
<br></details>

<details>
<summary>Is implementing data platforms and event-driven architecture a use case for event streaming?</summary>
Yes
<br></details>

<details>
<summary>Kafka distributed systems consist of&nbsp;<b>_____</b>&nbsp;and&nbsp;<strong>_____</strong>&nbsp;that communicate via a binary protocol over TCP.</summary>
clients and servers
<br></details>

<details>
<summary>Servers that run _____&nbsp;continuously import/export data as event streams, integrating Kafka with your existing systems, databases or other Kafka clusters.</summary>
<a href="https://kafka.apache.org/documentation/#connect">Kafka Connect</a>
<br></details>

<details>
<summary>_____<strong>&nbsp;</strong>allow you to write distributed applications and microservices that read/write/process streams of events in parallel, at scale, and in a fault-tolerant manner even in the case of network problems or machine failures.</summary>
Clients
<br></details>

<details>
<summary>An <b>_____&nbsp;</b>records the fact that something happened in your system.&nbsp;</summary>
event (or "record"/"message")
<br></details>

<details>
<summary>Does Kafka's performance lower with data size?</summary>
Kafka's performance is effectively constant with respect to data size, so storing data for a long time is perfectly fine.
<br></details>

<details>
<summary>Draw a diagram:&nbsp;- A topic has four partitions P1, P2, P3, P4.&nbsp;- Two different producers are independently publishing new events to the topic by writing events over the network to the topic's partitions. Both can write to the same partition if appropriate.- Events with the same key (denoted by their color in the diagram) are written to the same partition.&nbsp;</summary>
<img src="streams-and-tables-p1_p4.png">
<br></details>

<details>
<summary>A topic can be fault-tolerant and highly-available via being&nbsp;<strong>replicated</strong>&nbsp;across datacenters, so that there are always multiple _____ that have a copy of the data just in case things go wrong, you want to do maintenance on the brokers, and so on. A common production setting is a replication factor of 3, i.e., there will always be three copies of your data. This replication is performed at the level of topic-partitions.</summary>
brokers
<br></details>

<details>
<summary>Can Kafka be used to aggregate monitoring statistics from distributed applications to create centralized feeds of operational data?</summary>
Yes
<br></details>

<details>
<summary>Log aggregation typically collects physical log files off servers and puts them in HDFS or a central server for processing. Kafka abstracts away the details of files and gives a cleaner, lower-latency abstraction of log/event data as _____. This allows for easier support for multiple data sources and distributed data consumption.</summary>
a stream of messages
<br></details>

<details>
<summary>A processing pipeline for recommending news articles might crawl article content from RSS feeds and publish it to an "articles" topic; further processing might normalize or deduplicate this content and publish the cleansed article content to a new topic; a final processing stage might attempt to recommend this content to users.&nbsp;
Such processing pipelines create graphs of real-time data flows based on the individual topics. Starting in 0.10.0.0, a light-weight but powerful stream processing library called _____ is&nbsp;available in Apache Kafka to perform such data processing as described above. Apart from Kafka Streams, alternative open source stream processing tools include&nbsp;<a href="https://storm.apache.org/">Apache Storm</a>&nbsp;and&nbsp;<a href="http://samza.apache.org/">Apache Samza</a>.</summary>
<a href="https://kafka.apache.org/documentation/streams">Kafka Streams</a>&nbsp;
<br></details>

<details>
<summary>_____ is a style of application design where state changes are logged as a time-ordered sequence of records.</summary>
<a href="http://martinfowler.com/eaaDev/EventSourcing.html">Event sourcing</a>
<br></details>

<details>
<summary>Kafka can serve as an external commit-log for a distributed system, helping replicate data between nodes and re-syncing failed nodes to restore their data. The _____&nbsp;feature in Kafka helps support this usage.</summary>
<a href="https://kafka.apache.org/documentation.html#compaction">log compaction</a>
<br></details>

<details>
<summary>Kafka&nbsp;lets you read, write, store, and process _____ across many machines.</summary>
<a href="https://kafka.apache.org/documentation/#messages"><em>events</em></a>
<br></details>

<details>
<summary>Do you have to create a topic before writing your events?</summary>
Yes
<br></details>

<details>
<summary>Events in Kafka are durably stored. Can they be read any number of times by any number of consumers?</summary>
Yes
<br></details>

<details>
<summary>_____ allows you to integrate (via 'connectors') and continuously ingest data from existing, external systems into Kafka, and vice versa.</summary>
<a href="https://kafka.apache.org/documentation/#connect">Kafka Connect</a>
<br></details>

<details>
<summary>You can process events with the _____&nbsp;Java/Scala client library. The library supports exactly-once processing, stateful operations and aggregations, windowing, joins, processing based on event-time, etc.</summary>
<a href="https://kafka.apache.org/documentation/streams">Kafka Streams</a>
<br></details>

<details>
<summary>If your disk usage favors linear reads then read-ahead is effectively pre-populating this cache with useful data on each disk read. All data is immediately written to a persistent log on the filesystem without necessarily flushing to disk. In effect this just means that it is transferred into the kernel's _____.</summary>
pagecache
<br></details>

<details>
<summary>Efficient message compression requires compressing multiple messages together rather than compressing each message individually. A "_____" of messages can be clumped together compressed and sent to the server in this form. It will be written in compressed form and will remain compressed in the log and will only be decompressed by the consumer.</summary>
batch
<br></details>

<details>
<summary>To enable batching, the Kafka producer will attempt to accumulate data in memory and to send out larger batches of N messages in a single _____.</summary>
request
<br></details>

<details>
<summary>Kafka's topics are divided into a set of totally ordered _____, each consumed by exactly one consumer within each subscribing consumer group at any given time.&nbsp;</summary>
partitions
<br></details>

<details>
<summary>_____ aims to improve the availability of stream applications, consumer groups and other applications built on top of the group rebalance protocol. The rebalance protocol relies on the group coordinator to allocate entity ids to group members. These generated ids are ephemeral and will change when members restart and rejoin.&nbsp;

Kafka�s group management protocol allows group members to provide persistent entity ids. Group membership remains unchanged based on those ids, thus no rebalance will be triggered.</summary>
Static membership
<br></details>

<details>
<summary>If a majority of servers suffer a permanent failure, then you must either choose to lose _____ of your data or violate _____ by taking what remains on an existing server as your new source of truth.</summary>
100%

consistency
<br></details>

<details>
<summary>Each log _____ works as follows:<ol><li>It chooses the log that has the highest ratio of log head to log tail</li><li>It creates a succinct summary of the last offset for each key in the head of the log</li><li>It recopies the log from beginning to end removing keys which have a later occurrence in the log. New, clean segments are swapped into the log immediately so the additional disk space required is just one additional log segment (not a fully copy of the log).</li><li>The summary of the log head is essentially just a space-compact hash table. It uses exactly 24 bytes per entry. As a result with 8GB of cleaner buffer one cleaner iteration can clean around 366GB of log head (assuming 1k messages).</li></ol></summary>
compactor thread
<br></details>

<details>
<summary>The _____ controls which partition it publishes messages to. This can be done at random, or by some semantic partitioning function.&nbsp;
You can specify a key to partition by and using this to hash to a partition. For example if the key chosen was a user id then all data for a given user would be sent to the same partition.&nbsp;
This in turn will allow consumers to make locality assumptions about their consumption. This style of partitioning is explicitly designed to allow locality-sensitive processing in consumers.</summary>
client
<br></details>

<details>
<summary>_____ is a mechanism to give finer-grained per-record retention, rather than the coarser-grained time-based retention. The idea is to selectively remove records where we have a more recent update with the same primary key.&nbsp;
This way the log is guaranteed to have at least the last state for each key.This retention policy can be set per-topic, so a single cluster can have some topics where retention is enforced by size or time and other topics where retention is enforced by compaction.</summary>
Log compaction
<br></details>

<details>
<summary>It is possible for producers and consumers to produce/consume very high volumes of data or generate requests at a very high rate and thus monopolize broker resources, cause network saturation and generally DOS other clients and the brokers themselves. Having _____ protects against these issues and is all the more important in large multi-tenant clusters where a small set of badly behaved clients can degrade user experience for the well behaved ones.</summary>
quotas
<br></details>

<details>
<summary>Quota configuration may be defined for _____. It is possible to override the default quota at any of the quota levels. The mechanism is similar to the per-topic log config overrides.&nbsp;</summary>
(user, client-id), user and client-id groups
<br></details>

<details>
<summary>_____ quotas are defined as the byte rate threshold for each group of clients sharing a quota. By default, each unique client group receives a fixed quota in bytes/sec as configured by the cluster.&nbsp;
This quota is defined on a per-broker basis. Each group of clients can publish/fetch a maximum of X bytes/sec per broker before clients are throttled.</summary>
Network bandwidth&nbsp;
<br></details>

<details>
<summary>_____ quotas are defined as the percentage of time a client can utilize on request handler I/O threads and network threads of each broker within a quota window. A quota of&nbsp;n%&nbsp;represents&nbsp;n%&nbsp;of one thread, so the quota is out of a total capacity of&nbsp;((num.io.threads + num.network.threads) * 100)%. Each group of clients may use a total percentage of upto&nbsp;n%&nbsp;across all I/O and network threads in a quota window before being throttled. Since the number of threads allocated for I/O and network threads are typically based on the number of cores available on the broker host, request rate quotas represent the total percentage of CPU that may be used by each group of clients sharing the quota.</summary>
Request rate quotas
<br></details>

<details>
<summary>When a server is stopped gracefully it has two optimizations it will take advantage of:<ol><li>It will _____ to avoid needing to do any log recovery when it restarts (i.e. validating the checksum for all messages in the tail of the log). Log recovery takes time so this speeds up intentional restarts.</li><li>It will _____ to other replicas prior to shutting down. This will make the leadership transfer faster and minimize the time each partition is unavailable to a few milliseconds.</li></ol></summary>
sync all its logs to disk
migrate any partitions the server is the leader for&nbsp;
<br></details>

<details>
<summary>Whenever a broker stops or crashes, leadership for that broker's partitions transfers to other replicas. When the broker is restarted it will only be a follower for all its partitions, meaning it will not be used for client reads and writes.
To avoid this imbalance, Kafka has a notion of _____.</summary>
preferred replicas
<br></details>

<details>
<summary>Does the partition reassignment tool have the ability to automatically generate a reassignment plan for decommissioning brokers?&nbsp;</summary>
No - the admin has to come up with a reassignment plan to move the replica for all partitions hosted on the broker to be decommissioned, to the rest of the brokers.
<br></details>

<details>
<summary>The most important producer configurations are _____, _____ and _____</summary>
acks
compression
batch size
<br></details>

<details>
<summary>Kafka uses _____ Metrics for metrics reporting in the server.&nbsp;
The Java clients use Kafka Metrics, a built-in metrics registry that minimizes transitive dependencies pulled into client applications.&nbsp;
Both expose metrics via JMX and can be configured to report stats using pluggable stats reporters to hook up to your monitoring system.</summary>
Yammer
<br></details>

<details>
<summary>Can asynchronous workflows reduce request time for expensive operations (that would otherwise be performed in-line)?</summary>
Yes
<br></details>

