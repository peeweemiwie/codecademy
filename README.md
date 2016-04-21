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
