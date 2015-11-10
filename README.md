# Natural-Language-Processing-Using-Hidden-Markov-Models

Implemented a basic English sentence recognizer based on Hidden Markov Models. This version has only very limited vocabulary and does not use articles or prepositions. Only the following words are included in the vocabulary supported by the HMM: 
<li> 
{"do" "can" "computers" "students" "movies" "develop" "play" "games" }
</li>

The HMM recognizes and parses sentences that use the above vocabulary. My program can perform the following:
<li> 
                    Pattern Recognition: Forward algorithm
                </li>
                <li>
                    State-Path Determination: Vertibi algorithm
                </li>
                <li>
                    Model Optimization: Baum-Welch algorithm
                </li>

The program implements the forward-backward algorithm, Vertibi algorithm and Baum-Welch algorithm. Formulas from the article by Rabiner were used to implement the algorithms. Program can be used with command-line arguments. Here are the instructions to compile and run the program:<br><br>

            1. Compile: "javac HMM_System.java"
            2. Run: "java HMM_System (function name) sentence.hmm (file name)"
            Function names: recognize, statepath, optimize
            File names: example1.obs, example2.obs, question1.obs

Why is the probability lower than we expect? 

First of all, the fact that probability of observing the output sequence is low means that it is very unlikely to observe the given observation output sequence considering the initial state possiblities, initial state transition probabilities, and initial state-output probabilities. This means that initial probabilities related to state and outputting O1 = students, O2 =  play, O3 =  games is very low. It could mean that the initial parameters are able to recognize only certain output sequence related with certain state sequence and state-output probabilities. This means that one hmm system can be thought of as working only for specific case of sentences.

What does this probability tell us? 

The probability tells us how likely the given observation sequence or sentence is likely to occur in the system. Therefore, we can think of it as the aptitude of the Hidden Markov Model and how well it fits the given observation. This implies that a model is usually not a general solution for all possible observation sequences. We can therefore choose one model among many models using this probability depending on which observation sequence we would like to predict.

Does the current HMM always give a reasonable answer?

No. The first and second sentences of Example 1 ("students play games" and "computers develop movies") are actual, valid sentences. But the output probability is only 2.7% and 2.88%, respectively, which are very low probability values considering that the sentences can be used in a proper English phrase. The means that the HMM is not particularly strong. The output for the third sentence ("students develop can games") has a probability of 0 which makes sense because the sentence itself holds no meaning.

The overall purpose of this program is to implement a simple natural language processor that is able to determine the validity of a string of English words. Although the program is able to efficiently parse the sentences, in the case of this particular implementation, it is limited to a short collection of words and probability values are lower than expected.
