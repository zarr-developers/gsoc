## Progress and updates for the project [Building Codec Registry](https://summerofcode.withgoogle.com/programs/2022/projects/g4IPN5HL) by [Shivank Chaudhary](https://github.com/alt-shivam) for Google Summer of Code 2022

## About Me

Name: Shivank Chaudhary
Email: shivank1128@gmail.com

University: Ramanujan College, University of Delhi, Kalkaji, New Delhi (IN)  
Field of Study: Bachelors in Computer Science (Hons.)  
Grade: 9.18 CGPA  
GitHub: [Alt-Shivam](https://github.com/Alt-Shivam)  
LinkedIn: https://www.linkedin.com/in/shivank-chaudhary-a67681202/  

Location: Noida, Uttar Pradesh, IN (201301)

Time Zone: IST( UTC + 5:30)

## Project Information
Project Idea: Zarr is a format for compressed N-Dimensional arrays and uses many compression algorithms to handle the data. Each of these compression algorithms is bound with an identifier to identify them, But we don’t have any registry to help other languages identify them. To fill this gap we need a registry to be defined for these codecs which is human-readable as well as machine-readable.  

**Project length:** 175 hrs

## Related links:
1) https://github.com/zarr-developers/numcodecs
2) https://github.com/zarr-developers/numcodecs/issues/278
3) https://support.hdfgroup.org/services/filters.html
4) https://github.com/cgohlke/imagecodecs

# Project Weekly Updates:
Project Progress and Information: [Link](https://hackmd.io/@uTe8Vo8gSYeCbwHsQI2Z2Q/SypXtPRD9)

## Pre-GSoC Work
* Created a Research file. [Link](https://hackmd.io/bJ19oZGxS7-_4yuoNY4qXw)
* Documented several codecs into this format.
```
* Blosc
- A brief about how the compression technique works(2-3 lines)
- Where the codec is primarily used(webpages, PNGs, JPEGs, OS etc.)
- Comparing compression and decompression benchmarks/speeds
- Any other info you think is useful
- Important links for the codec(GitHub, Blog post, Implementations etc.)
```
* Created an initial version of Research file on Codecs.
* Created a Pull Request for [Pre-commit configuration](https://github.com/zarr-developers/zarr-python/pull/1015)

## Week 1 & 2
* Added following new codecs.
```
PackBits
Pickle
Quantize
Shuffle
ZFPY
Astype
Bitround
JSON
```
* Documented Codec informations in Research file.
* Created a Pull Request [Link](https://github.com/zarr-developers/zarr-python/pull/1016)
* Created this HackMD for community to track project progress. [link](https://hackmd.io/@uTe8Vo8gSYeCbwHsQI2Z2Q/SypXtPRD9)

## Week 3 & 4
* Created a Github Repo to keep registry files. [Link](https://github.com/Alt-Shivam/Codecs-Registry)
* Created a **csv** file for Registry. [Link](https://github.com/Alt-Shivam/Codecs-Registry/blob/main/Registry.csv)
* Added ImageCodecs.
```
AEC
APNG
AVIF
Brotli
Brunsli
```
and there documentation in research file.
* Created a Pull Request. [Link](https://github.com/zarr-developers/zarr-python/pull/1047)

## Week 5 & 6
* Created a Github-Pages website to show Codec Registry. [Link](https://alt-shivam.github.io/Codecs-Registry/)
* Shifted Codec research file from docs to .md.
* Created a saperate page to show the research file. [Link](https://alt-shivam.github.io/Codecs-Registry/Others/Research.html)
* Added Basic Information on CodecRegistry website.

# Mid-Term Evaluations. :tada:
**Montors Review:**  
  
![image](https://user-images.githubusercontent.com/81817735/184945777-26f1ed64-c30a-45ed-ad96-d421641d4481.png)



## Week 7 & 8
* Added codecIDs to the codecs as per [NumCodecs.](https://github.com/zarr-developers/numcodecs/tree/main/numcodecs)
* Created a new page to show the procedure to create a request to add a new Codec. [link](https://alt-shivam.github.io/Codecs-Registry/Others/AddNewCodec.html)
* Removed other codecs from registry as suggested by mentors. 
* Created a new page to keep other codecs saperate. [Link](https://alt-shivam.github.io/Codecs-Registry/Others/OtherCodecs.html)
* Defined a CodecID Naming Convention for codecs without codecIDs. [Link](https://alt-shivam.github.io/Codecs-Registry/Others/CodecID_Naming_Convention.html)

## Week 9 & 10
* Created a python script `main.py` for registry to perform the following operations:
- Search a codec in remote registry.
- If codec is not present in remote registry, script will redirect the user to the [link](https://alt-shivam.github.io/Codecs-Registry/Others/AddNewCodec.html).
- If codec is present in remote registry, script will display inforamtion `CodecID`,`CodecDescription`,`LastUpdate`,`Type` and `CodecResearch` file link.

## Week 11 & 12
* Created `Example.json` file to store the examples of codecs. [Link]()
* Added support of `Example.json` file to `main.py` python program to show the examples to users.
* Added a guide `How to run and use python script` on official website. [Link](https://alt-shivam.github.io/Codecs-Registry/Others/PythonParser.html)
* Migrated Registry repo to official [zarr-developers](https://github.com/zarr-developers/).
* Links and minor fixes.


# Final Evaluations. :tada:
