# doc-PosNeg-analysis

### create model
------------
It'll take a long enough time depends on the n-gram words chosen (see -min and -max)<br />
java -classpath weka.jar weka.classifiers.meta.FilteredClassifier -t SFU_Review_Corpus.arff -no-cv -d smo.model.dat -v -F "weka.filters.MultiFilter -F \"weka.filters.unsupervised.attribute.StringToWordVector -O -tokenizer \\\"weka.core.tokenizers.NGramTokenizer -delimiters \\\\\\\"\\\\\\\W\\\\\\\" -min 1 -max 3\\\" -W 10000000\" -F \"weka.filters.supervised.attribute.AttributeSelection -E weka.attributeSelection.InfoGainAttributeEval -S \\\"weka.attributeSelection.Ranker -T 0.0\\\"\"" -W weka.classifiers.functions.SMO

### compile java code & jar file
------------
javac -cp ".;weka.jar;" SentimentClassifier.java

### run java code & jar file
------------
java -cp ".;weka.jar;" SentimentClassifier caryes1.txt smo.model.dat

### simple test case
------------
It'll take a long enough time as it needs to load the model<br /><br />
===== Loaded text data: caryes2.txt =====
 i'm lazy
===== Loaded model: smo.model.dat =====
===== Instance created with reference dataset =====
@relation 'Test relation'

@attribute text string
@attribute @@class@@ {no,yes}

@data
' i\'m lazy',?
===== Classified instance =====
Class predicted: no