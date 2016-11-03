<!--
Copyright (c) 2007-2016 Pivotal Software, Inc.

All rights reserved. This program and the accompanying materials
are made available under the terms of the under the Apache License,
Version 2.0 (the "License”); you may not use this file except in compliance
with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# JMS Client Reference

This page annotates the [RabbitMQ JMS Client](/jms-client.html) implementation
of the JMS 1.1 API.

You can download the JMS 1.1 specification and API documentation 
from the [Oracle Technology Network Web site](http://www.oracle.com/technetwork/java/docs-136352.html).

## <a id="ConnectionFactories"></a>Connection Factory Interfaces

### <a id="ConnectionFactory"></a>ConnectionFactory

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Connection CreateConnection()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Connection CreateConnection(java.lang.String userName, 
                            java.lang.String password)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="QueueConnectionFactory"></a>QueueConnectionFactory

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">QueueConnection CreateQueueConnection()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">QueueConnection CreateQueueConnection(java.lang.String userName, 
                                      java.lang.String password)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TopicConnectionFactory"></a>TopicConnectionFactory

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">TopicConnection CreateTopicConnection()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TopicConnection CreateTopicConnection(java.lang.String userName, 
                                      java.lang.String password)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="XAQueueConnectionFactory"></a>XAQueueConnectionFactory

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">XAQueueConnection CreateXAQueueConnection()</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">XAQueueConnection CreateXAQueueConnection(java.lang.String userName, 
                                          java.lang.String password)</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

### <a id="XATopicConnectionFactory"></a>XATopicConnectionFactory

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">XATopicConnection CreateXATopicConnection()</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">XATopicConnection CreateXATopicConnection(java.lang.String userName, 
                                          java.lang.String password)</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

## <a id="ServerSessions"></a>Server Session Interfaces

The JMS for RabbitMQ client does not support server sessions.

### <a id="ServerSessionPool"></a>ServerSessionPool

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">ServerSession getServerSession()</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

### <a id="ServerSession"></a>ServerSession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Session getSession()</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">void start()</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

## <a id="Connections"></a>Connection Interfaces

### <a id="Connection"></a>Connection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Session createSession(boolean transacted, 
                      int acknowledgeMode)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getClientID()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setClientID(java.lang.String clientID)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionMetaData getMetaData()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">ExceptionListener getExceptionListener()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setExceptionListener(ExceptionListener listener)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void start()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void stop()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionConsumer createConnectionConsumer(Destination destination, 
                                            java.lang.String messageSelector, 
                                            ServerSessionPool sessionPool, 
                                            int maxMessages)</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionConsumer createDurableConnectionConsumer(Topic topic, 
                                                   java.lang.String subscriptionName, 
                                                   java.lang.String messageSelector, 
                                                   ServerSessionPool sessionPool, 
                                                   int maxMessages)</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

### <a id="QueueConnection"></a>QueueConnection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">QueueSession createQueueSession(boolean transacted, 
                                int acknowledgeMode)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionConsumer createConnectionConsumer(Queue queue, 
                                            java.lang.String messageSelector, 
                                            ServerSessionPool sessionPool, 
                                            int maxMessages)</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

### <a id="TopicConnection"></a>TopicConnection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">TopicSession createTopicSession(boolean transacted, 
                                int acknowledgeMode)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionConsumer createConnectionConsumer(Topic topic, 
                                            java.lang.String messageSelector, 
                                            ServerSessionPool sessionPool, 
                                            int maxMessages)</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">ConnectionConsumer createDurableConnectionConsumer(Topic topic, 
                                                   java.lang.String subscriptionName, 
                                                   java.lang.String messageSelector, 
                                                   ServerSessionPool sessionPool, 
                                                   int maxMessages)</pre></td>
<td>Not supported</td>
</tr>
</tbody>
</table>

### <a id="XAConnection"></a>XAConnection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">XASession createXASession()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">Session createSession(boolean transacted, 
                      int acknowledgeMode)</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

### <a id="XAQueueConnection"></a>XAQueueConnection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">XAQueueSession createXAQueueSession()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">QueueSession createQueueSession(boolean transacted, 
                                int acknowledgeMode)</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

### <a id="XATopicConnection"></a>XATopicConnection

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">XATopicSession createXATopicSession()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">TopicSession createTopicSession(boolean transacted, 
                                int acknowledgeMode)</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

## <a id="Sessions"></a>Session Interfaces

### <a id="Session"></a>Session

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">BytesMessage createBytesMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">MapMessage createMapMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Message createMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ObjectMessage createObjectMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">ObjectMessage createObjectMessage(java.io.Serializable object)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">StreamMessage createStreamMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TextMessage createTextMessage()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TextMessage createTextMessage(java.lang.String text)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean getTransacted()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getAcknowledgeMode()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void commit()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void rollback()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void recover()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">MessageListener getMessageListener()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setMessageListener(MessageListener listener)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void run()</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">MessageProducer createProducer(Destination destination)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">MessageConsumer createConsumer(Destination destination)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">MessageConsumer createConsumer(Destination destination, 
                               java.lang.String messageSelector)</pre></td>
