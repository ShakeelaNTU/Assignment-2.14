# Assignment-2.14 Shakeela

# SNS, Dead-letter Queue (DLQ), and Notifications

## Does SNS guarantee exactly once delivery to subscribers?
No, SNS (Simple Notification Service) does not guarantee exactly-once delivery to subscribers. SNS provides at-least-once delivery, meaning a message might be delivered more than once in certain scenarios, such as retries due to network issues or subscriber unavailability.

## What is the purpose of the Dead-letter Queue (DLQ)?
The purpose of a Dead-letter Queue (DLQ) is to store messages that cannot be successfully processed or delivered to their destination after a configured number of retry attempts. This feature is available in SQS, SNS, and EventBridge to help prevent message loss and to allow for debugging and resolution of issues with undelivered messages.

## How would you enable a notification to your email when messages are added to the DLQ?
To enable a notification to your email when messages are added to the DLQ, follow these steps:

1. **Create an SNS Topic:**
   - Go to the AWS Management Console and create a new SNS topic.

2. **Subscribe an Email Address to the SNS Topic:**
   - Add an email subscription to the SNS topic. Confirm the subscription by clicking the link in the confirmation email sent to the provided email address.

3. **Set Up an EventBridge Rule:**
   - Create an EventBridge rule that triggers when messages are sent to the DLQ.
   - Configure the rule to publish a notification to the SNS topic created in step 1.

4. **Test the Setup:**
   - Send a test message to the DLQ and verify that an email notification is received.

By following these steps, you can ensure that you are notified whenever a message is added to the DLQ.
