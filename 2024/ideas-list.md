# ⚡️ GSoC 2024 Project Ideas ⚡️

---

Thanks for your interest in applying for Google Summer of Code with Zarr. We welcome applications from all backgrounds, identities and abilities and encourage
applications from under-represented groups in tech.

## About Zarr

[Zarr](https://zarr.dev/) is a format for the storage of chunked, compressed, N-dimensional arrays.

## Getting Started

This guide illustrates a few steps that’ll help you get acquainted with Zarr:

- Check out the [contributing guide](https://zarr.readthedocs.io/en/stable/contributing.html) and set up the development environment.
- Check out the Zarr tutorials [here](https://zarr.readthedocs.io/en/stable/tutorial.html) and run some examples.
- Check out the [docs](https://zarr.readthedocs.io/en/stable/genindex.html) for detailed info.
- Additionally, go through the Zarr Storage Specifications [V2](https://zarr-specs.readthedocs.io/en/latest/v2/v2.0.html) and [V3](https://zarr-specs.readthedocs.io/en/latest/v3/core/v3.0.html). These documents provides the technical specifications of the protocol and format used for storing Zarr arrays.

You can start by going through the issues labelled as [‘help wanted'](https://github.com/zarr-developers/zarr-python/issues?q=label%3A%22help+wanted%22+is%3Aissue+is%3Aopen) and submit a PR.

Please find project ideas listed below! 👇🏻

## Project Idea I - Bit-Packing

> Abstract  🗂

Many engineering and science domains work with data from Analog-to-Digital Converters (ADCs). These ADCs typically return an (unsigned) integer value, e.g., 10 bits or 12 bits. When stored as (u)int16, this creates a substantial overhead. Therefore, we want to investigate if a "bit packing" shuffle filter can be implemented to just pack the data (without using conventional compression techniques) or to pack the data in addition to using existing compression.

This idea was discussed in the Zarr Benchmarking & Performance meetings (notes [here](https://docs.google.com/document/d/1s5VBWqyh_MliVZCy9KK8ZnMy2pIeKF5pTLI2XWZ0MNE/edit?usp=sharing)) and multiple participants expressed their interest in this feature. Additional topics discussed:

- Use additional entropy coding step: Huffman, arithmetic, etc.

> Tasks 📝

We haven’t defined concrete steps for this project yet. We encourage the interested contributor to discuss the procedure/tasks with the mentor. Please read, understand and document existing information about shuffle filters and how they are used in Zarr.

- Check by how much file size can be improved
- Check by how much write speed can be improved (either just packing, or packing and compression)
- Check by how much read speed can be improved (either just packing, or packing and compression)

> Extended Tasks 📝

Benchmark obtained implementations and present results to the Zarr Benchmarking & Performance group.

Perhaps a "stretch goal", for hardware-inclined coders, could be to hand-code at least one SIMD-optimized bit-packing algorithm, and compare its performance against an algorithm written purely in a high-level language.

> Project Length ⏰

175 hours

> Priority ⏩

Medium

> Complexity 👨🏻‍💻

Medium

> Potential Mentors 😇

[Vincent Immler](mailto:vincent.immler@oregonstate.edu)

## Project Idea II - Low-Latency Optimizations

> Abstract  🗂

Previous investigations within the Zarr Benchmarking & Performance group revealed that when Zarr is used in a low-latency environment (e.g., data is read from a fast SSD) in combination with one-pass statistical algorithms or cryptographic hash functions to process the data, then the burden of I/O is higher than that of the computation, which makes an unoptimized asynchronous prefetch fail.

> Tasks 📝

The goal of this project is to investigate this problem in a more detailed way, compare to theoretical throughput limits, and perform experiments with the upcoming Zarr V3 version (in particular, with sharded selections over multiple chunks), to either confirm improvements over the previous behavior, or to investigate further improvements that can be realized without a full re-implementation of Zarr-Python. Examples:

- Prefetch continuously through a session and/or more efficient OS interfaces (io_uring)
- Wrap callable function into Zarr for automated iteration through the data
- Check compatibility with Numba for processing outside of the OS-level interfaces

Benchmark reference:
- https://github.com/zarr-developers/zarr-benchmark

> Extended Tasks 📝

Benchmark obtained implementations and present results to the Zarr Benchmarking & Performance group.

> Project Length ⏰

175 hours

> Priority ⏩

Medium

> Complexity 👨🏻‍💻

High

> Potential Mentors 😇

[Vincent Immler](mailto:vincent.immler@oregonstate.edu)

> Related Links 🔗

- Zarr-Python issues
	- from 2020: https://github.com/zarr-developers/zarr-python/issues/547
	- from 2020: https://github.com/zarr-developers/zarr-python/issues/536
- 2021: https://github.com/pangeo-forge/pangeo-forge-recipes/issues/89
- https://github.com/martindurant/async-zarr
- https://github.com/scalableminds/zarrita/blob/async/zarrita/store.py 
- https://github.com/scalableminds/zarrita/blob/async/zarrita/store.py 
