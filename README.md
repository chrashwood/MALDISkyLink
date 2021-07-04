# MALDI-Skyline-conduit
Interface between Bruker raw files and Skyline
Once a dataset is acquired:
1. Run MALDI-link (converts all Bruker files into mzxml files via msconvert, then adds the required blank scans and duplicated data scans (python script or C# GUI)).
2. Run Skyline Batch on all the files in the folder
   a. Imports each mzml
   b. Refines for idotp >0.9 (therefore include the M-1 for every glycan composition in the Skyline document)
   c. New Skyline document is made with all the matching compositions quantified
   d. R script is run, making an excel spreadsheet with relative intensities for the monoisotopic peak quant AND full isotopic envelope quant
3. Skyline document is uploaded to Panorama.

Requires Proteowizard and Skyline to be installed

Process
1. msconvert.exe on the raw file in the prompt, convert to .mzxml
2. Read mzxml
3. Save the entire <scan 1 to </scan>
3. Change     <scan num="1"
to <scan num="2"
4. Write the blank scan to scan #1, just after </dataProcessing>
4. Change the scan num and retention time for each 
Scan 1 (blank) = 60 secs
Scan 2 (MALDI) = 61 secs
Scan 3 (MALDI) = 120 secs
Scan 4 (blank) = 121 secs
Scan 5 (blank) = 122 secs
5. Import mzxml into Skyline
