- Source: codecademy.com
- Course: Learn Go
- Year: 2022

**TOPICS**

1. GETTING STARTED	
- I will introducE the basic of GO. For more information, please click on: https://go.dev/doc/ to visit the Go's mainpage
	- Basic:
		+ First line: Package Declaration - create an executable or library
			```
			package main
			```
		+ Second line: Bringing in and using code from other packages. Use " ". 
			```	
			import "fmt" //importing the fmt package
			```
	- Running Go project:
		+ There are two ways to run Go file:
			* 1st way:
				```
				go build main.go //compile Go 
				./ main //run the compiled file
				```
			* 2nd way:
				```
 				go run main.go //Compile and Run the file
				```
	- Functions:
		+ Format of function:
		 	```
			func [NameOfFunction] (){
			fmt.Println("Hello World")}
			```
 	- Importing multiple packages:
		+ More packages: https://pkg.go.dev/std
			```
			import (
				"package1"
				"package2"
			)//each package is seperated by LINE, not by any special characters.
			```
		+ Using ALIAS 
			```
			import (p1 "package1") //p1 is an ALIAS.
			```
 	- Comments
		+ // This is a comment
		+ /* This is a block comment */
 	- Go Resources: 
 	 	+ https://go.dev/
		+ We can also look up Go document by typing **go doc [package_name]**
			```
			go doc fmt.Println //It will return the whole docs of Println
			```
---
2. VARIABLES, VALUES, AND FORMATING</summary>
- Next, I will introduct Variable, Values and Fomarting
	- Literals: numbers, strings, etc.
		+ add (+), substract (-), multiply (*), divide (/), remainder (%)
			```	
			fmt.Println(2*3) //6
			```	

	- Constants cannot be UPDATED when the program is RUNNING
		```
		constconst funcFact = "1+1=2"
		fmt.Println(funFact) //Prints: 2
		```

	- Data Type: THREE basic catagories for NUMBERS:
		+ int
		+ float
		+ complex
	
	- Basic Numeric Types in Go: 
	 	+ 15 different numeric types
		+ Clikc here for more information: https://go.dev/ref/spec#Numeric_types
	
	- Variables: 
		+ Can change during the running of a program
		+ ```var [prefered_name] [type]```
			```	
			var lengthOfSong uint16
			```	
	- Reading Errors
		+ Format: ./[package_name]:[line_number]:[column_number]
		+ ```./main.go:4:7: numberWheels declared and not used```
	
	- Assigning Variables:
		+ Variables are placeholder names
		+ Updating variables is called **ASSIGNING** a value to variable
		+ Use "=" to assign value to variable
			```
			var kilometersToMars int32 //declaring to variable
			kilometerToMars = 62100000 //assigning value to that variable
			```	
		+ OR: 
			```
		 	var kilometersToMars int32= = 61200000
			```		
	- String: 
		+ A signe quote ' cannot be used to define strings.
			```
			var myfavoriteFood string = "Pho"
			fmt.Println("My favorite food is " + myfavoriteFood) //Prints: My favorite food is Pho
			```
	- Zero Values:
		+ All numeric var have a value of 0 BEFORE assignment
			```
			var emptyFloat float32 
			fmt.Println(emptyFloat) //Prints: 0
			```
		+ String var have a default value of " ", or can be called **an empty string**
		+ Boolean var have a default value of FALSE

	- Inferring Type:
		+ `:=` is used to create the var and infer its type based on the VALUE PROVIDE
			```
			workTomorrow := true //boolean value assigned
			```
		+ There are **two ways** of inferring type:
			`friendName := "SizC"` or
			`var friendName = "SizC"`
		+ Checking type of a variable:  ```fmt.Printf("Type is: %T", [variable])```

	- Default int Type:
		+int vs. uint (unsigned integer)

	- Updating Variables:
		+ `+=`: to add from the var
		+ `-+`: to substract from the var
		+ `*=`: to multiply the var by a factor
		+ `/=`: to divide the var by a dividend
		+ Example 1:
			```
			command := "Hold"
			person := "me!"
			command += person
			fmt.Println (command) //Hold me!
			```
		+ Example 2:
			```
			$coolSneakers := 65.99
			niceNecklace := 45.50
			var taxCalculation float64
			taxCalculation += coolSneakers
			taxCalculation += niceNecklace
			// Compute the NYC sales tax
			// 8.875% of the purchase here:
			taxCalculation *= 0.08875
			fmt.Println("Purchase of", coolSneakers + niceNecklace, "with 8.875% sales tax", taxCalculation, "equal to", coolSneakers + niceNecklace + taxCalculation)
			```

	- Multiple var Declaration:
		+ We can combine all the variable with the same type or different types in one line
			```
			var part1, part2 string //both are strings. Same type.
			quote, fact := "The sun is bigger than the moon", true //string, boolean. Different type.
			```
