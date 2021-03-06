# Mesh Slicer
### Journal of Neuroscience Methods 2018 [[Paper]](https://arxiv.org/abs/1712.09684) [[Project Page]](https://www.ics.uci.edu/~agarwal/mouseBrain/index.html)
![](./misc/interface.png)

A simple user interface with which one can slice any mesh (with single or multiple components) in arbitarary directions and get either a rasterized image of the resultant contour or a mesh file (PLY) containing the vertices and edges of the contour.  

## Getting Started

The below instructions will help you install the mesh slicer on your local linux machine and give details on the user interface.

### Prerequisites

On Ubuntu/Debian, make sure you have installed the following packages

```
sudo apt-get install cmake xorg-dev libglu1-mesa-dev python-dev libglew-dev
```

Also install [libigl](https://github.com/libigl/libigl) and make sure its in your path. Its a header only library used to import/export mesh files


### Compiling

Clone the repository and all the dependencies
    
```
git clone --recursive-submodules https://github.com/nitinagarwal/mesh_slicer.git
mkdir build
cd build
cmake ..
make
```

After successful installation, you can import any meshfile with [OFF](http://segeval.cs.princeton.edu/public/off_format.html) format. For example:

```
./mesh_slicer ../mouseBrain.off ./output_directory
```

where:
* the first argument is the mesh file
* the second argument is the output directory for contour mesh or image file(s).

## User Interface

1. The orientation of the cutting plane is given by its normal vector in x, y and z coordinates.
2. The position of the cutting plane is given by the position of its center in x, y, z coordinates.
3. The user can specify either the number of slices they want or the inter-slice distance (same units as the input mesh).
4. To assist the user in visualizing what output files would be generated, they can slice the mesh in the UI to see
an example section. After which they can reload the mesh to slice at a different orientation. 
5. The output after slicing could either be a [.PLY](http://paulbourke.net/dataformats/ply/) file with vertices of the contour or rasterized section images in bmp format.
6. If the vertices of the input mesh do not have color, by default they will be assinged an RGB color of [255,0,255]

To know more about mesh slicer press `H` inside the UI.

## Citation
If you use the code/data, please cite the following paper:

```
@article{agarwal2017mouse,
  author = {Nitin Agarwal, Xiangmin Xu, Gopi Meenakshisundaram},
  title = {Geometry Processing of Conventionally Produced Mouse Brain Slice Images},
  journal = {Journal of Neuroscience Methods},
  year = {2018}
}
```

## License

Feel free to use the code for your own research or project. However keep in mind that this is a research code, thus
it is NOT clean and might have unncessary variables and  wierd inter-dependencies. 


## Contact

Mesh Slicer was created by [Nitin Agarwal](http://www.ics.uci.edu/~agarwal/) to help neuroscience researchers to
generate 2D atlas images by slicing a Virtual 3D Mouse Brain Atlas Model in any arbitarary direction.


