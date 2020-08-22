# GSoC Final Report
##### Organization : International Neuroinformatics Coordinating Facility (INCF)
##### Project      : Automated comparison of scientific methods for time series analysis.

##### Student      : Salman Khan
##### Mentors      : Ben Fulcher, Oliver Cliff, Joseph Lizier

### Introduction
In this **Google Summer of Code 2020** project i had developed a web-based system that helps the user to compare timeseries analysis method.It takes time-series analysis method as python code from a user, computes it with a diverse time-series dataset and analyzes the relation of the newly developed method with 7700+ features and presents the best matching features as output which can help the user to conclude the similarity
between new method and pre-existing methods.

<img src="GIF-200822_154754.gif">
### What was done :
Since the project needs to be developed from scratch, i had breakdown the development in three parts:
<ol>
<li><strong>First phase</strong> - Backend / logic development</li><br>
<em>For execution of user's code properly and perform automated comparison i had written series of functions that help performs the several operations.</em><br>
<br>
<ul><li>Function that properly reads user's code as string and check for malicious code before execution. </li>
<li>Function that passes diverse time-series dataset through user's function and generate  long feature vector.</li>
<li>Function that takes newly generated feature vector, and find its spearman's correlation with each column of hctsa datamatrix and store all the information (Feature name, Keywords,p-value,Correlation) of best matches in sorted order.</li>
<li>Structured the results for rendering in dynamic table and for interactive plots.</li>
</ul>
<br>
<li><strong>Second phase</strong> - Front-end development</li>
<br><em>In this phase i had focused on front-end development , that will be used by the user which includes :</em><br>
<br>
<ul>
<li>Development of pages for websites that includes Home, How-it-works, Contact,  Preloader, Result, Syntax error, Timeout Error, 404 Not found. </li>
<li>Interactive Result table that includes with options to:<ul><li>Toggle to change representation of results.</li><li>Download all results in .csv format</li><li>Toggle button to view table in full size.</li><li>Choose show / hide column from table.</li></ul><img src="GIF-200822_154604.gif"></li>
<li>Visualization of top 12 results with Interactive scatter plots<ul><li>Hover to see data points.</li><li>Zoom each plot or all subplots simultaneously  to understand clearly the data points.</li></ul>
<img src="GIF-200822_154727.gif"></li> 

<li>Visualization of top 12 results with correlation heatmap with linkage clustering dendogram.</li>

</ul>
<br>
<li><strong>Third phase</strong> - Running user's code securely and Error handlings.<br><br>
<em>This was one of the major challenge as executing user code on server could compromise the system. So to run user's code safely:</em><br><br>
<ul><li>We are using RestrictedPython to run user's code in a restricted environment.</li><li>Allows to import only those modules that are computation specific and does not tries to access/modify system</li>
<li>Restricted in-built functions like exec, eval that can harm our system.</li>
<li>Timeout limit added to user's function so that if it falls into infinite loop and exceeds limit we can kill the process and render timeout error. </li>

<li>Other than that handled all possible errors like Syntax error, 404 page not found, Timeout error
</li>
<br>
</ul>

<h2> Link to work </h2>
<ul>
<li><a href="https://github.com/NeuralSystemsAndSignals/Comp-Engine-Features"> Link to full repository</a></li>
<li><a href="https://github.com/NeuralSystemsAndSignals/Comp-Engine-Features/commits/master">Link for all commits</a></li>
</ul>

<br>

<h2> Weekly Reports</h2>
These are the weekly reports that i had submitted to INCF during GSoC period :<br>

<a href="https://drive.google.com/file/d/1DKX11fXbYbpREzT8H0AB5Vdq8xSzLO8u/view?usp=sharing">Week 1 & Week 2</a><br>
<a href="https://drive.google.com/file/d/12lr42BS4PyOyBUC1cqbAaYDeUksdllxe/view?usp=sharing">Week 3</a><br>
<a href="https://drive.google.com/file/d/1tuV2kLixLSpDSst-rc-eXj4rhZbz_qRD/view?usp=sharing">Week 4</a><br>
<a href="https://drive.google.com/file/d/1GFv2RhH4dg96NdV-CrnO9bd1RFiPVMU-/view?usp=sharing">Week 5</a><br>
<a href="https://drive.google.com/file/d/18O2VJ8uYRXfamjCmKa0Cq0Z6MYyw5nMU/view?usp=sharing">Week 6</a><br>
<a href="https://drive.google.com/file/d/1ket_4KNNlxDDR6v5ec2s3zPjcN3RSA8B/view?usp=sharing">Week 7</a><br>
<a href="https://drive.google.com/file/d/179jS-Ztb675IzxVpvI9Y-fvxnvsq-oRC/view?usp=sharing">Week 8</a><br>
<a href="https://drive.google.com/file/d/1uTio6VrW_wJp66dp83JSSduzNPK8g6T0/view?usp=sharing">Week 9</a><br>
<a href="https://drive.google.com/file/d/1PAvLqlv8p7_tm2dWcwDtFrH4Fp-rOYxd/view?usp=sharing">Week 10</a><br>
<a href="https://drive.google.com/file/d/1PumTCAHoR7FEz21GVpolGOb6o0J14Khd/view?usp=sharing">Week 11</a><br>
<a href="https://drive.google.com/file/d/10CzCYMVjRRHOa4Khtgkno3oRTgbn06p7/view?usp=sharing">Week 12</a><br>


<br>
<br>
<h2> Future Work</h2>
Since the minimal requirements of this project as outlined in GSoC proposal is completed but there are lot more things that could be implemented and can enhance the system. After GSoC period i am planning to:
<ul><li>Add explore mode by which user can compare already exisiting features.</li>
<li>Add a nested result table clicking on any result will take to other result table of similar features</li><li>Other ways of visualization like Network Visualization.</li></ul>
