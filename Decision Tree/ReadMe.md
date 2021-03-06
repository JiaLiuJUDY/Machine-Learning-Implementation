This folder contains all information to build a simple decision-tree from nothing. To be simplify, this program assume that the class attribute is binary. It can handle both numeric and nominal features.
The program is callable from the command line through:
   *dt-learn <train-set-file> <test-set-file> m*
The program's output will print the tree learned from the training set, its prediction for the set-set instances and the number of training instances of each class after each node.

* **code folder**: The Python code for ID3-like classification decision-tree learner.
  * Candidate splite:
    * Candidate splits for nominal features have one branch per value of the nominal feature. The branches are ordered according to the order of the feature values listed in the given ARFF file.
    * Candidate splits for numeric features  use the thresholds that are midpoints between values in the given set of instances. The left branch of such a split represents values that are less than or equal to the threshold.
  * Splits are chosen using information gain. 
    * If there is a tie between two features in their information gain, break the tie in favor of the feature listed first in the header section of the ARFF file. 
    * If there is a tie between two different thresholds for a numeric feature, breakt the tie in favor of the smaller threshold.
  * Stopping ctiteria for making a node into a leaf are:
    * all of the training instances reaching the node belong to the same class, or
    * there are fewer than *m* training instances reaching the node, where *m* is a input provided to the program by user, or
    * no feature has positive information gain, or
    * there are no more remaining candidate splits at the node'
  * If the classes of the training instances reaching a leaf are euqally represented, the leaf will predict the most common class of instances reaching its parent node.
  * If the number of instances that reach a leaf node is 0, the leaf should predict the most common class of instances reaching its parent node.
  
  
* **data folder**: The test data to evaluate the preformance of the self build learner. The test data is generate enough to contain both numeric and nominal attributes.