<td>Not implemented for non-empty messageSelector</td>
</tr>
<tr>
<td><pre class="pre">MessageConsumer createConsumer(Destination destination, 
                               java.lang.String messageSelector, 
                               boolean NoLocal)</pre></td>
<td>Not implemented for non-empty messageSelector, and noLocal accepted but ignored</td>
</tr>
<tr>
<td><pre class="pre">Queue createQueue(java.lang.String queueName)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Topic createTopic(java.lang.String topicName)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TopicSubscriber createDurableSubscriber(Topic topic, 
                                        java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TopicSubscriber createDurableSubscriber(Topic topic, 
                                        java.lang.String name, 
                                        java.lang.String messageSelector, 
                                        boolean noLocal)</pre></td>
<td>Supported without NoLocal</td>
</tr>
<tr>
<td><pre class="pre">QueueBrowser createBrowser(Queue queue)</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">QueueBrowser createBrowser(Queue queue, 
                           java.lang.String messageSelector)</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">TemporaryQueue createTemporaryQueue()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TemporaryTopic createTemporaryTopic()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void unsubscribe(java.lang.String name)</pre></td>
<td>Supported for durable subscriptions only</td>
</tr>
</tbody>
</table>

### <a id="TopicSession"></a>TopicSession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Topic createTopic(java.lang.String topicName)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TopicSubscriber createSubscriber(Topic topic, 
                java.lang.String messageSelector, 
                boolean noLocal)</pre></td>
<td>NoLocal is not supported</td>
</tr>
<tr>
<td><pre class="pre">TopicSubscriber createSubscriber(Topic topic)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TopicSubscriber createDurableSubscriber(Topic topic,
                                        java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="QueueSession"></a>QueueSession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Queue createQueue(java.lang.String queueName))</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">QueueReceiver createReceiver(Queue queue)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">QueueReceiver createReceiver(Queue queue,
                             java.lang.String messageSelector)</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">QueueSender createSender(Queue queue)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">QueueBrowser createBrowser(Queue queue)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">QueueBrowser createBrowser(Queue queue,
                           java.lang.String messageSelector)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">TemporaryQueue createTemporaryQueue()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="XAQueueSession"></a>XAQueueSession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">QueueSession getQueueSession()</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

### <a id="XASession"></a>XASession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Session getSession()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">XAResource getXAResource()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">boolean getTransacted()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">void commit()</pre></td>
<td>Not yet implemented</td>
</tr>
<tr>
<td><pre class="pre">void rollback()</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

### <a id="XATopicSession"></a>XATopicSession

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">TopicSession getTopicSession()</pre></td>
<td>Not yet implemented</td>
</tr>
</tbody>
</table>

## <a id="consumers-producers"></a>Consumer and Producer Interfaces

### <a id="ConnectionConsumer"></a>ConnectionConsumer

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">ServerSessionPool getServerSessionPool()</pre></td>
<td>Not supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Not Supported</td>
</tr>
</tbody>
</table>

