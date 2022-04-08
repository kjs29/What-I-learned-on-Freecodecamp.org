# What-I-learned-on-Freecodecamp.org
&lt;script async src="//jsfiddle.net/kjs3980/4snyhzf9/145/embed/">&lt;/script


function testEqual(val,b) {
	if (val !== b) {
  	return "Not Equal";
  }
  return "Equal";
}
console.log(testEqual("12",12));


function testing(val) {
	if (val <=50 && val >=25) {
  	return "Yes";
  }
}
/*console.log(typeof testing(22))

console.log(typeof testing(44))
*/

let names = ["holeinone","eagle","birdie","par","bogey","double Bogey","go home"]
function test(strokes,par) {
	if (strokes == 1) {
		return names[0];
	} else if (strokes <= par - 2) {
		return names[1];
	} else if (strokes <= par - 1) {
		return names[2];
	} else if (strokes == par) {
		return names[3];
	} else if (strokes == par + 1) {
		return names[4];
	}	else if (strokes == par + 2) {
		return names[5];
	} else if (strokes >= par + 3) {
		return names[6]
  	}
}


console.log(test(8,5));


function caseIn(val) {
	let answer = "";
  switch (val) {
  	case 1:
  		answer = "alpha";
  		break;
  	case 2:
    	answer = "Beta";
      break;
    case 3:
    	answer = "gamma";
      break;
    case 4:
    	answer = "delta";
      break;
    default:
    	answer = "none";
    	break;
  }
  return answer;
}

console.log(caseIn(555));
/*
function chainToSwitch(val) {
let answer = "";
}

switch (val) {
	case "bob":
  	answer = "marley";
    break;
  case 42:
  	answer = "the Answer";
    break;
  case 1:
  	answer = "no there is n 1";
    break;
  case 99:
  	answer = "missed me by this much!";
    break;
  case 7:
  	answer = "ate night";
    break;
}
*/

let count = 0;
function cc(card) {
	switch(card) {
  	case 2:
    case 3:
    case 4:
    case 5:
    case 6:
    	count ++;
    	break;
   	case 10:
    case "J":
    case "Q":
    case "K":
    case "A":
    	count --;
      break;    
  }
  let holdbet = "Hold";
  if (count>0) {
  	holdbet = "Bet";
  }
  return count +" " + holdbet;
}
console.log(cc(2));
console.log(count);
cc(5);
console.log(count);
cc("K"); cc("Q");
console.log(count);

let myDog = {
	"name" : "Quincy",
  "legs" : 3,
  "nose" : 1,
  "friends": ["Fred"]
};
console.log(myDog)

//There are two ways to access to object properties: dot notation, and bracket notation.
let myDogsName = myDog.name;//dot notation
console.log(myDogsName);
let myDogsFriends = myDog.friends;
console.log(myDogsFriends);

let myDogsLegs = myDog["legs"];//bracket notation
console.log(myDogsLegs);
let myDogsNose = myDog['nose'];
console.log(myDogsNose);

//we can also access to object's properties using other variables.
let testObj = {
	1: "Do",
  2: "Re",
  3: "Mi"
}

let theFirst = 1;
let testObjFirst = testObj[theFirst+1];
console.log(testObjFirst);

//We can also modify objects properties using a dot notation
myDog.name = "Happy Quincy"
console.log(myDog);
myDog["name"] = "Excited Quincy";
console.log(myDog);

//We can also add a new property using dot notation or bracket notation

myDog["bark"] = "Woof!";
console.log(myDog);

//we can delete properties using dot or bracket notation.

delete myDog.bark; //dot notation
console.log(myDog)

delete myDog["nose"]; //bracket notation
console.log(myDog);

myDog.nose = 5;
console.log(myDog)

//we don't need to use "" to assign properties in objects.
let myCat = {
	frontLeg : 2, //no "" around frontLeg
  tail : 1 //no '' or "" around tail
}
console.log(myCat)

delete myCat['tail'];
console.log(myCat)

delete myCat.frontLeg
console.log(myCat);

myCat['nose'] = 1
myCat.tail = 1
myCat['frontLeg'] = 2
myCat.color = "black"
console.log(myCat)

//check property
function checkObj(checkProp) {
	if (myCat.hasOwnProperty(checkProp)) {
  	return "Yes" + " , " + myCat[checkProp];
  } else {
  	return "Not Found";
  }
}

console.log(checkObj("tail"));
console.log(checkObj("Hello"));


//manipulating complex objects

let album = {
 "artist" : "MJ",
 "year": 1992,
 "family" : {
 "son": "son MJ",
 "wifes lastName" : "wife J"
 }
}
console.log(album)

//access to complex objects using dot notation , and bracket notation

let accessTo = album["family"]; //we have to use "" when we access to objects using bracket notation
console.log(accessTo)

console.log(album.family["wifes lastName"]) //we have to use bracket notation to access to properties that have space. ex) wifes lastName

let myPlants = [
{
	type : "flowers", 
  list: [
  	"rose",
    "tulip",
    "lily"
    ]
 },
{
 type: "trees", 
 list : [
 	"fir",
 	"pine",
  "birch"
 	]
 }
]
console.log(myPlants);

//To get the second tree's value
let secondTree = myPlants[1]["list"][1]
console.log(secondTree)


//small coding challenge
let collection = {
"1223" : {
"artist" : "Queen",
"album" : "We are the rock"
},
"3451" : {
"artist" : "MJ",
"album" : "Man in the mirror",
"tracks" : ["1999", "Little Red Corvette"]
}
}

let collectionCopy = JSON.parse(JSON.stringify(collection));

function updateRecords(id, prop, value) {
	if (value ===  "") {
  delete collection[id][prop];
  } else if (prop === "tracks"){
  collection[id][prop] = collection[id][prop] || [];
  collection[id][prop].push(value);
  } else {
  collection[id][prop] = value;
  }
}
console.log(collection);
updateRecords(3451,"tracks","test")
console.log(updateRecords(3451,'tracks',"test"))

let myArray = [];
let i = 0;
while (i<5) {
	myArray.push(i);
  i++;
}
console.log(myArray);


