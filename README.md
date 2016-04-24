# codecademy
## Javascript snippets from codecademy

### substring

`"Hamburgers".substring(3,10)` returns "burgers"

### Nested for loop

    var text = "Hi my name is Miwa. Yes that's my name. Miwa!\ There is a mountain called Mount Miwa. That's where my name\ come from.";

    var myName = "Miwa";

    var hits = [];

    for(var i = 0; i < text.length; i++){
      if(text[i] === "M"){
          for(var j = i; j < (myName.length + i); j++){
            hits.push(text[j]);
          }
      }
    }

### while loop

    var i = 0
    var loop = function(){
	    while(i < 3){
		    console.log("I'm looping!");
		    i++;
	    }
    };
    loop();
    
### Do while

	var loopCondition = false;

	do {
		console.log("I'm gonna stop looping 'cause my condition is " + loopCondition + "!");	
	} while (loopCondition);


### boolean using Math

`var i` to `Math.floor(Math.random() * 2)`. This sets `i` to a random number that's either `0` (which JavaScript reads as `false`) or `1` (which JavaScript reads as `true`).


	var slaying = true;
	var youHit = function(){
		rerutn Math.floor(Math.random() * 2)
	};
	var damageThisRound = Math.floor(Math.random()*5 + 1);
	var totalDamage = 0;

	while(slaying){
    	if(youHit == 1){
        	console.log("Congrats!");
        	totalDamage += damageThisRound;
        	if(totalDamage >= 4){
            		console.log("Yay! You slew the dragon!");
            		slaying = false;
        	}else{
            		youHit();
        	}
    	}else{
        	console.log(":(")
    	}
    	slaying = false;
	}
	
### FizzBuzz

	for(var i=1; i<=20; i++){

  		if(i%3===0 && i%5===0){
    			console.log("FizzBuzz")
  		}else if (i%3===0){
    			console.log("Fizz");
  		}else if (i%5===0){
    			console.log("Buzz");
  		}else{
    			console.log(i);
  		}
	}

### Objects

    var friends = {};
    friends.bill = {
      firstName: "Bill",
      lastName: "Gates",
      number: "(206) 555-5555",
      address: ['One Microsoft Way','Redmond','WA','98052']
    };
    friends.steve = {
      firstName: "Steve",
      lastName: "Jobs",
      number: "(408) 555-5555",
      address: ['1 Infinite Loop','Cupertino','CA','95014']
    };

    var list = function(obj) {
      for(var prop in obj) {
        console.log(prop);
      }
    };

    var search = function(name) {
      for(var prop in friends) {
        if(friends[prop].firstName === name) {
          console.log(friends[prop]);
          return friends[prop];
        }
      }
    };

    list(friends);
    search("Steve");
