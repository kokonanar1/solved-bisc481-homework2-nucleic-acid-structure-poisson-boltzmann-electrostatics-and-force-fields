Download Link: https://assignmentchef.com/product/solved-bisc481-homework2-nucleic-acid-structure-poisson-boltzmann-electrostatics-and-force-fields
<br>
<strong> </strong>Question 1: General knowledge

<ol>

 <li>Name (i) the two main physical interactions that stabilize the DNA double helix and (ii) explain the physical basis for each of those interactions. 4pts</li>

 <li>List and <u>briefly explain</u> the definition of (i) three intra-base pair helical parameters of your choice, (ii) three inter-base pair parameters of your choice, and (iii) three other structural parameters that are used to describe nucleic acid structure. 6pts</li>

 <li>Briefly explain the basis for (a) base readout and (b) shape readout of</li>

</ol>

DNA sequence through DNA binding proteins 4pts

<h1>Question 2: DNA Structure</h1>

This question will use the two PDB files provided with this assignment, red.pdb and blue.pdb. One of these contains the structure of an A-DNA helix, and the other of a B-DNA helix. Let’s determine which is which.

<ol>

 <li>Using PyMol, open both structures within the same session. Play around with the various visualization options to get familiar with them. Now, use the align command (<a href="https://pymolwiki.org/index.php/Align">https://pymolwiki.org/index.php/Align</a><a href="https://pymolwiki.org/index.php/Align">)</a> to superimpose these two structures, then use the translate command <a href="https://pymolwiki.org/index.php/Translate">(</a><a href="https://pymolwiki.org/index.php/Translate">https://pymolwiki.org/index.php/Translate</a><a href="https://pymolwiki.org/index.php/Translate">)</a> to shift one of them so that they are in the same orientation, but not overlapping. Produce a visualization similar to the one below (but using a different color scheme than I did) and include it in your report. Describe some of the differences you observe between these two structures (aside from the different number of nucleotides). 4pts</li>

</ol>

Figure 1 – produce a visualization similar to this

<ol>

 <li>Let’s take a look at the DNA shape parameters and quantify the differences between the structures.</li>

</ol>

We will use the 3DNA web server to calculate some DNA shape parameters for the two helices. Visit <a href="http://web.x3dna.org/">http://web.x3dna.org/</a> and upload the red.pdb and blue.pdb files individually. You’ll be shown a page with some visualizations and a lot of information. Scroll down to the following section:

Download the parameter summary file for both structures. Within that file, find the table labeled as “Local base-pair helical parameters”. Take the data in that table and plot two of the shape parameters for both of the helices:

<ul>

 <li>Plot x-displacement vs inclination as a scatter plot for both structures (plot everything on the same graph)</li>

 <li>Color the pdb points red, and blue.pdb points blue</li>

 <li>Label the horizontal and vertical axis appropriately</li>

 <li>Include, for each set of points, the <strong>median</strong> point, and plot it as a large, distinct point which is easily identified, and label it</li>

</ul>

Include this plot in your report. 10pts

<ol start="2">

 <li>Based on the two visualizations you’ve produced in part <strong>A</strong> and <strong>2.B</strong>, which helix is A-DNA and which is B-DNA? Justify your response. 2pts</li>

 <li>*BONUS* Using the protein data bank or another web site, find an example of a Z-DNA helix. Reproduce the same plot as you made in part <strong>B</strong>, but this time add the shape parameters of the Z-DNA helix colored in green. Also include a visualization of this helix using PyMol in your report. 4pts</li>

</ol>

<h1>Question 3: Poisson-Boltzmann Electrostatics</h1>

We will use the PyMol plugin known as “APBS Electrostatics” to perform a Poisson-Boltzmann calculation on a protein structure. This will allow us to visualize the electrostatic potential of that protein. I have provided you with the structure of a homeodomain (a protein domain that binds DNA) for this purpose.

<ol>

 <li>Open the file pdb (provided) in PyMol. We are going to perform 3 separate Poisson-Boltzmann calculations on this protein structure using different settings. Please do these separately (in different PyMol sessions) in order to avoid making mistakes. <strong>For all three runs, you must include visualizations of the resulting electrostatic potential surface in your report.</strong></li>

 <li>With PyMol open, at the top of the screen you will see a “Plugin” menu. Open this and select “APBS Electrostatics” and a new window will open.</li>

</ol>

Figure 3 – the APBS Electrostatics plugin window

For the first run, we will leave everything as default. Click “Run”. You will get a warning stating “pdb2pqr emitted warnings, do you want to continue?” click “yes”. A surface will be added to your PyMol session that is colored from red to blue. This surface represents the solvent excluded surface of the protein with the value of the electrostatic potential at the surface represented by the color (blue is positive, red is negative).

<ol start="2">

 <li>Perform a second calculation, but this time go to “APBS Template” at the top of the ABPS Electrostatics pop-up window. Here we can adjust the parameters used in the calculation. Near the bottom, you will see the following two lines:</li>

</ol>

ion charge +1 conc 0.15 radius 2.0 ion charge -1 conc 0.15 radius 1.8

These lines specify the charge, concentration and ionic radius of two salts that are, by default, included in our calculation. Change the value of “conc” from 0.15 to 0.0 in both lines – this effectively removes any ionic charge from the calculation. Perform a second calculation as before.

<ol start="3">

 <li>Perform a third calculation, but this time set the salt concentrations to</li>

</ol>

0.45, and change “lpbe” to “npbe” (don’t worry about what this means). This triples the salt concentration relative to the first calculation.

Now, include visualizations for all three runs in your report. Include two different camera angles for each run and try to make the angles consistent with each other between runs. Be sure to label each run correctly! 10pts

<ol>

 <li>Based on your observations, how does changing the salt concentration affect the electrostatic potential? How might this be relevant to proteinDNA binding? Do you expect protein-DNA binding to be stronger under high or low salt concentrations? 5pts</li>

 <li>Based on the electrostatic potential you have observed in run #1 (under near-physiological conditions), and the known chemical and electrostatic properties of DNA, identify the region of this protein domain that is most likely to bind DNA. You can simply circle a region from the visualizations you produced in run #1 (add them as new figures in response to this question). 5pts</li>

</ol>

<h1>Question 4: Force Field Energy Minimization using Python</h1>

In this question we will be using python and a very very (very) simple force-field to find the conformation of a molecule structure which minimizes a potential energy function.

I have provided you two python scripts, energy_minimization.py and Atoms.py. You will be editing the first, but do not edit or modify the second in any way. You don’t even need to look at it. If you have never used python before, please spend some time reviewing the following tutorial (or one of the hundreds of others): <a href="https://www.programiz.com/python-programming/tutorial">https://www.programiz.com/python</a><a href="https://www.programiz.com/python-programming/tutorial">–</a><a href="https://www.programiz.com/python-programming/tutorial">programming/tutorial</a>

Before proceeding, please install the packages “numpy” and “scipy” if they are not already installed:

conda install numpy conda install scipy

<ol>

 <li>Open the script py in a text editor. I recommend the program “geany” (google it), you don’t need something fancy.</li>

</ol>

Now, have a look over the code and try to grasp a little of what it is doing.

Your task is simply to fill in a few lines of code to produce some output and then have a look at the results. The comments in the code will walk you through what you need to do, beginning at STEP 1.

You need to:

<ul>

 <li>Calculate the total potential energy of the initial configuration of the atoms (using provided functions) and include this value in your report. 4pts</li>

 <li>Calculate the total potential energy of the final configuration, after energy minimization, and include this value in your report. 3pts Visualize the initial and final conformations of the molecule (represented by the “atoms” object) using PyMol and include these in your report. 3pts</li>

</ul>

<ol>

 <li>**BONUS** You may have guessed by now that this molecule is benzene. However, an inspection of the final conformation will reveal that the carbon ring is not planar. This is because we have failed to include torsion angles in our force field! Experiment with some torsion potential energy functions and come up with an extra term in the force field which, when added to the total energy, will produce a planar molecule based on computed torsion angles. Include a visualization of your final minimized molecule AND the code for your torsion potential in your report. 8pts</li>

</ol>








