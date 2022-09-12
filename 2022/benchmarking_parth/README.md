## Progress and updates for the project [Benchmarking Zarr Implementations](https://summerofcode.withgoogle.com/programs/2022/projects/qa93Xk9L) by [Parth Tripathi](https://github.com/parthxtripathi/) for Google Summer of Code 2022

# About Me:

- Name: Parth Tripathi
- A 3rd-year undergraduate student pursuing a major in Information Technology and Mathematical Innovations at Cluster Innovation Centre, University Of Delhi, India.
- Gmail: [parthxtripathi@gmail.com](parthxtripathi@gmail.com)
- Github: [parthxtripathi](https://github.com/parthxtripathi)
- LinkedIn: [Parth Tripathi](https://www.linkedin.com/in/parth-tripathi-689506202/)
- Medium: [parthxtripathi](https://medium.com/@parthxtripathi)
- New Delhi, India (GMT +5:30)

# Project Information:
- **Project Idea:** Zarr is a format for the storage of chunked, compressed, N-dimensional arrays that is inspired by HDF5, h5py and bcolz and depends on NumPy. This project works on the implementation of benchmarking in Zarr using Airspeed Velocity(ASV) in order to catch any changes that introduce a performance regression.
- **Project Length:** 175 hours

# Related Links:
1. [Complete Project Idea](https://summerofcode.withgoogle.com/programs/2022/projects/qa93Xk9L)
2. [Blog](https://medium.com/@parthxtripathi/pre-gsoc-journey-9a6a580b9014)
3. [Project HackMD](https://hackmd.io/TfAoFELyRMapjQqo3t5XnQ?view)
4. [Guide to work with Zarr-ASV](https://hackmd.io/uNr_pyaCRiyjBmmoDjvtHg)
5. [Zarr Documentation](https://zarr.readthedocs.io/en/stable/)
6. [ASV Documentation](https://asv.readthedocs.io/en/stable/)
 

# GSoC Journey:
## Phase-1
## Community Bonding Period: 
- In the community bonding period, I interacted with the mentors and got to know about the whole Zarr community.
- We as a team discussed how effective benchmarks could be and told my plan to execute them.
- Learned how ASV works and went through the code base of Zarr.

## Week 1:
- Explored the Zarr repository.
- Worked on ASV & started creating the asv.conf.json file for the benchmarking suite.

## Week 2: 
-  Completed the asv.conf.json file.
- Started developing the benchmarks for the functions `save_array` , `save_group` , `save` and `copy` in the convenience module.

## Week 3: 
- Benchmarks for the `save_array` , `save_group` , `save` and `copy` failed.
- Started developing benchmarks for the functions `load` , `open` , `copy_store` and `copy_all` in the convenience module. 
- Changed the asv.conf.json file dependencies. 
- Published a blog.

## Week 4:
- Benchmarks for the convenience failed.
- After discussion with the mentors we started with the creation module.
- Started developing benchmarks for the functions `create`, `empty`, `full`, `zeros`, `ones`, `open_array` and `array`in the creation module. 

## Week 5: 
- The creation module benchmarks were developed.
- Graphs/Regression list were obtained. 
- Examined the graphs with the mentors. 
- Got inputs for the betterment of the graphs and the regressions list.

## Evaluation-1 (July 25-July 29) : Passed
Mentor's Review: ![](https://i.imgur.com/JTLgPlf.png)

## Phase-2

## Week 6:
- Change in the asv.conf.json file with dependencies. Removed all other dependencies and ran the asv just with Zarr as a dependencies. 
- Obtained the graphs and regression list just with zarr as a dependency. 

## Week-7: 
- Wrote the [complete guide](https://hackmd.io/uNr_pyaCRiyjBmmoDjvtHg) to work with asv in Zarr. 
- Obatined new grpahs with control of the every dependency in zarr.  

## Week 8:
- Testing of Zarr's major release is going on.
- Created the new environment for the creation module.

## Week 9:
- Ran the benchmarks on the new environment. 
- Ran the benchmarks for all the commits. (Creation)

## Week 10: 
- Compared the new graphs with previous ones. 
- Ran and checked the benchmarks for all the versions.

## Week 11 & 12:
- Completed the creation module.
- Started off with convenience module and completed it for the `open` function. 

## Final Evaluations 🎉