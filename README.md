TIFF to MRC Conversion Script

This Python script converts .tif or .tiff image files (such as those used in electron microscopy) to the MRC format. 
The script processes individual files or batches of TIFF files in a directory.

Features
•	Converts both .tif and .tiff files to .mrc.
•	Supports batch processing using wildcard patterns (e.g., *.tif or *.tiff).
•	Confirms the number of files to be converted before proceeding.
•	Automatically checks if required Python modules are installed and provides instructions if they're missing.

Requirements
Ensure you have the following Python modules installed:
•	tifffile
•	mrcfile
•	numpy

If not run:
pip install tifffile mrcfile numpy

How to use convert_tiff2mrc.py tool:

1. Clone the repository:
  git clone https://github.com/yourusername/convert_tiff2mrc.git
  cd convert_tiff2mrc

2. Make the script executable using:
   chmod +x convert_tiff2mrc.py

4. Place the script convert_tiff2mrc.py in the directory where the .tif or .tiff files are located or vice-vera.


5. Run the script:
  python convert_tiff2mrc.py

---- Extra ----
Customizing the Directory or File Patterns:
By default, the script processes all .tif and .tiff files in the current directory. You can modify the script to point to a different directory or use custom wildcard patterns.
For example, to convert .tif files in a different directory:
  batch_convert_tiff_to_mrc("/path/to/your/directory/*.tif")


Contributing
Feel free to submit pull requests or open issues if you find bugs or have suggestions for improvements!

License
This project is licensed under the MIT License - see the LICENSE file for details.
