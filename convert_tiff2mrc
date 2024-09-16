print("                                                      ")
print("  ___    _    _     ___  _  _       _       _    ___  ")
print(" / __|  /_\  | |   | __|| || | ___ | |     /_\  | _ ) ")
print(" \__ \ / _ \ | |__ | _| | __ ||___|| |__  / _ \ | _ \ ")
print(" |___//_/ \_\|____||___||_||_|     |____|/_/ \_\|___/ ")
print("                                                      ")
print("             TIFF to MRC convertion tool              ")
print("                   Saleh-Lab 2024                     ")
print("                convert_tiff2mrc.py                   ")
print("                                                      ")
print("                                                      ")
print(" Credit: tif2mrc by Jim Kremer and David Mastronarde  ")
print("If you incur issues run: pip install tifffile mrcfile numpy")
                                                    

import sys
import os
import glob

# Check if required modules are installed
try:
    import tifffile
    import mrcfile
    import numpy as np
except ImportError as e:
    print(f"Error: {e}. Please install the required modules by running:")
    print("pip install tifffile mrcfile numpy")
    sys.exit(1)

def convert_tiff_to_mrc(tiff_file, mrc_file):
    """Converts a single TIFF/TIF file to MRC format."""
    print(f"Processing {tiff_file}...")
    
    # Read the TIFF file
    with tifffile.TiffFile(tiff_file) as tif:
        images = tif.asarray()

    # Ensure it's in the correct format (MRC expects a 3D array for image stacks)
    if images.ndim == 2:
        images = images[np.newaxis, :, :]  # Add a Z dimension if it's a single image

    # Write the MRC file
    with mrcfile.new(mrc_file, overwrite=True) as mrc:
        mrc.set_data(images.astype(np.float32))  # Convert to float32 if needed
        mrc.update_header_from_data()

    print(f"Converted {tiff_file} to {mrc_file}")

def batch_convert_tiff_to_mrc(tiff_pattern):
    """Processes multiple TIFF/TIF files in a directory using a wildcard pattern."""
    tiff_files = glob.glob(tiff_pattern)

    if not tiff_files:
        print(f"No files found matching pattern: {tiff_pattern}")
        return

    # Count the number of TIFF files found
    num_files = len(tiff_files)
    print(f"Found {num_files} micrographs matching pattern '{tiff_pattern}'.")

    # Ask for confirmation before proceeding
    confirm = input(f"Do you want to proceed with converting these {num_files} files to MRC? (y/n): ")
    if confirm.lower() != 'y':
        print("Conversion aborted.")
        return

    # Process each TIFF file and convert it to MRC
    for tiff_file in tiff_files:
        # Generate output MRC file name by replacing .tif/.tiff with .mrc
        base_name = os.path.splitext(tiff_file)[0]
        mrc_file = base_name + ".mrc"
        convert_tiff_to_mrc(tiff_file, mrc_file)

if __name__ == "__main__":
    # Process all .tif and .tiff files in the current directory
    batch_convert_tiff_to_mrc("*.tif")  # For .tif files
    batch_convert_tiff_to_mrc("*.tiff")  # For .tiff files

