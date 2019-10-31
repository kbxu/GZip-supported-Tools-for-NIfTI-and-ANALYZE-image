# GZip-supported-Tools-for-NIfTI-and-ANALYZE-image

* A modified MATLAB-based toolbox directly load/save *.nii.gz file without explicit compression/decompression.

* Raw version from [Jimmy Shen](https://www.mathworks.com/matlabcentral/fileexchange/8797-tools-for-nifti-and-analyze-image)


Supported Platforms
----------------
*  ![](https://img.shields.io/static/v1?label=Platform&message=Windows-x64&color=green)
*  ![](https://img.shields.io/static/v1?label=Platform&message=Windows-x32&color=green)
*  ![](https://img.shields.io/static/v1?label=Platform&message=Linux-x64&color=green)
*  ![](https://img.shields.io/static/v1?label=Platform&message=MacOS-x64&color=green)


Usage (same as raw ones)
------------------------
* add both folders to MATLAB's search path

* `load_nii/save_nii` &rarr; `load_nii_mod/save_nii_mod`

* `load_untouch_nii/save_untouch_nii` &rarr; `load_untouch_nii_mod/save_untouch_nii_mod`

Performance Test
------------------
* Code Snippet

```
tic;
test_img1 = load_nii('test_file.nii');
time1 = toc;
test_img2 = load_nii('test_file.nii.gz');
time2 = toc;
test_img3 = load_nii_mod('test_file.nii.gz');
time3 = toc;

assert(isequal(test_img1.img, test_img2.img))
assert(isequal(test_img1.img, test_img3.img))

fprintf('time of load_nii for *.nii file %.2fs\n', time1);
fprintf('time of load_nii for *.nii.gz file %.2fs\n', time2 - time1);
fprintf('time of load_nii_mod for *.nii.gz file %.2fs\n', time3 - time2);
```

* Output
```
time of load_nii for *.nii file 0.35s
time of load_nii for *.nii.gz file 6.19s
time of load_nii_mod for *.nii.gz file 1.56s
```