### <a id="MessageProducer"></a>MessageProducer

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">void setDisableMessageID(boolean value)</pre></td>
<td>Ignored.</td>
</tr>
<tr>
<td><pre class="pre">boolean getDisableMessageID()</pre></td>
<td>Ignored.</td>
</tr>
<tr>
<td><pre class="pre">void setDisableMessageTimestamp(boolean value)</pre></td>
<td>Ignored.</td>
</tr>
<tr>
<td><pre class="pre">boolean getDisableMessageTimestamp()</pre></td>
<td>Ignored.</td>
</tr>
<tr>
<td><pre class="pre">void setDeliveryMode(int deliveryMode)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getDeliveryMode()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setPriority(int defaultPriority)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getPriority()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setTimeToLive(long timeToLive)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long getTimeToLive()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Destination getDestination()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Message message,
          int deliveryMode,
          int priority,
          long timeToLive)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Destination destination,
          Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Destination destination,
          Message message,
          int deliveryMode,
          int priority,
          long timeToLive)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="QueueSender"></a>QueueSender

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Queue getQueue()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Message message,
          int deliveryMode,
          int priority,
          long timeToLive)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Queue queue,
          Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void send(Queue queue,
          Message message,
          int deliveryMode,
          int priority,
          long timeToLive)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TopicPublisher"></a>TopicPublisher

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Topic getTopic()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void publish(Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void publish(Message message,
             int deliveryMode,
             int priority,
             long timeToLive)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void publish(Topic topic,
             Message message)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void publish(Topic topic,
             Message message,
             int deliveryMode,
             int priority,
             long timeToLive)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

## <a id="messages"></a>Message Interfaces

### <a id="Message"></a>Message

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">java.lang.String getJMSMessageID()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSMessageID(java.lang.String id)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long getJMSTimestamp()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSTimestamp(long timestamp)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte[] getJMSCorrelationIDAsBytes()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSCorrelationIDAsBytes(byte[] correlationID)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSCorrelationID(java.lang.String correlationID)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getJMSCorrelationID()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Destination getJMSReplyTo()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSReplyTo(Destination replyTo)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Destination getJMSDestination()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSDestination(Destination destination)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getJMSDeliveryMode()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSDeliveryMode(int deliveryMode)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean getJMSRedelivered()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSRedelivered(boolean redelivered)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getJMSType()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSType(java.lang.String type)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long getJMSExpiration()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSExpiration(long expiration)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getJMSPriority()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setJMSPriority(int priority)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void clearProperties()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean propertyExists(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean getBooleanProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte getByteProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">short getShortProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getIntProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long getLongProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">float getFloatProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">double getDoubleProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getStringProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.Object getObjectProperty(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.util.Enumeration getPropertyNames()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setBooleanProperty(java.lang.String name,
                        boolean value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setShortProperty(java.lang.String name,
                      short value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setIntProperty(java.lang.String name,
                    int value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setLongProperty(java.lang.String name,
                     long value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setFloatProperty(java.lang.String name,
                      float value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setDoubleProperty(java.lang.String name,
                       double value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setStringProperty(java.lang.String name,
                       java.lang.String value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setObjectProperty(java.lang.String name,
                       java.lang.Object value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void acknowledge()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void clearBody()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="BytesMessage"></a>BytesMessage

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">long getBodyLength()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean readBoolean()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte readByte()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readUnsignedByte()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">short readShort()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readUnsignedShort()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">char readChar()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readInt()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long readLong()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">float readFloat()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">double readDouble()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String readUTF()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readBytes(byte[] value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readBytes(byte[] value,
              int length)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBoolean(boolean value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeByte(byte value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeShort(short value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeChar(char value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeInt(int value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeLong(long value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeFloat(float value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeDouble(double value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeUTF(java.lang.String value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBytes(byte[] value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBytes(byte[] value,
                int offset,
                int length)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeObject(java.lang.Object value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void reset()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="MapMessage"></a>MapMessage

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">boolean getBoolean(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte getByte(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">short getShort(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">char getChar(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int getInt(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long getLong(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">float getFloat(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">double getDouble(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getString(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte[] getBytes(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.Object getObject(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.util.Enumeration getMapNames()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setBoolean(java.lang.String name,
                boolean value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setByte(java.lang.String name,
             byte value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setShort(java.lang.String name,
              short value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setChar(java.lang.String name,
             char value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setInt(java.lang.String name,
            int value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setLong(java.lang.String name,
             long value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setFloat(java.lang.String name,
              float value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setDouble(java.lang.String name,
               double value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setString(java.lang.String name,
               java.lang.String value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setBytes(java.lang.String name,
              byte[] value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setBytes(java.lang.String name,
              byte[] value,
              int offset,
              int length)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setObject(java.lang.String name,
               java.lang.Object value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean itemExists(java.lang.String name)</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="ObjectMessage"></a>ObjectMessage

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">void setObject(java.io.Serializable object)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.io.Serializable getObject()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="StreamMessage"></a>StreamMessage

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">boolean readBoolean()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">byte readByte()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">short readShort()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">char readChar()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readInt()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">long readLong()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">float readFloat()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">double readDouble()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String readString()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">int readBytes(byte[] value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.Object readObject()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBoolean(boolean value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">oid writeByte(byte value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeShort(short value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeChar(char value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeInt(int value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeLong(long value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeFloat(float value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeDouble(double value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeString(java.lang.String value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBytes(byte[] value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeBytes(byte[] value,
                int offset,
                int length)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void writeObject(java.lang.Object value)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void reset()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TextMessage"></a>TextMessage

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">void setText(java.lang.String string)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getText()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

## <a id="consumers"></a>Message Consumer Interfaces

### <a id="MessageConsumer"></a>MessageConsumer

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">java.lang.String getMessageSelector()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">MessageListener getMessageListener()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void setMessageListener(MessageListener listener)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Message receive()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Message receive(long timeout)</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">Message receiveNoWait()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="QueueReceiver"></a>QueueReceiver

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Queue getQueue()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TopicSubscriber"></a>TopicSubscriber

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Topic getTopic()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">boolean getNoLocal()</pre></td>
<td>NoLocal is not supported</td>
</tr>
</tbody>
</table>

## <a id="destinations"></a>Destination Interfaces

### <a id="Destination"></a>Destination

(Has No Methods)

### <a id="Queue"></a>Queue

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">java.lang.String getQueueName()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String toString()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TemporaryQueue"></a>TemporaryQueue

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">void delete()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="Topic"></a>Topic

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">java.lang.String getTopicName()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String toString()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

### <a id="TemporaryTopic"></a>TemporaryTopic

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">void delete()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

## <a id="QueueBrowser"></a>QueueBrowser

See [QueueBrowser support](jms-client-api-guide.html#queue_browser_sup) for implementation details.

<table>
<colgroup>
<col width="80%" />
<col width="20%" />
</colgroup>
<tbody>
<tr>
<td><pre class="pre">Queue getQueue()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.lang.String getMessageSelector()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">java.util.Enumeration getEnumeration()</pre></td>
<td>Supported</td>
</tr>
<tr>
<td><pre class="pre">void close()</pre></td>
<td>Supported</td>
</tr>
</tbody>
</table>

