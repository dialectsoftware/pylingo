## pylingo

Pylingo is a general purpose declarative grammar.

The following template approximates the syntax. Below that is an example of a valid grammar file.

```bash

config {
  [key = object | array | "string" | number | json | DOC ]+
}

import alias {
  [key = object | array | "string"| number | json | DOC ]+
}

variable [namespace]* name {
	[key = object | array | "string" | number | json | DOC ]+
}

data [namespace]+ name {
    [key = object | array | "string" | number | json | DOC]+
}

generator [namespace]+ name {
  [key =  object | array | "string" | number | json | DOC ]+
}

```

Example of a valid grammar file:

```bash

config {
   key1 = "value1"
   key2 {
	   key3 = 10
	   key4 = ["my","array",10]
     key5 {
          one = 1
          two = "2"
     }
   }
}

import name {
	key="value"
}

variable name1 name2 {
	description = "description"
	default = "@default"
}

data name1 name2 self {
	key = "value"
}


#This is a comment
generator name1 name2 self {
    key = "value"
    number = 100
		array = ["this","is","an","array"]
    numbers = [1,2,3,4,5]
		object {
			attribute1 = "value1"
			attribute2 = []
      attribute3 =  10
			attribute4 {
				subattribute = "value"
			}
		}
		json = {
            "key":"value",
            "key1":10,
            "key2" : {
              "key3":"value",
              "key4":{ }
				    }
		  }
    complex_array=[
      {
        "key":"value",
        "key2" : {
          "key3":"value",
          "key4":{ }
        }
		  },
      {
        "key":"value",
        "key2" : {
          "key3":"value",
          "key4":{ }
        }
		  }]
		doc=<<DOC
		{
        "key":"value",
        "key2" : {
          "key3":"value",
          "key4":{ },
          "key5":5
        }
		}
		DOC
}



```

