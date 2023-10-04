# POLAR3D
a database of bounding box labels and terrain meshes for the <a href="https://ti.arc.nasa.gov/dataset/IRG_PolarDB/" target="_blank">POLAR dataset</a>

# Cover Photos
Pictures in the *CoverPhotos* folder show how we index the rocks in each terrain. The indices do not meet the label orders in the bounding box label txt files. The indices meet the rock ID of the mesh files in each terrain. Original pictures come from the POLAR dataset.

# Bounding Box Labels
Please check the *Labels* folder. The bounding box label files in YOLO format are categorized in the terrain ID folders. Each txt file meets with one HDR photo of the POLAR dataset.

- The label files are named as the following rule:  
[terrain ID]\_[stereo camera position]\_[rover light on/off]\_[Sun azimuth]\_[Left/Right camera of the stereo camera]\_[exposure time in millisecond].txt,  
and "no" in [Sun azimuth] means that there was no simulated Sun (the spot light was turned off).

- The photos of very low exposure time may not have shadow or rock labels, since the photos are so dark that the rocks and shadows are judged invisible by the annotator.

- If the photos have no corresponding label files, it means that the photos have no labels (usually due to nothing visible).

# Terrain Meshes (the separated ground and rocks)
(Until now only Terrains 1, 4, and 11 finished. The rest terrains will be done and uploaded soon.)

Please check the *TerrainMeshes* folder. Meshes of the separated ground and rocks (rock IDs can be referred in the cover photos) of each terrain are built in obj files.

- There is a mesh file of ground for each terrain, named *terrain[terrain ID]_ground.obj*, which was generated by removing all the rocks from the terrain.

- The mesh files of rocks are named as the following rule: terrain[terrain ID]_rock[rock ID].obj

- The coordinate directions are defined as follows,  
+X: Sun azimuth 0 deg, +Y: Sun azimuth 90 deg, and +Z: upward of the sandbox

- The coordinate order in the obj files is defined as: (X, Y, Z).

- Those obj files with file name suffixed by "decimate-005" have only 5% vertices of original object meshes. Those files are used in contact models for collision detection/calculation (such as in PyBullet or Chrono) to mitigate computing loading and facilitate computing speed.

- Terrain 4: Rocks 16 and 17 in the cover photo were combined into Rock 16 mesh obj file, since they were indivisible along X, Y, or Z axis.

# Questions And Bug Logs
Please raise Issues if you have any questions or find any bug. Thank you for your contributions to make this project more complete!

# Ppaer Citation
If you use our dataset, please consider citing our paper, which includes some cases of how to utilize the POLAR3D dataset

<a href="https://arxiv.org/abs/2309.12397" target="_blank">Paper</a>

@misc{chen2023polar3d,
      title={POLAR3D: Augmenting NASA's POLAR Dataset for Data-Driven Lunar Perception and Rover Simulation}, 
      author={Bo-Hsun Chen and Peter Negrut and Thomas Liang and Nevindu Batagoda and Harry Zhang and Dan Negrut},
      year={2023},
      eprint={2309.12397},
      archivePrefix={arXiv},
      primaryClass={cs.RO}
}
# Copyright
All rights reserved by the Simulation Based Engineering Lab in the University of Wisconsin-Madison
