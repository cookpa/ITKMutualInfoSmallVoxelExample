Example code and data from here:

https://examples.itk.org/src/registration/common/mutualinformation/documentation

Make small voxel data
---------------------

First convert example data to NIFTI:

c2d fixed.png -o fixed.nii
c2d moving.png -o moving.nii


Then edit pixels in R:

library(RNifti)
fixed = readNifti('fixed.nii')
pixdim(fixed) = c(0.001, 0.001)
writeNifti(fixed, 'fixedMicron.nii.gz')

moving = readNifti('moving.nii')
pixdim(moving) = c(0.001, 0.001)
writeNifti(moving, 'movingMicron.nii.gz')
