# RedisKit.

  Collection of Redis backed data structures for nodejs. RedisKit aims to create first-class JavaScript objects of the primitives that Redis provies as well as higher level abstractions and interactions between the data types.

## Structures

    - Key
      - List
        - Queue
        - CappedList
      - Hash

## Installation

    $ npm install rediskit

## Example

    var list = new List('pets')
      , tobi = new Hash('pet:tobi')
      , loki = new Hash('pet:loki')
      , jane = new Hash('pet:jane');

    list.rpush('tobi');
    list.rpush('jane');
    list.rpush('loki');

    tobi.set('age', 1);
    loki.set('age', 0.5);
    jane.set('age', 3);

    list.sort.by('pet:*->age').get('#').get('pet:*->age').end(function(err, res){
      res.should.eql(['loki', '0.5', 'tobi', '1', 'jane', '3']);
    });

## Running Tests

    $ npm install
    $ redis-server
    $ make test


















































