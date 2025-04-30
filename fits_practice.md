### 📅 28 April 2025 - GSoC Learning Log Update

- Learned about FITS files structure (Header + Data).
- Installed and used `astropy.io.fits` to create and open FITS files.
- Created a sample random image FITS file manually.
- Opened, explored header and data.
- Visualized FITS image using `matplotlib.pyplot`.

## FITS File Creation and Visualization Practice

### ✅ FITS File Created Using Python

```python
# create_fits.py
from astropy.io import fits
import numpy as np

# Create a 100x100 array of random floats
data = np.random.rand(100, 100)

# Write the array to a FITS file
hdu = fits.PrimaryHDU(data)
hdu.writeto('vineela_generated.fits', overwrite=True)

print("✅ FITS file created successfully!")
from astropy.io import fits
import matplotlib.pyplot as plt

# Open the FITS file
hdul = fits.open('vineela_generated.fits')

# View header and structure
hdul.info()

# Extract image data
image_data = hdul[0].data

# Visualize image
plt.imshow(image_data, cmap='gray', origin='lower')
plt.colorbar()
plt.title('FITS Image Visualization')
plt.show()


