# ⚡️ GSoC 2022 Project Ideas ⚡️

---

Thanks for your interest in applying for Google Summer of Code with Zarr. We welcome applications from all backgrounds, identities and abilities and encourage
applications from under-represented groups in tech.

There have been changes in the program by Google. To know more, please read this: https://opensource.googleblog.com/2021/11/expanding-google-summer-of-code-in-2022.html

Since this is the first time Zarr is participating in Google Summer of Code, we’re excited and are looking forward to welcoming every one of you to the community! We recommend you go through the getting started guide and get yourselves acquainted with the project before you start working on your proposals.

## About Zarr

[Zarr](https://zarr.dev/) is a format for the storage of chunked, compressed, N-dimensional arrays.

## Getting Started

This guide illustrates a few steps that’ll help you get acquainted with Zarr:

- Check out the [contributing guide](https://zarr.readthedocs.io/en/stable/contributing.html) and set up the development environment.
- Check out the Zarr tutorials [here](https://zarr.readthedocs.io/en/stable/tutorial.html) and run some examples.
- Check out the [docs](https://zarr.readthedocs.io/en/stable/genindex.html) for detailed info.
- Additionally, go through the [Zarr Storage Specification V2](https://zarr.readthedocs.io/en/stable/spec/v2.html). This document provides a technical specification of the protocol and format used for storing Zarr arrays.

You can start by going through the issues labelled as [‘help wanted'](https://github.com/zarr-developers/zarr-python/issues?q=label%3A%22help+wanted%22+is%3Aissue+is%3Aopen) and submit a PR.

Please find project ideas listed below! 👇🏻

## Project Idea I - Add multi-language Zarr implementation tests

> Abstract  🗂

Zarr is a chunked, compressed format for the storage for N-dimensional arrays like those created by NumPy. There are a number of Zarr implementations across a wide range of programming languages that all need to conform to the same specification. We would like to have Zarr tested across as many of these languages as possible in order to ensure conformance. You can find implementations of Zarr in other languages [here](https://github.com/zarr-developers/zarr_implementations).

> Current State 👀

Some implementations have tests but those tests work for some cases and don’t work across all the desirable cases. For example, Test 1 works for write functionality but not for read or Test 2 works for read functionality but not write or Test 3 doesn’t exist. Every Test[1, 2, 3…] basically tests different features across Zarr from the existing [spec](https://zarr.readthedocs.io/en/stable/spec/v2.html).

> Tasks 📝

The contributor should pick implementations according to the language of their choice. We expect the contributor to select at least 2-3 implementations and write test cases for them.

If need be, we are also open to dividing this project into multiple projects among different contributors according to their language of choice.

1. A small driver application will be needed in each language. Initially, the driver should create a Zarr file using the given library and evaluate if the output can be read by other implementations.
2. Extend the driver to reading Zarr files from all other implementations [#25](https://github.com/zarr-developers/zarr_implementations/issues/25), reporting (and perhaps fixing!) any failures.
3. After this, the contributor needs to write the tests for the selected implementation of Zarr as discussed with the mentor and cover all the existing working features of the specific implementation.

We’d recommend the contributor get in touch with the mentor for this project before submitting the final application. This will help us in the allotment of different implementations and answer any questions/issues.

> Extended Tasks 📝

Add all the tests which would cover all the features from existing [spec](https://zarr.readthedocs.io/en/stable/spec/v2.html) and also are of importance according to maintainers.

> Expected Outcome 🔖

As the Zarr ecosystem grows, this project will verify that all implementations produce compatible and robust data.
Also, this project aims to identify if there are any shortcomings in implementations, then report and fix them.

> Prerequisites 👍🏻

Familiarity with testing, implementations’ programming language & Zarr.

> Project Length ⏰

350 hours

> Priority ⏩

High

> Complexity 👨🏻‍💻

Medium

> Potential Mentors 😇

[Josh Moore](https://github.com/joshmoore)

> Related Links 🔗

1. https://github.com/zarr-developers/zarr_implementations/pull/37
2. https://github.com/zarr-developers/zarr_implementations/pull/24
3. https://github.com/zarr-developers/zarr_implementations/pull/21
4. https://github.com/zarr-developers/zarr_implementations/pull/23
5. https://github.com/zarr-developers/zarr_implementations/pull/10

## Project Idea II - Build registry of Zarr codecs

> Abstract  🗂

Zarr is a chunked compressed format for the storage of N-dimensional arrays like those created by NumPy. Each compression algorithm used by Zarr is assigned an identifier by the [numcodecs](https://github.com/zarr-developers/numcodecs) library. In order to make these identifiers useful in other programming languages, [#278](https://github.com/zarr-developers/numcodecs/issues/278) requires a registry to be defined that is machine-readable from multiple programming languages (C, Java, Javascript, etc.).

> Current State 👀

Need to start the project from scratch. Discussions related to this project are [here](https://github.com/zarr-developers/numcodecs/issues/278).

> Tasks 📝

1. Research and compare existing lists of compression filters (e.g. from HDF5 and [imagecodecs](https://github.com/cgohlke/imagecodecs)).
2. Document all of the current codecs and their identifiers from the research in an issue.
3. Propose a format for the registry in an issue for community review.
4. Create and publish the registry, both in a machine-readable as well as human-friendly form.
5. Document the steps for others to update the registry.

After the above-mentioned tasks are done we expect a page on the website which shows the registry.

> Extended Tasks 📝

Write tests that show which codecs from each implementation are supported by other implementations and display a matrix of the results.

> Expected Outcome 🔖

- This project will give the contributor insight into low-level details for several file formats and compression techniques as well as the importance of standardisation for
keeping data readable.
- The registry built by the contributor will serve as a critical bridge between several communities for different programming language like Python, C, Java as well as multiple
file formats like Zarr, NetCDF, HDF5 etc.

> Prerequisites 👍🏻

Familiarity with Python, HTML & static website generators like Jekyll. 

> Project Length ⏰

175 hours

> Priority ⏩

Medium

> Complexity 👨🏻‍💻

Easy

> Potential Mentors 😇

[Sanket Verma](https://github.com/MSanKeys963) & [Josh Moore](https://github.com/joshmoore)

> Related Links 🔗

1. https://github.com/zarr-developers/numcodecs
2. https://github.com/zarr-developers/numcodecs/issues/278
3. https://support.hdfgroup.org/services/filters.html
4. https://github.com/cgohlke/imagecodecs

## Project Idea III - Benchmark Zarr implementations

> Abstract 🗂

Zarr is a chunked compressed format for the storage of N-dimensional arrays like those created by NumPy. Performance when reading and writing very large arrays is critical for user acceptance. With [#337](https://github.com/zarr-developers/zarr-python/issues/337), we would like to have benchmarks updated with each version of Zarr showing the long-term tendency of various metrics, warning developers if a change causes too much slowdown. [Airspeed Velocity (ASV)](https://github.com/airspeed-velocity/asv) is a likely tool for this project. (Example output can be seen in the [aicsimageio](https://allencellmodeling.github.io/aicsimageio/_benchmarks/index.html) project.)

> Current State 👀

Need to start the project from scratch. Discussion related to project are [here](https://github.com/zarr-developers/zarr-python/issues/337).

> Tasks 📝

1. Define a number of simple metrics for reading and writing Zarr files, asking the community for further suggestions. Examples include writing arrays in a number of different sizes & shapes; reading those same arrays back in.
2. Write code and implement these metrics in [Zarr-python](https://github.com/zarr-developers/zarr-python) and optionally in other programming languages available in [zarr_implementations](https://github.com/zarr-developers/zarr_implementations).
3. Publish the benchmarks results.

> Extended Tasks 📝

A further stretch goal would be to compare the same operations using HDF5 or NumPy files (.npy) as described in [#519](https://github.com/zarr-developers/zarr-python/issues/519).

> Expected Outcome 🔖

- This project will allow the contributor to learn the basics of the Zarr format and APIs as well as experiment with benchmarking.
- The community will benefit from a clear, visual representation of Zarr’s speed overtime which will identify areas for further optimisation. 

> Prerequisites 👍🏻

Python and if the contributor aims to complete the extended tasks then familiarity with languages in those implementations too.

> Project Length ⏰

175 hours if working on Zarr-python and 350 hours if working for all the other implementations

> Priority ⏩

Low

> Complexity 👨🏻‍💻

Low

> Potential Mentors 😇

[Josh Moore](https://github.com/joshmoore) and [Sanket Verma](https://github.com/MSanKeys963)

> Related Links 🔗

1. https://github.com/zarr-developers/zarr-python/issues/337
2. https://github.com/TileDB-Inc/tiledb-benchmarks/blob/master/bcolz-zarr/slicing-benchmarks.ipynb
3. https://github.com/airspeed-velocity/asv
4. https://allencellmodeling.github.io/aicsimageio/_benchmarks/index.html
5. https://github.com/zarr-developers/zarr-python/issues/519

## Project Idea IV - Standardizing .zmetadata

> Abstract 🗂

Zarr is a chunked compressed format for the storage of N-dimensional arrays like those created by NumPy. Currently, we use the ‘flat-encoding’ format for consolidated metadata. The aim of this project is to standardise the .zmetadata format for consolidated metadata. This project includes researching the existing format for consolidated metadata and adapting and standardising one of the formats for Zarr. Previously, there have been discussions regarding this topic and the contributor needs to follow up with all of them and propose a method to adapt one of the formats, implement them and test them.

> Current State 👀

Need to start the project from scratch. Discussion related to project are [here](https://github.com/zarr-developers/zarr-specs/issues/113).

> Tasks 📝

1. Research and understand .zmetadata from Zarr-python implementation.
2. Look for other [implementations](https://docs.openmicroscopy.org/bio-formats/6.8.1/supported-formats.html) of metadata and document them well.
3. Document how the output would look if implemented in Zarr.
4. Add support for .zmetadata in upcoming spec V3.
5. Implement .zmetadata in Zarr and write tests.

> Extended Tasks 📝

We aim to have .zmetadata in Python implementation but an extended goal could be to implement this in other implementations of Zarr too.

> Expected Outcome 🔖

- This project will help explicitly enumerate all of the relevant Zarr metadata objects (.zarray, .zattrs, .zgroup) within a directory which would eliminate the need to
explicitly ‘list’ the store.

- Also, it collects the contents of those files within a nested JSON structure reducing the number of distinct read operations a user needs to open a dataset which
improves performance for high-latency stores.

> Prerequisites 👍🏻

Familiarity with Python. Understanding of standards. Documentation and research skills. Communicating thoughts in a well-structured manner to the community and mentors.

> Project Length ⏰

175 hours

> Priority ⏩

Medium

> Complexity 👨🏻‍💻

Medium

> Potential Mentors 😇

[Josh Moore](https://github.com/joshmoore), [Sanket Verma](https://github.com/MSanKeys963) & [Ryan Abernathy](https://github.com/rabernat)

> Related Links 🔗

1. https://github.com/zarr-developers/zarr-specs/issues/113
2. https://github.com/zarr-developers/zarr-specs/issues/41
3. https://github.com/zarr-developers/zarr-specs/issues/41#issuecomment-835580731 
4. https://github.com/zarr-developers/zarr-specs/issues/121
5. https://docs.openmicroscopy.org/bio-formats/6.8.1/supported-formats.html

## Project Idea V - Awkward Arrays

> Abstract 🗂

We’re thinking of having Awkward Arrays support in Zarr. Previously, there has been only discussion about this. You can check them out [here](https://github.com/zarr-developers/community/issues/29).

The inspiration comes from [here](https://github.com/scikit-hep/awkward-1.0). Awkward arrays let you manipulate JSON-like data with NumPy-like idioms. You can check out the documentation [here](https://awkward-array.readthedocs.io/en/latest/index.html).

Previously the development has been mainly driven by high energy physics use cases but the need for variable-length data structure and other “awkward” structures is common to other domains too. The use cases and stakeholders for this project have been increased in the past few years and we’d like to initiate the development of this.

The work in Awkward array could inform if/how Zarr might support some of these features.

> Tasks 📝

We haven’t defined concrete steps for this project as there has been a lot of discussions about this one in the past. We encourage the interested contributor to discuss the procedure/tasks with the mentor. Just a few things you need to take care of before contacting the mentor:

1. Read, understand and document existing information about awkward arrays.
2. Go through existing discussions listed here:
    1. https://github.com/zarr-developers/community/issues/29
    2. https://github.com/zarr-developers/zarr-specs/issues/62

We understand this project requires a substantial amount of time and effort and the GSoC time frame wouldn’t allow you to completely implement the feature in Zarr that’s why we’re also considering a case where the contributor could develop a prototype for this feature which could act as a stepping stone for further development.

> Current State 👀

Need to start the project from scratch. Discussion related to project are [here](https://github.com/zarr-developers/community/issues/29).

> Extended Tasks 📝

None

> Expected Outcome 🔖

- Awkward Arrays open the possibility of storing new data types in Zarr which would expand the user and community reach of the project.
- We expect from the contributor a prototype PR which could be used as an initial point for development of an ‘Awkward Arrays’ specification.

> Prerequisites 👍🏻

Familiarity with Python, NumPy, JSON and Awkward Arrays. Having some experience with Zarr is a plus.

> Project Length ⏰

350 hours

> Priority ⏩

Medium

> Complexity 👨🏻‍💻

High

> Potential Mentors 😇

[Josh Moore](https://github.com/joshmoore), [Martin Durant](https://github.com/martindurant) & [Jim Pivarski](https://github.com/jpivarski)

> Related Links 🔗

1. https://github.com/zarr-developers/community/issues/29
2. https://github.com/scikit-hep/awkward-1.0
3. https://github.com/zarr-developers/zarr-specs/issues/62
4. https://awkward-array.readthedocs.io/en/latest/index.html


## Other Projects

We also have other project ideas that contributors could work on. They are listed below:

- [Tree Bottleneck](https://github.com/zarr-developers/zarr-python/issues/224)
- [Transactions](https://github.com/zarr-developers/zarr-python/issues/247)
- [DataFrames](https://github.com/zarr-developers/zarr-python/issues/149)/[Paraquet](https://github.com/zarr-developers/zarr-python/issues/515)

You can check the description of these additional projects in the aforementioned issues.


We encourage interested contributors to go through the above-mentioned projects and check them out. If any of the projects seem interesting to you and you want to spend your summer working on contributing to one of the important and cool open-source projects please feel free to reach out to [Sanket Verma](mailto:svsanketverma5@gmail.com) or [Josh Moore](mailto:j.a.moore@dundee.ac.uk).

You can also join the community discussion at our [Gitter channel](https://gitter.im/zarr-developers/community).

Best,

~Zarr Community ❤️
