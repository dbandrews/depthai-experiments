## Host-Side WLS Filtering

### Background

This gives an example of doing host-side WLS filtering using the `rectified_right` and `depth` stream from DepthAI.  

Example running on [BW1092](https://shop.luxonis.com/collections/all/products/bw1092-pre-order) shown below:
![image](https://user-images.githubusercontent.com/32992551/94463964-fc920d00-017a-11eb-9e99-8a023cdc8a72.png)

Example of running on OAK-D:


### How to Run

Run
```
conda env create --name wls_filter_demo python=3.7
conda activate wls_filter_demo
./install_dependencies.sh
./main.py
```

### Troubleshooting:

If you see the following when running `main.py`:
```
Traceback (most recent call last):
  File "/Users/leeroy/depthai-experiments/wls-filter/./main.py", line 52, in <module>
    wls_filter = cv2.ximgproc.createDisparityWLSFilterGeneric(lr_check)
AttributeError: module 'cv2.cv2' has no attribute 'ximgproc'
```

This means that `opencv-contrib-python` is missing on your machine.  Please install it using `python3 -m pip install opencv-contrib-python` and then re-run `./main.py`:

![image](https://user-images.githubusercontent.com/32992551/104220890-628a6380-53fd-11eb-9098-ffefc3dd3aa6.png)