---
3. FMT PACKAGES
	1. The Print method:
		$fmt.Println() //Print in line, line break
		$fmt.Print() //No line break
			- Example 1:
				$fmt.Print("Hello! ")
				$fmt.Print("How are you?") //Hello! How are you?
				-Example 2:
				$fmt.Print("How","are","you?") //Howareyou?
				$fmt.Println("How", "are", "you?") //How are you?

	2. The Prinf method with %v:
		- %v is a place holder - verb in Golang
			- Example:
				$food := "Pho"
				$price := "$12.99"
				$fmt.Printf("Your %v costs %v", food, price) //Your Pho costs $12.99
				//If we swap the arguemtns: pho and price, the result will change.

	3. Different Verbs:
		- Different other verbs: https://pkg.go.dev/fmt#hdr-Printing
		- %T - checking the type of selected agurment
			$floatExample := 1.75
			$fmt.Println("Working with a %T", floatExample) //Working with a float64
		- %d - interpolating a number into a string 
			$month := 01
			$year := 1997
			$fmt.Printf("I was born in %d/%d") //I was born in 01/1997
		- %f - can limit how percise we want the value to be 
		- %.2f - 2 decimal point (price)
	
	4. Sprint and Sprintln:
		- These methods fmt.Sprint()-no space- & fmt.Sprintln()-inclusing space- format not print out the statement
			- Example:
				$name:= "Tran"
				$iSay := fmt.Sprint("This is ", name)
				$fmt.Print(iSay) //This is Tran
	
	5. Srpintf method:
		- Works as the Printf method
		
	6. Getting User Input:
		- fmt.Scan(): allows to get user input
			- Example:
				$var response1 string 
				$var response2 string 
				$fmt.Scan(&response1)
				$fmt.Scan(&response2)
				$fmt.Printf("I'm %v %v", response1, response2)

4. CONDITIONALS
	1. The if Statement:
		$if [condition := true] { Result follows by conditions }
		
	2. The else statement:
		- provide another result based on the conditon
		$if [condition := true] {Result 1} else {Rersult 2}
		
	3. The else if statement:
		$if condition1 { Result 1} else if condition2 { Result 2 } else condtion3 { Result 3 }
		
	4. The switch statement:
		$switch condition {
		$	case "a" or 1:
		$	case "b" or 2: 
		$	default: } 
		
	5. Comparison Operators:
		- Comparison operators are used to check more than 1 condition
		- == : Is equal to
		- != : Is NOT equal to
		- <  : Less than
		- >  : Greater than
		- <= : Less than or equal to
		- >= : Greater than or equal to
		
	6. Logical Operators (And, Or):
		- Check multiple conditons
		- %% : And
		- || : Or
		- !  : Not -> negates (reverses) the value of a boolean
		
	7. Scoped Short Declaration Statement:
		- if statement:
			$x := 1
			$y := 2
			$if product := x * y; product > 1 { fmt. Println ("WOW")} //WOW
			Error case:
				$fmt.Println(product) //./main.go:11:13: undefined: product --> product is out of scope
		- switch statement:
			$switch season := "summer" ; season {
			$case "summer":
			$	fmt.Println("Go out and enjoy the sun!")} 
			
	8. Randomizing:
		- imporing "math/rand"
		$fmt.Println(rand.Intn(100)) //If we run the code multiple times, it always return 81
			- Example
				$amountLeft := rand.Intn(1000)
				$fmt.Println("amountLeft is: ", amountLeft) //1081
			
	9. Seeding:
		- By default, the NEW seed value is 1
		$rand.Seed([passing an integer])
