# Interprocess-Communication

This class facilitates communication of data between different programs by creating a shared memory space and then writing the data to it. This code uses Boost 1.76.0, which can be found at https://www.boost.org/. To control writing and extraction of data, each vector of data is assigned a key that can be referenced to extract the data later. This program is designed to work with a series of traffic lights, though it can be repurposed for other ends. 

The functions within this class are: UpdateLight, CheckOp, CheckKey, GetLight, and Cycle.

UpdateLight inserts data into a vector in the shared memory specified by a key.

CheckOp ensures that a vector in the shared memory can be recalled by specifying its key.

CheckKey ensures that the key for a vector corresponds to data. I prefer to run this function directly after assigning all my data to the shared memory.

GetLight returns a specific vector by calling the key.

Cycle is a more general GetLight and returns all the data from the shared memory by building an unordered_map with the data and keys. 
