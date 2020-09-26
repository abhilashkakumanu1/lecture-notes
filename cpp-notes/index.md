# C++ Notes
This notes is inspired from a C++ [crash course](https://youtu.be/vLnPwxZdW4Y) by FCC
## Classes and Objects
Built-in data types linke `string, int, double, char` let's us create variable to store corresponding types of data. The problem with this approach is that there are lot of "things" or real world entities which can't be represented using just number, string or bool. For example, I can't represent my phone for example using a string or number.
Consider if we want to work with books. In this program I need to somehow represent books. There is no book data type. The only problem is having a limited number of data types. __Classes__ are used to solve this problem, to create a blue print for new type of data, i.e, blue print for custom data types.
```cpp
class Book{
	public: 
		string title;
		string author;
		int pages;
}

int main(){
	Book book1;
	book1.title = "Harry Potter";
	book1.author = "JK Rowling";
	book1.pages = 500;
	return 0;
}
```
We define the book by creating __attributes__ using the built-in datatypes. Basically, I am just _mapping out_ what book is gonna be and what its gonna have. Class is just a blue print. In order to use it, we have to create a __instance__ of it (called as __Object__)

### Constructor functions
```cpp
class Book{
	public: 
		string title;
		string author;
		int pages;
		
		// Default params
		Book(){
			title = "no title";
			author = "no author";
			pages = 0;
		}
		
		Book(string aTitle, string aAuthor, int aPages){
			title = aTitle;
			author = aAuthor;
			pages = aPages;
		}
}

int main(){
	Book book1("Harry Potter", "JK Rowling", 500);
	cout << book1.pages << endl;
	
	return 0;
}		
```
A constructor is a special function that is gonna get called whenever we create an Object of a class.
"a" (meaning attribute) infront the is used to differentiate them.

Multiple constructors gives user to create the Objects in multiple ways. Here we are using them to provide default values to the parameters.

### Object Functions or Methods
```cpp
class Student{
	public: 
		string name;
		string major;
		double gpa;
		
		Student(string aName, string aMajor, double aGpa){
			name = aName;
			major = aMajor;
			gpa = aGpa;
		}
		
		bool hasHonors(){
			if(gpa>=3.5){
				return true;
			}
			return false;
		}
}

int main(){
	Student student1("Jim", "Art", 3.6);
	cout << student1.hasHonors();
	return 0;
}
```
### Getters and Setters
These allow you to __control the access__ to different attributes inside the C++ classes.

In this example, if the user enters a invalid rating, we set it as NR (not rated). We are doing this by making rating as a private attribute
```cpp
class Movie{
	private:
		string rating;
	public: 
		string title;
		string director;
		
		Movie(string aTitle, string aDirector, string aRating){
			title = aTitle
			director = aDirector;
			setRating(aRating);
		}
		
		void setRating(string aRating){
			if(aRating == "G" || aRating == "PG" || aRating == "PG-13" || aRating == "R" || aRating == "NR"){
				rating = aRating;
			} else {
				rating = "NR";
			}
		}
		string getRating(){
			return rating;
		}
}

int main(){
	Movie avengers("The Avengers", "Joss Whedon", "PG-13");
	// cout << avengers.rating(); => This gives an error as we can't access rating.
	cout << avengers.getRating() << endl;
	return 0;
}
```
If we put an attribute inside `private` , then only code inside the class can access that attribute.
### Inheritence
Parent class is also called __super class__ and child class as __sub class__
```cpp
class ChildClass : public ParentClass{
	// Here we can ovveride certain functionality of parent class by redefining them
}
```
