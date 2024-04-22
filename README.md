# Tutorial 8
Farrel Ayman Abisatyo  <br>
2206828916 <br>
Advanced Programming B <br>

## Reflection
### a. How many data your publisher program will send to the message broker in one run?
The publisher program will send 5 messages to the broker. It is reflected in the number of 
```publish_event``` function calls in ```main.rs```.
### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
It means that both subscriber and publisher programs are connected to the same message broker that's
running on the same machine.

### Running RabbitMQ
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 22.24.57.png" width="600px"> <br>
This is the default state of RabbitMQ.

### Running subscriber
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 22.44.32.png" width="600px"> <br>
This is the terminal state after running subscriber. The output is a result from running publisher multiple times
as shown in the next picture.

### Running publisher
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 22.42.08.png" width="600px"> <br>
This is the state after running publisher multiple times.

### Running RabbitMQ after connection
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 22.44.57.png" width="600px"> <br>

This is the state of RabbitMQ after running subscriber. The ```Connections: 1``` indicates that there's
1 subscriber making connection to the broker.

### Running the publisher repeatedly
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 22.59.27.png" width="600px"> <br>
This is the state of RabbitMQ after running the publisher multiple times. It is shown that there is an increase in messages in a time interval. 
This is because of the multiple cargo runs of the the publisher project. 
Every time the publisher is implemented, there will be an increase in the message rate on RabbitMQ which is useful information.

### Running the publisher repeatedly
<img src= "/Users/farrelayman/Desktop/Screen Shot 2024-04-22 at 23.07.40.png" width="600px"> <br>
After making the subscriber slower, the total number of queued 
messages after running cargo run five times is 20. This indicates the number of messages that are still in the 
queue at that current time, before they are received by the subsciber.