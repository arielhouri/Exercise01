# Exercise01
### by Ariel Houri & Yonatan Semidubersky

>The classification k-nearest neighbors algorithm (k-NN),
return a class membership.
An object is classified by a plurality vote of its neighbors,
with the object being assigned to the class most common among its k nearest neighbors. [wikipedia](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm)

In this assignment, we implemented a KNN Classifier for irises.
Given a set of data for an unclassified iris and a natural number k,
we determine his type using the KNN algorithm.

## Instruction:
1. The first thing is to set the database with a list of already-classified Irises. In order to do that, you need to
   put the data in the file named: `classified.csv`. The data will be in this formation:
   `bottomwidth,bottomlength,topwidth,topLength,type`, for example: `5.4,3.9,1.7,0.4,Iris-setosa`. There is a default database inside the file.
2. After that, You need to push the data of the Irises that you want to classify in the file named: `unclassified.csv`.
   The data will be in this formation:
   `bottomwidth,bottomlength,topwidth,topLength`.
   There is also a default set of data inside the file.
3. Then, you compile the code using the following command: `g++ -std=c++11 *.cpp` and run it using the following
   command `./a.out k` where `k` is an integer, which will be used for the algorithm itself. Note that if the value
   of `k` is too large/small, an error message will be written into the console and the program will stop.
4. The output of the program will be in the files named: `euclidean_output.csv`, `manhattan_output.csv` and
   `chebyshev_output.csv` (Every files will have the types determined according to a different metric, which is also
   mentioned at the name of the file).
5. Note that if you want to use the classified again, you don't have to clear the output files, they will be emptied
   automatically.
## The Algorithm:
- The Main class is in charge of setting up the data - converting the input (.csv files) into objects. It also writes the data to the file when a flower is classified.
- The Iris class stores data about a specific flower, and can measure its distance to another flowers (there are 3 possible metrics)
- The ClassifierKNN class is in charge of arranging the data, and process the input for the algorithm.
- IrisAndDistance is an object that stores an iris and his distance from the unclassified iris.
Also, the algorithm uses "quick-select" in order to find the closest irises. We used Quick-Select algorithm instead of sorting because we don't need to know what is the exact order of the irises, and the time complexity of the Select algorithm is lower than the Sorting algorithm.
### note:
if there will be a few points in same distance from the main point, the algorithm will *count* them all (even if it's more then k).
