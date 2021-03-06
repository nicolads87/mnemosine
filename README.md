# mnemosine
Simple in memory key - value store and Message Broker written in Python



## Installation
  Menmosine works on most Linux and BSD like systems. Requires python 3.7.0
  Download the pachage and run the command `py mnemosine.py`

## Install a client
  Menmosine on its own is simply a key/value store daemon and message broker. Applications will need clients, of which there should be ones readily available for your language of choice.


## Use of the node js client
### Mnemosine store

```node
  let Mnemosine = require('./mnemosine');
  let mnemosine = new Mnemosine();


  var person = {
    name: "Jade",
    age: 30,
    id: "123e4567-e89b-12d3-a456-426655440000"
  };
  mnemosine.put("key", JSON.stringify(person));
```

```node
let Mnemosine = require('./mnemosine');


let mnemosine = new Mnemosine();



mnemosine.get("key", function(data) {
	console.log(data)
});
```

### Mnemosine message broker

```node
let Mnemosine = require('./mnemosine');


let producer = new Mnemosine();


var person = {
	name: "Jade",
	age: 30,
	email: "emai@example.com",
	id: "123e4567-e89b-12d3-a456-426655440000"
};
producer.publish("queue_name", JSON.stringify(person));
```

```node
let Mnemosine = require('./mnemosine');


let subscriber = new Mnemosine();
subscriber.subscribe("queue_name", function(data) {
	console.log(data);
});
```
