# MALDISkyLink
Interface between Bruker raw files and Skyline.

Once a dataset is acquired:
1. Run MALDISkylink (converts a Bruker file into mzxml file via msconvert, then adds the required blank scans and duplicated data scans {C# GUI}).
2. Run Skyline Batch or Skyline on all the files in the folder:

   a. Import each mzml
   
   b. Refine for idotp >0.9 (therefore include the M-1 for every glycan composition in the Skyline document)
   
   c. New Skyline document should then be made with all the matching compositions quantified
   
   d. Run an R script, making an excel spreadsheet with relative intensities for the monoisotopic peak quant AND full isotopic envelope quant
   
3. Upload your Skyline document to 

Requires Proteowizard and Skyline to be installed. MSConvert should also be added to the path on Windows 10 (https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/).
