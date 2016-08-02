# doc-PosNeg-analysis

### creating model
------------
It'll take a long enough time depends on the n-gram words chosen (see -min and -max)<br />
Just execute the **learn.sh** file<br /><br />
If you can't run the bash file, you can simply copy the code and execute it on Terminal.

### compiling java code & jar file
------------
javac -cp ".;weka.jar;" SentimentClassifier.java

### running java code & jar file
------------
java -cp ".;weka.jar;" SentimentClassifier caryes1.txt smo.model.dat

### a very simple test case
------------
It'll take a long enough time as it needs to load the model<br /><br />
===== Loaded text data: caryes2.txt =====<br />
 i'm lazy<br />
===== Loaded model: smo.model.dat =====<br />
===== Instance created with reference dataset =====<br />
@relation 'Test relation'<br />

@attribute text string<br />
@attribute @@class@@ {no,yes}<br />

@data<br />
' i\'m lazy',?<br />
===== Classified instance =====<br />
Class predicted: no

