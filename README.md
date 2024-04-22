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
<img src= "assets/images/Screen Shot 2024-04-22 at 22.24.57.png" width="600px"> <br>
This is the default state of RabbitMQ.

### Running subscriber
<img src= "assets/images/Screen Shot 2024-04-22 at 22.44.32.png" width="600px"> <br>
This is the terminal state after running subscriber. The output is a result from running publisher multiple times
as shown in the next picture.

### Running publisher
<img src= "assets/images/Screen Shot 2024-04-22 at 22.42.08.png" width="600px"> <br>
This is the state after running publisher multiple times.

### Running RabbitMQ after connection
<img src= "assets/images/Screen Shot 2024-04-22 at 22.44.57.png" width="600px"> <br>

This is the state of RabbitMQ after running subscriber. The ```Connections: 1``` indicates that there's
1 subscriber making connection to the broker.

### Running the publisher repeatedly
<img src= "assets/images/Screen Shot 2024-04-22 at 22.59.27.png" width="600px"> <br>
This is the state of RabbitMQ after running the publisher multiple times. It is shown that there is an increase in messages in a time interval. 
This is because of the multiple cargo runs of the the publisher project. 
Every time the publisher is implemented, there will be an increase in the message rate on RabbitMQ which is useful information.

### Running at least three subscribers
<img src= "assets/images/Screen Shot 2024-04-22 at 23.28.13.png" width="600px"> <br>
<img src= "assets/images/Screen Shot 2024-04-22 at 23.28.53.png" width="600px"> <br>
The spike in the queued messages graph is less pronounced and declines more rapidly. 
This is because there are three subscribers, allowing the message broker to distribute 
the queued messages among all three simultaneously, which is significantly quicker than if there were only one subscriber.
In the first picture, it is visible that the cargo runs of publisher is split to be received by three separate subscriber
consoles. Therefore the process becomes a lot faster.

