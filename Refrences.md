# Backgroud - 

1. Satellite Data (Raster + GeoTIFF)
Raster Data

What it is: A grid of pixels (like a photo), each pixel storing values (e.g., brightness, reflectance).

Used in: Satellite imagery, DEMs, slope maps.

File Formats:

GeoTIFF (.tif) → most common (stores raster values + georeferencing info).

NetCDF (.nc) → common in climate and environmental datasets.

HDF5 (.h5) → used by NASA (e.g., MODIS data).

✅ GeoTIFF is the standard for satellite + elevation data.

Example: Landslide4Sense dataset uses GeoTIFF with 14 bands (Sentinel-2 + DEM + slope).

Each band = a raster layer.

2. LiDAR / Photogrammetry Data
Point Clouds

Raw LiDAR data = millions of 3D points (X, Y, Z, sometimes intensity or color).

File Formats:

LAS (.las) → standard LiDAR format (binary).

LAZ (.laz) → compressed LAS (smaller file size).

PLY (.ply) → point cloud format, also used in 3D scanning.

XYZ (.xyz) → simple text format with X, Y, Z coordinates.

Meshes (Photogrammetry Outputs)

Photogrammetry often produces 3D surface meshes.

File Formats:

OBJ (.obj) → 3D mesh format with geometry + texture.

FBX (.fbx), GLTF (.gltf) → used for 3D visualization.

Rasterized LiDAR Products

LiDAR point clouds can be processed into rasters (like satellite images):

DEM (Digital Elevation Model) → ground surface elevation.

DSM (Digital Surface Model) → includes trees/buildings.

DTM (Digital Terrain Model) → only bare ground.

Stored as GeoTIFFs (so they can align with satellite rasters).

3. How They Work Together

For rockfall prediction:

Satellite (GeoTIFF raster)

Multispectral bands (vegetation, soil moisture, geology).

DEM/Slope from satellites (ALOS, SRTM).

LiDAR (Point cloud or rasterized DEM/DTM)

High-resolution slope geometry.

Detects micro-changes in slope over time.

Combined workflow

LiDAR point cloud → process into DEM (GeoTIFF).

Use both raw raster (satellite) + derived raster (LiDAR DEM) in ML models.
