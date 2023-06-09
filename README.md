Download Link: https://assignmentchef.com/product/solved-mdl-genetic-algorithms-assignment-2
<br>



1 Genetic Algorithm

Genetic algorithm is often used in parameter selection and obtaining optimal solutions. You have been given coefficients of features(a vector of size 11) corresponding to an overfit model and your task is to apply genetic algorithm in order to reduce the overfitting i.e. generalize the model so that the model performs better on unseen data. To help you with the formulation of your fitness function, you will be allowed to query and check how your coefficients perform on the training and the validation set.

The output(of your vector) will be calculated using:

1 0

f(x) = ~ wi * xi

i=0

where xi represents the features, and wi represents the coefficients submitted by you. MSE, which will be returned for the validation and the train data, will be calculated using:

MSE = ~ ((y—f(x))<sup>2</sup>)/N

x∈data

For the sake of simplicity, the weights you submit should satisfy:

wi &lt; 10

wi ≥ —10

2 Server Details

You will be provided with a file <a href="http://client.py">client.py</a>. It has one function named get errors that you can use to query the server. Import this client into the GA code you write and call the function by supplying your team key and weight vector. The team key will be sent directly through an email. Please note that there is a daily limit of 200 requests to the server which means total functions calls allowed are 200. This limit might change in the due course of project. To check your daily usage, visit <a href="http://10.4.21.156/getusage">http://10.4.21.156/getusage</a>

2.1 Available Functions

<ul>

 <li>get errorsparams:</li>

</ul>

– ID =&gt; String: The secret team ID

– Vector =&gt; Python List: The 11D weight vector

returns: 2 element python array of the form [train error, validation error]




2.2 Workflow

A typical workflow will be as follows:

<ul>

 <li>Start by reading the overfit array from the text file provided with the assignment itself.</li>

 <li>Use the get errors function to guide the learning in Genetic Algorithm.</li>

 <li>Submit the final 10 weight vectors with your submission(in descending order of your preference as described below).</li>

</ul>

2.3 Essential Notes

<ul>

 <li>Please be mindful of the daily usage limit.</li>

 <li>Please do not share your secret ID with anyone. If someone exhausts your daily quota, there is nothing we can do.</li>

 <li>The secret ID will be sent through an email.</li>

</ul>

3 Format of Report

<ul>

 <li>Summary of your Genetic Algorithm with all the steps, also mention if you have made any major changes to the base genetic algorithm.</li>

 <li>Three diagrams that showcase three iterations of your algorithm. Refer Fig. 1 that illustrates one iteration of a genetic algorithm. You can choose a population of size minimum 7 to draw the diagram and then proceed with the iterations. The initial population(corresponding to the 1st diagram) need not be your very first population you used and can be intermediate, but the diagrams should be for 3 successive/consecutive iterations. The vectors cannot be random and should be the ones generated by your algorithm.</li>

 <li>Explain your fitness function.</li>

 <li>Explain your crossover function.</li>

 <li>How exactly did you apply the mutations(if any).</li>

 <li>What were your hyperparameters like pool size, splitting point for creating new genes, etc and why did you choose those parameters?</li>

 <li>Statistical information like number of iterations to converge, etc.</li>

 <li>What heuristics did you apply, mention the ones that didn’t work too.</li>

 <li>Mention the train error and validation error that you were able to achieve. Explain why this performs well on an unseen data with theoretically sound points. Avoid vague arguments.</li>

 <li>Anything else that you used, tricks, brute force, etc. that we should be aware of.</li>

</ul>

4 Deliverables

Submit a zip file named &lt;TeamNumber&gt;.zip which on unzipping returns a folder named &lt;TeamNumber&gt; that contains the following files,

<ul>

 <li>A report named pdf that follows the format as mentioned in Section 3.</li>

</ul>




Figure 1: Sample Iteration of Genetic Algorithm

<ul>

 <li>A python file named <a href="http://main.py">py</a> that contains the source code of your Genetic Algorithm. The code, on executing should generate a file named output.txt which contains ten vectors of size 11. The MSE will be computed using these ten vectors on an unseen test dataset which decides your leaderboard position. The lesser the average MSE is, the higher your position is in the leaderboard.</li>

 <li>A text file named txt which contains ten 11-D vectors in the following format,</li>

</ul>

– The vectors should be arranged in the order you want us to consider the vectors. This means the first vector is the first best vector and the tenth vector is the least best vector according to you.

– Each vector should be a list of 11 floats

– Append all the vectors into a single list of lists called answer – Each element in answer is a list of floats

– The answer list would look like,

– Use json.dump to put the answer array into a file called output.txt. Code should be like,

<table>

 <tbody>

  <tr>

   <td width="562">with open ( ‘ output . txt ‘ , ‘w’ ) as write file: json .dump( answer , write file)</td>

  </tr>

 </tbody>

</table>




– Make sure you are able to use json.load to construct back the original array from output file. Since we have automated evaluations, failure to be able to reconstruct the original array from output.txt file would lead to zero points in the leaderboard.

<ul>

 <li>A folder named generations which contains ten files namely generations 1.txt, generations 2.txt, generations 3.txt, generations 4.txt, generations 5.txt, generations 6.txt, generations 7.txt, genera­tions 8.txt, generations 9.txt, generations 10.txt. Each of these files should contain the intermediate population after selection(if any), crossover(if any) and mutation(if any) for every generation for that particular vector. For ex: generations 1.txt should contain all the intermediate population(please label them) for every generation corresponding to the first 11-D vector.</li>

</ul>

The directory structure on unzipping &lt;TeamNumber&gt;.zip should look like,

<ul>

 <li>&lt;TeamNumber&gt;</li>

</ul>

– Report.pdf

– <a href="http://main.py">main.py</a>

– output.txt

– generations

∗ generations 1.txt ∗ generations 2.txt ∗ generations 3.txt ∗ generations 4.txt ∗ generations 5.txt ∗ generations 6.txt ∗ generations 7.txt ∗ generations 8.txt ∗ generations 9.txt ∗ generations 10.txt

5 Evaluation Criteria

<ul>

 <li>Marks Distribution</li>

</ul>

<ol>

 <li>Intermediate Evaluation (March 5th): 10%</li>

 <li>Basic Code, Report and Viva: 40%</li>

 <li>Relative preformance on the test set(on the basis of rank among all the teams): 50%</li>

 <li>Your weights will be tested on a completely unseen dataset, lower the MSE, higher your position on the leaderboard.</li>

</ol>

<ul>

 <li>All coding questions have to be done in Python3 only.</li>

 <li>You are expected to write vectorized code.</li>

 <li>Plagiarism will be penalized heavily.</li>

 <li>No deadline extensions.</li>

</ul>

Manual evaluations will be held regarding which further details will be announced lat