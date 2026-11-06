# AstroFormats

Open-source C++ libraries for the file formats of astronomical imaging. Each one is written from the published
specification of its format, treats every file as untrusted input, and has an API that does not depend on any
application.

| Library | Format | Status |
|---|---|---|
| [OpenXISF](https://github.com/astroformats/openxisf) | [XISF 1.0](https://pixinsight.com/doc/docs/XISF-1.0-spec/XISF-1.0-spec.html), the Extensible Image Serialization Format of PixInsight | Stable: 1.1.0 |
| [OpenFITS](https://github.com/astroformats/openfits) | [FITS 4.0](https://fits.gsfc.nasa.gov/fits_standard.html), the Flexible Image Transport System |  Stable: 1.0.0 |
| A SER library | SER, the video format of planetary and lunar capture | Planned |

## What they share

- **Conformance.** Each library follows its specification, and is tested against files written by other
  implementations.
- **Safety.** Sizes, offsets and counts are checked before they are used, within limits that the application can set,
  and the parsers are fuzzed.
- **Speed and threads.** No mutable global state: one file can be read from several threads at once, and built with
  oneTBB, decoding also runs in parallel within one call.
- **Compatible output.** Writers default to what every reader of the format understands; compression and checksums are
  opt-in.
- **Plain C++20.** Standard CMake, dependencies through `find_package`, on Linux, Windows and macOS.
- **Apache-2.0.**

## Contributing

Issues and pull requests are welcome in the repository of each library. Please report security problems privately,
through the "Report a vulnerability" button of its Security tab.
