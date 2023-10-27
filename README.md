# Java-Novel-Interpreter
A java program to interprete / generate a novel from a story model

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/574dab06-cc5c-4435-8d9f-2a3cb8515f09)

# How it works ?
The interpreter needs in input the source code of a story model (must be written by the human author). So the human author creates the story world and the rules in a specific language (defined later), then the Java Novel Interpeter chooses a possible path.

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/1a696fe3-c8be-4c6b-aa08-59e381369f0d)

# How to write the source code of your story model ?
In theory you just need a text editor :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/57cdbecc-9ae4-46a4-b4f0-723a2fc5b211)

The root element is <story> :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/807ffc60-ac37-4df5-a934-9115f79c1916)

It contains four attributes :
- title : the title of the story model
- author : the author of the sotry model
- startPoint : the node ID where the interpreter starts to generate a story
- length : the number of nodes that the interpreter has to going throw

The main element is <node> :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/bdbc0534-9f5e-4c71-a574-9393dfa9163d)

When the sotry model become too big, you may use a dedicated editor (at least to visualize graphically the story world). In the example, the file is converted in Cmap format and can be visualized with CmapTools :

![image](https://github.com/JNovGen/Java-Novel-Interpreter/assets/120131145/5f1997ea-c9c6-48d2-9fc7-9d460d6ab822)



