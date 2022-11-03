# Pairing points algorithm

### PROJECT BRIEFING

Custom implementation of an algorithm to group points into pairs.

### PROJECT OVERVIEW

The aim of the project was to create an algorithm that groups points from two different
sets of points on the Cartesian plane (in the form of a geojson) into pairs. This was
necessary so that points are not paired in a naive way, as this leads to a situation
where certain points are paired after the longest distances between them instead of
the shortest distances.

For the creation of the algorithm, two small sets of points were drawn up,
with the points forming natural pairs with each other (distance criterion).
In one of these sets of points, the position of a couple of points was changed
on purpose, so that a naive approach would produce bad pairing results.

### SUMMARY

The following approaches were tried:

- naive approach - groups points close together well, the larger the dataset the greater the errors in determining pairs of the furthest points.
- shapely.nearest_point - using the shapely.nearest_points module, the closest points around the point to be checked were wanted. The problem was that it was not possible to exclude the repeated assignment of points
- shapely.cKDTree.query_pairs - using the shapely.cKDTree.query_pairs module, one wanted to obtain the closest points around the checked point that were within a given radius. Problematic was the inability to compare two datasets and the case where none of the points searched for were within the given radius
- shapely.cKDTree.query - The shapely.cKDTree.query module was used to find the most satisfactory results. similar to query_pairs, the closest 5 results were compared and by sorting only by a narrow group of the closest points, the most relevant pair of points were found.

### INSTALATION

Short guide to get startd with sofware:

1. Clone the repo or donwload zip file.
2. Open the folder with IDE editor.
3. Create conda virtual environment.
4. Install all the libraries form requirements.txt

### AUTHOR

Michał Piernicki 
