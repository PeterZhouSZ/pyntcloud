.. _samplers:

========
Samplers
========

.. currentmodule:: pyntcloud

Samplers use PyntCloud information to generate a sample of points. This points might or might not were present in the original point cloud.

For example, `RandomPoints` generates a sample by randomly selecting points from the original point cloud. 
In this case all sample's points were present in the original point cloud.

On the other hand, `VoxelgridCentroids` generates a sample by computing the centroid of each group of points inside of each occupied VoxelGrid's cell. 
In this case any of the sample's points were present in the original point cloud.

All samplers take a point cloud as input and return a pandas DataFrame.

This pandas DataFrame can be used to generate a new PyntCloud.

All samplers are accesible trough:

.. function:: PyntCloud.get_sample

We group the avaliable samplers based on what information is used for it's computation.

.. currentmodule:: pyntcloud.samplers


Require points
==============


"points_random_sampling"
------------------------

.. autoclass:: RandomPoints

Require mesh
============

"mesh_random_sampling"
----------------------

.. autoclass:: RandomMesh

Require VoxelGrid
=================

Required args:

    voxelgrid: VoxelGrid.id

.. code-block:: python


    voxelgrid = pointcloud.add_structure("voxelgrid", ...)

"voxelgrid_centers"
-------------------

.. autoclass:: VoxelgridCenters

"voxelgrid_centroids"
---------------------

.. autoclass:: VoxelgridCentroids

"voxelgrid_nearest"
-------------------

.. autoclass:: VoxelgridNearest