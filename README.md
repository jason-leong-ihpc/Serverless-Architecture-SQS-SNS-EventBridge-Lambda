# Serverless-Architecture-SQS-SNS-EventBridge-Lambda

## Answer the following:
### - Does SNS guarantee exactly once delivery to subscribers?  
![SNS Topic Creation](images/sns_fifo.png)  
Amazon SNS FIFO (First-In-First-Out) topics provide exactly-once message delivery to subscribers, given certain conditions are met:
* The subscriber is an Amazon SQS queue that has permissions that allow the Amazon SNS service principal to deliver messages to the queue.
* The Amazon SQS FIFO queue consumer processes the message and deletes it from the queue before the visibility timeout expires.
* Must avoid message filtering which can lead to at-least-once delivery behaviour.
* No network disruptions that prevent acknowledgment of the message delivery.  

Source [Amazon SNS message deduplication for FIFO topics](https://docs.aws.amazon.com/sns/latest/dg/fifo-message-dedup.html)
### - What is the purpose of the Dead-letter Queue (DLQ)? This a feature available to SQS/SNS/EventBridge.  

### - How would you enable a notification to your email when messages are added to the DLQ?  
