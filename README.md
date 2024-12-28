![NyxEngine Logo](docs/readme_assets/nyx-logo-horizontal.png)
## NyxEngine: An experimental, high-performance game engine and rendering pipeline for the terminal. Written in Python with NumPy.
[cmorman89/nyx-engine](https://github.com/cmorman89/nyx-engine)

---

## Status Update: 
### **Release v0.1.0-alpha:** _(12/27/2024)_
> ### **Major Performance Gain** 
> 
> The latest release, v0.1.0-alpha, introduces significant performance improvements to the printing speed of the engine. When printing to the terminal, the ndarrays (frames) must be converted to a printable string format. Profiling the code revealed that this conversion was the significant bottleneck in the terminal printing process. After a many, _many_ rounds of line profiling and optimizing the string generation, the printing speed of a 640x480 resolution frame has improved by 95%, from 0.0954 seconds per frame to 0.0069 seconds per frame -- while still running on a single thread.
>
> This optimization significantly enhances the engine's performance and opens up new possibilities for more complex and faster-rendering games and applications in the terminal. The magnitude of the improvement is such that a minor version bump is well-warranted, despite the lack of any new or major feature.
>
> The GIF below demonstrates the printing speed difference between the previous release (v0.0.4-alpha) and the current release (v0.1.0-alpha).

> | ![Before and after optimization (v0.0.4-alpha vs v0.1.0-alpha)](docs/readme_assets/optimization-before-after.gif) |
> |:--:|
> | **Printing speed of V0.0.4-alpha** _(left, 0.0954 sec/frame)_ **vs v0.1.0-alpha** _(right, 0.0069 sec/frame)_ <br> _Internal Resolution: 640 x 480_  |
