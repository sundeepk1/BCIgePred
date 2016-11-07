# BCIgePred
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
