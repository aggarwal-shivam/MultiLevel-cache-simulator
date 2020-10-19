## Abstract
This project implements a MultiLevel Cache simulator to simulate a two level cache model. L1 miss traces are generated for spec CPU files, and then these traces are passed through the simulator to simulate the behaviour of L2 and L3 cache. This was implemented as an assignment in the course CS622 Advanced Computer Architecture at IIT Kanpur in Autumn sem 2020. 

## Contributors
1. Shivam Aggarwal (shivama20@iitk.ac.in)
2. Boppana Tej Kiran (tejkiranb20@iitk.ac.in)

## Working
First we needed to convert the binary files into a suitable format. So we converted these traces into text files which only contains the address of misses from L1 cache. Cache is implemented in  cache.py file. We can implement one of the three policies between caches, i.e. Inclusive, Exclusive and Nine. The simulator is implemented in simulator.py file. If you want to run the simulator on a file with all three policies then use the run.sh script.

All the traces are present in the traces directory. The names of different binary files and their corresponding text file is as follow.

Binary file name | text file name
--------------------|------------------
bzip2.log_l1misstrace|bzip2
gcc.log_l1misstrace|gcc
gromacs.log_l1misstrace|gromacs
h264ref.log_l1misstrace|h264
hmmer.log_l1misstrace|hmmer
sphinx3.log_l1misstrace|sphinx3

To run the simulator for a file on all three policies, use following commands.
```sh
$ ./run.sh
$ arg
```
Here, arg will be the name of text file, for which you want to run the simulator.

And, if you want to run the simulator for a particular policy, use following mapping table
Policy name | value_mapped
----|-----
Inclusive | 1
Nine | 2
Exclusive | 3

Now use the following command to run the simulator.
```sh
$ python3 simulator.py arg1 arg2
```
here arg1 will be the name of text file and arg2 will be the value corresponding to the policy.

#### Note

Although Cache parameters are fixed in the simulator, but you can change them according to your need in simulator.py