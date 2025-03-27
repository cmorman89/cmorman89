[![promptBot](https://github.com/user-attachments/assets/1b19770f-b7f6-4c75-a5ad-78b618b76211)](https://cmorman89.github.io/local-ai-chatbot)
## prompt:BOT
React-based UI for interacting with a locally-hosted LLM (such as with LM Studio).

---

[![NyxEngine Logo](docs/readme_assets/nyx-logo-horizontal.png)](https://github.com/cmorman89/nyx-engine)

## **NyxEngine:**
An experimental, high-performance graphic rendering pipeline and game engine for the terminal. Written in Python with NumPy.

**See it in action: [NyxEngine (GitHub Pages)](https://cmorman89.github.io/nyx-engine)**

---

## **Status Updates:**

**Note**
I have to take a temporary development break from NyxEngine as I focus on finding a job these next couple of weeks! If you notice less activity, the project is not dead -- just paused for now.

---

**Rust Progress** ([Demo](https://www.youtube.com/playlist?list=PLvkXEUKaigSyHm_Q2-Cmmdko0IKtBOLpU)): _(01/07/2025)_
<details>
<summary>TrueColor 24-bit Terminal Printing</summary>

> The transition to Rust is well underway, and progressing much faster than I had anticipated given Rust's reputation for a steep learning curve. I am still working on properly benchmarking Rust code, so I have no hard numbers to share yet. However, the Rust code is already vastly outperforming the Python code, even in its current state. Right now, I am in the "just get it to work" stage so it lacks any significant optimizations. Despite this, the Rust version of `HemeraTermFx` can print full 24-bit RGB color to to the terminal at a relatively usable speed and resolution (360*200 @~20-60 fps).
> 
> See print GIF demos [here](https://www.youtube.com/playlist?list=PLvkXEUKaigSyHm_Q2-Cmmdko0IKtBOLpU) (note: same link as above).
>
> The next steps are to:
> - Properly allocate memory for the various buffers -- and reusing those buffers throughout the lifetime of the program.
> - Begin working on a basic delta framebuffer system once the memory allocation is sorted.
> - Trial various quantization methods for the 24-bit RGB colors to allow for dynamic fidelity adjustments as a means to keep a stable frame rate.
>   - For example, if the framerate is slipping, the engine can automatically reduce the color fidelity to maintain a stable frame rate.
>   - Conversely, if the engine is spending time sleeping, it can increase the color fidelity to improve the visual quality.
> - Figure out how to profile Rust code to get a better idea of where the bottlenecks are and begin aggressively optimizing the code.

</details>

---

**Release v0.1.0-alpha:** _(12/27/2024)_

<details>
<summary>Click here to expand the demo!</summary>

>  ### **Major Performance Gain** 
> 
> The latest release, v0.1.0-alpha, introduces significant performance improvements to the printing speed of the engine. When printing to the terminal, the ndarrays (frames) must be converted to a printable string format. Profiling the code revealed that this conversion was the significant bottleneck in the terminal printing process. After a many, _many_ rounds of line profiling and optimizing the string generation, the printing speed of a 640x480 resolution frame has improved by 95%, from 0.0954 seconds per frame to 0.0069 seconds per frame -- while still running on a single thread.
>
> This optimization significantly enhances the engine's performance and opens up new possibilities for more complex and faster-rendering games and applications in the terminal. The magnitude of the improvement is such that a minor version bump is well-warranted, despite the lack of any new or major feature.
>
> The GIF below demonstrates the printing speed difference between the previous release (v0.0.4-alpha) and the current release (v0.1.0-alpha).
>
> | ![Before and after optimization (v0.0.4-alpha vs v0.1.0-alpha)](docs/readme_assets/optimization-before-after.gif) |
> |:--:|
> | **Printing speed of V0.0.4-alpha** _(left, 0.0954 sec/frame)_ **vs v0.1.0-alpha** _(right, 0.0069 sec/frame)_ <br> _Internal Resolution: 640 x 480_  |
</details>

---

### Repo: [cmorman89/nyx-engine](https://github.com/cmorman89/nyx-engine)