*****		Random Num:
			$rand.Seed(time(Now).UnixNano())
			$randomNumber := rand.Intn(100)
			$fmt.Println(randomNumber) //it will generate different NUM every time

5. FUNCTIONS
	1. Using Functions:
		- func [func_name] (parameters?) {do something...}
		
	2. Scope:
		- Is a concept that refers to where the values and functions are defined and where they can accessed
		- When a var is defined within a function, that var is only asseccible within that funciton.
		
 	3. Returning Values from Functions:
		- When return a value, we pass the value to another place in our code.
		- A func can be given a RETURN type - the type of returned value.
			-Example 1:
				$func gettingAge() int32 {
				$	myAge := 18
				$	return myAge } 
				$func main() {
				$	var myAge int32
				$	myAge = gettingMyAge()
				$	fmt.Println(myAge)} //Prints: 18
				
	4. Using Func Parameters:
		- Func para are variables that are used within the function to use in some sort of computation or calculation
		- Arguments are values that we want those parameters to take
			- Example
				$func multiplier(x, y int32) int32 {
				$	return x * y}
				$func main (){
				$	var A, B, product int32
				$	A = 2
				$	B = 3
				$	product = multiplier (A, B)
				$	fmt.Println(product)} //Prints: 6

	5. Reusing Code with Func:
		- Make your code shorter and more organized by using func
			- Example
				$fmt.Println(5*5)
				$......
				$fmt.Println(10*10)
				- Issue: 5 same lines. Let's clean up the code!
				$func squareNum(x int){
				$	fmt.Println(x*x) //Prints: 25
			
	6. Multiple Return Values:
		- Functions also have ability to return multiple values
			- Example:
				$func myExample(x int) (string, int){
				$	var stringEx string
				$	var numEx int
				$	switch x {
				$		case 1:
				$			numEx = 10
				$			stringEx = "String1"
				$		case 2:
				$			numEx = 20
				$			stringEx = "String 2" }//close SWITCH
				$	return stringEx, numEx }
				$func main(){
				$	var getString string
				$	var getNum int
				$	getString, getNum = myExample(2)}
				$	fmt.Println(getStringm getNum) //Prints: String 2, 20
				
	7. Deferring Resolution:
		- We can delay a func call to THE END oif the CURRENT SCOPE by using DEFER
		$defer delayFunction() //the delayFunction will execute at the end

6. ADDRESSES AND POINTERS
	1. Usage of pointers & addresses:
		- The ability to change values from a DIFFERENT SCOPES using: ADDRESSES, POINTERS, DEREFERCING
		
	2. Addresses:
		- Instead of writting info. down in the memory, it will be SPACE which can be used to store value - ADDRESSES
		- To find a var's address we use "&" followed by the var name
			$x := "My very first address"
			$fmt.Println(&x) //Prints: 0x414020
			
	3. Pointers:
		- Pointers are used to store value in the specific address
			$var pointerForInt *int
				- the "*" signifies that this var will store an address
				- the "int" means that the address contains an integer value
			-Example:
				$star := "Hello"
				$starAddress := &star
				$fmt.Println(starAddress) //Prints: 0xc000010230
				
	4. Dereferecing:
		- We can use our pointer to access the address and change its value. This action is called DEFERECING or INDIRECTING
			- Example:
				$lyrics := "Lalala"
				$pointerForLyrics := &lyrics
				$*pointerForLyrics = "Hihihi"
				$fmt.Println(lyrics) //Prints: Hihihi
				
	5.Changing Values in Different Scopes:
			-Example:
				$func addHundred (numPtr *int) {
				$	*numPtr += 100}
				$func main() {
				$	x:= 1
				$	addHundred (&x)
				$	fmt.Println(x) //Prints 101}		

				
				