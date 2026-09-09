# Shade Source 2 SDK

Generated C++23 SDKs for supported Source 2 games. The SDKs are produced by
[shadegenerator](https://github.com/arisuwine/shadegenerator).

The `main` branch contains documentation only. Select a game branch when adding
the repository to a project.

## Available SDKs

| Game | Branch |
| --- | --- |
| Counter-Strike 2 | `cs2` |
| Dota 2 | `dota2` |
| Deadlock | `deadlock` |

Each game branch always contains the latest SDK published for that game.

## Requirements

- Windows x64
- CMake 3.20 or newer
- A compiler with C++23 support
- Git

## CMake Usage

Choose the required game through `GIT_TAG`:

```cmake
include(FetchContent)

FetchContent_Declare(
    shade_source2_sdk
    GIT_REPOSITORY https://github.com/arisuwine/shade-source2-sdk.git
    GIT_TAG cs2
    GIT_SHALLOW TRUE
)

FetchContent_MakeAvailable(shade_source2_sdk)

target_link_libraries(your_target PRIVATE shade)
```

The SDK can then be included directly:

```cpp
#include <shade/sdk/client/C_BaseEntity.hpp>
```

Replace `cs2` with `dota2` or `deadlock` to use another game SDK.

## Repository Layout

The game branches have the following structure:

```text
shade-source2-sdk/
├── CMakeLists.txt
├── README.md
└── shade/
    ├── CMakeLists.txt
    └── sdk/
        ├── types.hpp
        └── ...
```

The root `CMakeLists.txt` exposes the generated `shade` interface target through
`FetchContent`. The generated SDK itself remains inside the `shade` directory and
can also be copied into another project without using `FetchContent`.
