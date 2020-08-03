# VIA2COCO

This repository contains Python code to convert annotations from VIA to COCO format.

## Installation

- Install the latest version of [Python 3.X](https://www.python.org/downloads/).

## Usage

The simplest usage would be to specify a list of categories.

Caveat:
-   categories should have distinct names,
-   the order matters, as it will be used to number categories.

```python
import convert as via2coco

input_dir = '/content/data/balloon/train/'
input_json = input_dir + 'via_region_data.json'
categories = ['balloon']

coco_dict = via2coco.convert(
    imgdir=input_dir,
    annpath=input_json,
    categories=categories,
)
```

To save the output as a JSON file:

```python
import convert as via2coco

input_dir = '/content/data/balloon/train/'
input_json = input_dir + 'via_region_data.json'
categories = ['balloon']

output_json = input_dir + 'coco_train.json'

coco_dict = via2coco.convert(
    imgdir=input_dir,
    annpath=input_json,
    categories=categories,
    output_file_name=output_json,
)
```

It is also possible to specify a list of super-categories.

Caveat:
-   super-categories can have the same name,
-   the lists of categories and super-categories should have the same length,
-   the order matters, as it will be used to match categories and super-categories. 

```python
import convert as via2coco

input_dir = '/content/data/balloon/train/'
input_json = input_dir + 'via_region_data.json'
categories = ['balloon']

super_categories = ['N/A']

coco_dict = via2coco.convert(
    imgdir=input_dir,
    annpath=input_json,
    categories=categories,
    super_categories=super_categories,
)
```

to use it , you should install cv2,json first
and you should modify the category by yourself

## References

-   [pycococreator](https://github.com/waspinator/pycococreator/)
-   [VIA2COCO: the original repository](https://github.com/codingwolfman/VIA2COCO)
