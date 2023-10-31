# Java-Novel-Interpreter
A java program to interprete / generate a novel from a story model. You can download and run the java runnable version or import in Eclipse IDE the java project.

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/574dab06-cc5c-4435-8d9f-2a3cb8515f09)

# How it works ?
The interpreter needs in input the source code of a story model (must be written by the human author). So the human author creates the story world and the rules in a specific language (defined later), then the Java Novel Interpeter chooses a possible path (based on Markov chain principle).

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/1a696fe3-c8be-4c6b-aa08-59e381369f0d)

# How to write the source code of your story model ?
In theory you just need a text editor :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/57cdbecc-9ae4-46a4-b4f0-723a2fc5b211)

The root element is "story" :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/807ffc60-ac37-4df5-a934-9115f79c1916)

It contains four attributes :
- title : the title of the story model
- author : the author of the story model
- startPoint : the node ID where the interpreter starts to generate a story
- length : the number of nodes that the interpreter has to going throw

The main element is "node" :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/bdbc0534-9f5e-4c71-a574-9393dfa9163d)
![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/0a9ed46e-f874-4a8f-a5bd-e1226b1ae756)

The node element contains height attributes :
- id : the unique identifier of a node
- textcontent : contains the text that will be displayed during the execution. In the field description, the character “#” is recognized as a separator for different version of the text but to express the same idea. It permits to vary the vocabulary; this way it would be not too repetitive when passing again in the same node. For example: “The room is dark.#There is no light in the room and it’s hard to see something#The room is very dark, it’s impossible to see something.” When passing in this node the interpreter will take randomly one of the different version of the text description. The text description can also be used to display the content of the
memory.
- memoryAdd : it indicates to the interpreter to set up the global memory of the story. For example : memoryAdd="FOOD*3", means to the interpreter to add 3 to the FOOD variable, you don't need to declare first the variable. You can also set a value, for example memoryAdd="FOOD=0".
- memoryRemove : same principle but to remove elements from the global memory : memoryAdd="FOOD*2", means to the interpreter to remove 2 to the FOOD variable, you don't need to declare first the variable.
- memoryCondition : Before entering a node, the program first has to determine which node it can enter in. So, if a node contains a condition, the program will check the statement. You can only make one statement for
each node.You can use the operators: <, >, =, >=, <= to compare with integer number or with other element of memory. For example : memoryCondition="FOOD>0".
- nextNodes : contains a set of nodes identifier that will be executed next. If you put nextNodes="node1", the interpreter will try to execute the next node called "node1".  If you put nextNodes="node1,node2,node3", the interpreter will randomly choose one of the three nodes (depending also the condition)".
- unique : means if the interpreter can throw more times or not in the same node. unique can take two values : "false" or "true".
- variable : you can set here variable names that as used in textContent. For example : textContent="The survivor had only FOOD tins left." so in the variable field you will have : variable="FOOD". The interpreter will replace the value of FOOD in the text description.

# Using the interpreter
- At first you need to load a story model :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/d3a38c37-5782-45ab-9eb1-3effbe70cd58)

So click on "open a story", and choose your file. Then the program will load all the nodes of the story model :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/8907f207-df63-4a8c-b9b3-021e881ed0f1)

You can also browse node information, it will display what is written in the xml file.

- Generate a story from the source code of the story model :
  
Going to the "run" panel :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/1002d692-ad2b-4955-8138-d3b86b38183d)


You can choose a start point, a story length, from these parameters the interpreter will generate a story by choosing a path in your story model. You can use the button "reset path" to force the generate a new story and not use an existing path. By using the button "Run story", the interpreter will execute the story model (by choosing a path) and generate a story. A story is a chosen path in story model. Below is an example of output.

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/c5c0eb37-9ee9-4eed-8132-698447ce91e0)

You can use the button "Show progress", it's like a debug mode, it will show up the nodes chosen and the memory state at each step :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/9480c28f-e6e0-4891-bb28-1481beeec1b0)

# Advice

When the story model become too big, you may use a dedicated editor (at least to visualize graphically the story world). In the example, the file is converted in Cmap format and can be visualized with CmapTools :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/5f1997ea-c9c6-48d2-9fc7-9d460d6ab822)

# Conclusion

The program doesn't invent anything, but deduces a story from the information and rules provided by the user.

