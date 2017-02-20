# Grocery Dataset

This repository contains annotation files and links for downloading images for the Grocery Dataset.

The Grocery Dataset is an image dataset:
* Collected from ~40 groceries, with 4 cameras,
* With 10 product categories,
* Created Spring 2014 - Idea Teknoloji, Istanbul, Turkey.

The dataset is available for research only, not for commercial use.

## Download links
Here are [part1](https://github.com/gulvarol/grocerydataset/releases/download/1.0/GroceryDataset_part1.tar.gz) and [part2](https://github.com/gulvarol/grocerydataset/releases/download/1.0/GroceryDataset_part2.tar.gz) for downloading the image files. The total disk space is around 3GB. You can equally find these links under the releases of this repository. 

## Organization of the folders

### ShelfImages
This folder contains 354 grocery images.

The naming is as follows:
```
			"C<c>_P<p>_N<n>_S<s>_<i>.JPG"
			where
				<c> := camera id (1: iPhone5S, 2: iPhone4, 3: Sony Cybershot, 4: Nikon Coolpix)
				<p> := planogram id
				<n> := the rank of the top shelf on the image according to the planogram
				<s> := number of shelves on the image
				<i> := copy number
```
	
### ProductImages
This folder contains images from 10 different product categories numbered from 1-10. Each category has a separate directory.

The naming is as follows:
```
		"B<b>_N<N>.JPG"
			where
				<b> := brand id
				<n> := copy number
```

		
### BrandImages

This folder contains the cropped versions of the ProductImages directory. The images are cropped so that only the brand logo remains.


### ProductImagesFromShelves

This folder contains product images cropped from shelf images. They are divided into 10 product categories plus one negative category where the products not belonging to any of the 10 classes are gathered.

The naming is as follows:
```
			"<shelf image name>_<x>_<y>_<w>_<h>.png"
			where
			<shelf image name>   := the source image where the image is cropped from
			<x>                  := x-coordinate of the image's top-left corner on the source image
			<y>                  := y-coordinate of the image's top-left corner on the source image
			<w>                  := width of the image on the source image
			<h>                  := height of the image on the source image
```

### BrandImagesFromShelves
This folder contains the cropped versions of the ProductImagesFromShelves directory. The images are cropped so that only the brand logo remains.

*******************************
## Annotation files

### annotation.txt
This file summarizes the annotation information of the shelf images into one text file. Each row explains one shelf image.

The format of one line is as follows:

```
			<shelf image name> <n> <x_1> <y_1> <w_1> <h_1> <b_1> <x_2> <y_2> <w_2> <h_2> <b_2> ... <x_n> <y_n> <w_n> <h_n> <b_n>
			where
			<shelf image name>   := shelf image name
			<n>                  := number of product on the shelf image
			<x_i>                := x-coordinate of the i'th product image
			<y_i>                := y-coordinate of the i'th product image
			<w_i>                := width of the i'th product image
			<h_i>                := height of the i'th product image
			<b_i>                := brand of the i'th product image
```

### subset.txt
This file lists the names of the image files used for training and testing. It is a subset of the BrandImages and BrandImagesFromShelves contents.

## Citation
If you use this dataset, please cite the following:
> @article{varol16a,  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TITLE = {{Toward Retail Product Recognition on Grocery Shelves}},  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AUTHOR = {Varol, G{\"u}l and Kuzu, Ridvan S.},  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;JOURNAL =  {ICIVC},  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;YEAR = {2014}  
}

## Acknowledgements
The dataset is collected as part of a TUBITAK funded project carried out by Idea Teknoloji.
