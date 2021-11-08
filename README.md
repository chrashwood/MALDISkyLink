# MALDISkyLink
Interface between Bruker raw files and Skyline
Once a dataset is acquired:
1. Run MALDISkylink (converts a Bruker file into mzxml file via msconvert, then adds the required blank scans and duplicated data scans {C# GUI}).
2. Run Skyline Batch or Skyline on all the files in the folder
   a. Imports each mzml
   b. Refines for idotp >0.9 (therefore include the M-1 for every glycan composition in the Skyline document)
   c. New Skyline document is made with all the matching compositions quantified
   d. R script is run, making an excel spreadsheet with relative intensities for the monoisotopic peak quant AND full isotopic envelope quant
3. Skyline document is uploaded to Panorama.

Requires Proteowizard and Skyline to be installed. MSConvert should also be added to the path (https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/).
