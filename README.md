# Introduction
This is the Thangka dataset for image annotation, classification, vectorization and other tasks that listed in paper 
"Ma Y, Liu Y, Xie Q, et al. A Tibetan Thangka Dataset and Relative Tasks[J]. Image and vision computing." .
Any research work on this data set should place proper citation of this paper.


# How to read the json files?
The labeling work is finished using the tool LabelMe[1]. Because the output file format of “LabelMe” is “json”, the 
image and the label information can be directly read from the tool "LabelMe". 

The image and the label information can also be read by the python code, with "import labelme.utils", following is a example:
```python
import argparse
import json
import matplotlib.pyplot as plt
from labelme import utils

json_file = "YourPathOfJsonFiles\1005.json"
data = json.load(open(json_file))
img = utils.img_b64_to_arr(data['imageData']) # Analyze the original image data
lbl, lbl_names = utils.labelme_shapes_to_label(img.shape, data['shapes']) # read label information
print(lbl_names.keys())
print(len(data['shapes']))
plt.imshow(img)
plt.show()

```

# Files in the project
There are 2 directories, "jsons" and "jsons_2".   
jsons---contains 0-999 files  
jsons_2---contains 1000-1777 files  
Train_list.txt---the list of the image names for training in the annotation task  
Test_list.txt---the list of the image names for testing in the annotation task  

# References
[1] B. C. Russell, A. Torralba, K. P. Murphy, W. T. Freeman, Labelme: A database and web-based 
tool for image annotation, International journal of computer vision 77 (1-3) (2008) 157–173.
doi:https://doi.org/10.1007/s11263-007-0090-8.
