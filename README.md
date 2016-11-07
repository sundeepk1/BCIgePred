# BCIgEPred
Linear B-Cell IgE Predictor

1. Introduction
   =============
   BCIgePred (Linear B cell IgE Epitope Predictor) is a perl based open source tool for the prediction of Linear B-cell IgE epitopes.

2. Installation
   ============
   Linux OS
   (a) Download BCIgePred from github.
   (b) Extract the files to the desired location.
   (c) Provide executable permission to LIgE, IgEPred, and LBEEP files (if it doesn't have executable rights).
   (d) Provide read and write permission to "temp" folder (if it doesn't have read and write permission).
   (e) make sure java 1.6 or higher is installed in your system.
   (f) make sure PERL 5.0 or higher version is installed in your system.
   
   Windows and other operating system
   (a) The source code has been writtern in PERL and hence it can be executed as perl script in other operating system. Note: The program is not tested in any other operating system (except Linux based OS) and hence not advised to execute in other OS.

3. Command line options
   ====================
   
   -i : input file in fasta format (mandatory). 
        Note: The option does not validate the FASTA format and hence make sure the input sequence is in fasta format.
   -m : mode either 'pep' for peptide or 'pro' for protein  (mandatory).
   -M : Model to be used 'RF' for Random Forest, 'SVM' for support vector machine model (default RF model).
	 -t : threshold for predcition of IgE; integer ranging between 0.0 and 1.0 (default 0.5).
   -BT : threshold for predcition of B-cell epitope (firt layer prediction); integer ranging between 0.0 and 1.0 (default 0.5).
   -o : output file (if not mentioned output will be stored in LBEEP_out file).

4. Output Interpretation          
   =====================
   
   (a) A CSV (comma seperated values) file will be generated as output for both peptide and protein mode, which contans peptideheader|input peptide|, and probability score for the peptide mode and Position of peptide in protein, |peptide|, and probability score for protein mode.
   (b) The peptides having score greater than threshold mentioned in -t is considered IgE epitopes.
   (c) Two output files will be generated, the one with the suffix "_out_Bcell" (contains results produced by LBEEP, Linear B cell epitope prediction first layer)  and the one with the suffix "_out_IgE" (contains results produced by IgEPred, Linear IgE epitope prediction second layer).
   
5. Limitations
   ============
   
   (a) Since the models are trained using epitopes and non-epitopes of length >5 and <=15, predictions made for peptides other than these lengths will be undesirable. Hence, it is advised not to mention window size less than 6 and greater than 15 in protein mode, and not advised to input peptides of length less than 6 and greater than 15 in peptide mode. 

6. Example
   =======
   (a) ./LIgE -i test_input_peptides -m 'pep' -M 'RF' -o Test_peptide -t 0.5 -BT 0.5 
   (b) ./LIgE -i test_input_protein -m pro -M 'RF' -t 0.5 -BT 0.7 -o Test_protein
   (c) ./LIgE -i test_input_peptides -m pep -M 'SVM' -o Test_peptide_svm
 	
7. License
   =======
   BCIgEpred V1.0 is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation version 3.0 of the License.
   This software is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License contained in the file LICENSE for more details.

