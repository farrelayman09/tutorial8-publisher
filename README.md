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
