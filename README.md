# cicd2-RabbitMQ-


**What is the difference between a producer, a queue and a consumer?**
A producer submits the the to the queue, which acts as a broker controlling which tasks the consumer gets

**When the worker was stopped, why did the Ready count increase?** 
Because the order will still be accepted for later processing when worker is available

**What changed in RabbitMQ Management while the worker was processing a message?** 

**What does HTTP 202 Accepted tell the client, and what does it not guarantee?** 
It indicates that the job has being accepted but not completed

**Why is await useful when a FastAPI endpoint communicates with RabbitMQ?**
It allows you to pause the without blocking the event-loop thread.The loop can then run other ready work and return to the paused function when the result is available

**What changed when you set prefetch_count=2? Did the worker actually process two orders at the same time?** 
No. it just means that the worker can  have 2 unacknowledged deliveries at a time in queue

**With two consumers using prefetch_count=1, what did the Consumers and Unacknowledged counts show?**
The consumer should still have at most one unacknowledged message at a time. Both Consumers should receive some orders. count increase

**What happened when one worker stopped before acknowledging an order? Why can the same message be delivered twice?** 
It will be sent to the other worker . RabbitMQ tracks message delivery and acknowledgements 

**In your own words, what does an event loop do while an async function is awaiting a network operation?**

It mocks a waiting for a actually network response.
