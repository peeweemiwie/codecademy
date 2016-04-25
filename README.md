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



### `this` keywords


    var rectangle = new Object();
    rectangle.height = 3;
    rectangle.width = 4;
    // here is our method to set the height
    rectangle.setHeight = function (newHeight) {
      this.height = newHeight;
    };
    // help by finishing this method
    rectangle.setWidth = function (newWidth) {
        this.width = newWidth;
    };
      
    // here change the width to 8 and height to 6 using our new methods
    rectangle.setHeight(6);
    rectangle.setWidth(8);



### Custom Constructors

    function Person(name,age) {
      this.name = name;
      this.age = age;
    }

    // Let's make bob and susan again, using our constructor
    var bob = new Person("Bob Smith", 30);
    var susan = new Person("Susan Jordan", 25);
    // help us make george, whose name is "George Washington" and age is 275
    var george = new Person("George Washington", 275);



### Method in constructor

    var james = {
        job: "programmer",
        married: false,
        speak: function( feeling ) {
            console.log("Hello, I am feeling " + feeling);
        }
    };

    james.speak("great");
    james.speak("just okay");


### hasOwnProperty

    var suitcase = {
        shirt: "Hawaiian"
    };

    if(suitcase.hasOwnProperty("shorts")){
        console.log(suitcase.shorts);
    }else{
        suitcase.shorts = "beach shorts";  
        console.log(suitcase. shorts)
    }


### for in

    var nyc = {
        fullName: "New York City",
        mayor: "Bill de Blasio",
        population: 8000000,
        boroughs: 5
    };

    for(var value in nyc){
        console.log(nyc[value]);
    }


### class

    function Person(name,age) {
      this.name = name;
      this.age = age;
    }

    var printPersonName = function (p) {
      console.log(p.name);
    };

    var bob = new Person("Bob Smith", 30);
    printPersonName(bob);

    var me = new Person("Love Yagi", 2);
    printPersonName(me);

### prototype

    function Cat(name, breed) {
        this.name = name;
        this.breed = breed;
    }

    var cheshire = new Cat("Cheshire Cat", "British Shorthair");
    var gary = new Cat("Gary", "Domestic Shorthair");
    var love = new Cat("Love", "Tuxedo");

    // add a method "meow" to the Cat class that will allow
    // all cats to print "Meow!" to the console
    Cat.prototype.meow = function(sound){
        console.log(sound);
    };

    // add code here to make the cats meow!
    cheshire.meow("Meow");
    gary.meow("Meooow!");
    love.meow("Meoooooowwww!");


### Inheritence

    function Animal(name, numLegs) {
        this.name = name;
        this.numLegs = numLegs;
    }

    Animal.prototype.sayName = function() {
        console.log("Hi my name is " + this.name);
    };

    function Penguin(name) {
        this.name = name;
        this.numLegs = 2;
    }

    Penguin.prototype = new Animal();
    var penguin = new Penguin("Pen");
    penguin.sayName();


### Accessing Private Variables

    function Person(first,last,age) {
       this.firstname = first;
       this.lastname = last;
       this.age = age;
       var bankBalance = 7500;
      
       this.getBalance = function() {
          return bankBalance;
       };
    }

    var john = new Person('John','Smith',30);

    var myBalance = john.getBalance();
    console.log(myBalance);


### Private Methods

    function Person(first,last,age) {
       this.firstname = first;
       this.lastname = last;
       this.age = age;
       var bankBalance = 7500;
      
       var returnBalance = function() {
          return bankBalance;
       };
           
       // create the new function here
       this.askTeller = function(){
            return returnBalance;
        }
    }

    var john = new Person('John','Smith',30);
    var myBalanceMethod = john.askTeller();
    var myBalance = myBalanceMethod();
    console.log(myBalance);


### For in - typeof

    var languages = {
        english: "Hello!",
        french: "Bonjour!",
        notALanguage: 4,
        spanish: "Hola!"
    };


    for(var prop in languages){
        if(typeof languages[prop] === "string"){
            console.log(languages[prop]);
        }
    }


### prototype

    function Dog (breed) {
        this.breed = breed;
    };

    Dog.prototype.sayHello = function(breed){
        console.log("Hello this is a " + this.breed + " dog")
    };

    var yourDog = new Dog("golden retriever");
    yourDog.sayHello();

    var myDog = new Dog("dachshund");
    myDog.sayHello();





### Lots of methods

    function StaffMember(name,discountPercent){
        this.name = name;
        this.discountPercent = discountPercent;
    }

    var sally = new StaffMember("Sally",5);
    var bob = new StaffMember("Bob",10);

    // Create yourself again as 'me' with a staff discount of 20%
    var me = new StaffMember("me",20);

    var cashRegister = {
        total:0,
        lastTransactionAmount: 0,
        add: function(itemCost){
            this.total += (itemCost || 0);
            this.lastTransactionAmount = itemCost;
        },
        scan: function(item,quantity){
            switch (item){
            case "eggs": this.add(0.98 * quantity); break;
            case "milk": this.add(1.23 * quantity); break;
            case "magazine": this.add(4.99 * quantity); break;
            case "chocolate": this.add(0.45 * quantity); break;
            }
            return true;
        },
        voidLastTransaction : function(){
            this.total -= this.lastTransactionAmount;
            this.lastTransactionAmount = 0;
        },
        // Create a new method applyStaffDiscount here
        applyStaffDiscount: function(employee){
            this.total -= this.total * (employee.discountPercent / 100);
        }
    };

    cashRegister.scan('eggs',1);
    cashRegister.scan('milk',1);
    cashRegister.scan('magazine',3);
    // Apply your staff discount by passing the 'me' object 
    // to applyStaffDiscount
    cashRegister.applyStaffDiscount(me);

    // Show the total bill
    console.log('Your bill is '+cashRegister.total.toFixed(2));




