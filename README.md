# Movie Project 

This is the movie search list project. This project will display a default list of movies that is iterated through and compared to a movie inputted by the user. 

* Compares user strings in list displayed, ignoring case
* The most recent search will appear in the top of the list
* When user exits program, data will be saved and exported to file

### Quick start
**Make sure you have Windows OS version 8 or Linux OS**
**or
**Access to internet to run on Rep Lit

> Clone/Download the solution then run `main.rb`

```

# Download all files from canvas

# For Windows
$ ruby main.rb

```

# Table of Contents
* [Problem](#Problem)
* [Installing](#installing)
* [API](#API)
* [License](#license)
* [Author](#author)

#### Problem

Some interesting stuff here .......

___

#### Installing

There are no futher installation requirments for this project. SImply run on Rep Lit or accessory ruby IDE.

___

#### API

The accomodating methods and classes below describes how main.rb creates an instance of the movie list and updates the list.
```
Class SearchController

attr_accessor :searchSuggestionList 

  ####
  #
  #1. contstuctor for controller class
  #2. contains search list
  #
  ####
	def initialize(search_list = [])
    @searchSuggestionList = search_list
  end

  ####
  #
  #1. prints list
  #
  #
  ####	
  def showList()
		puts @searchSuggestionList
	end

	##### 
	#
	# 1.save updated search suggestion list to "data.txt" file 
	#
	#####
	def saveListToFile()
		out_file = File.new("data.txt", "a")
    out_file.puts(@searchSuggestionList)
    out_file.close
	end
end
```
```
def updateList(movie_name)	
  for movie in @searchSuggestionList
      if movie.downcase.eql? movie_name.downcase 
        @searchSuggestionList.delete(movie)
        @searchSuggestionList.unshift(movie_name)
        return
      end
    end
    @searchSuggestionList.unshift(movie_name)
end
```
___

#### Result of Sample Test Case

some image or output is shown by Foo program execution......

___

#### License
 [Auburn University](/LICENSE)

___

## Author
 [Marvin Royal](/LICENSE)
