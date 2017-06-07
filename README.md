# archive/ar

Go library for reading/writing [ar files](https://en.wikipedia.org/wiki/Ar_(Unix))

From Wikipedia;
> ar is generally used only to create and update static library files that the
> link editor or linker uses and for generating .deb packages for the Debian
> family; it can be used to create archives for any purpose, but has been
> largely replaced by tar for purposes other than static libraries.

ar archives are the simplest format that stratifies the following criteria;
 * Is an existing standard which has tools which ship on standard Linux
   systems.
 * Requires no escaping / processing of file contents.
 * Header can be written without needing to understand the whole file.
 * Extremely fast to process / generate.

Other formats which were consider before selecting the ar format;
 * tar
 * zip
 * cpio
 * rar
 * Something protobuf based.

This ar format is ~5 times faster than the archive/tar equivalent which ships
with go 1.5 (newer Go versions might be faster).

There are a couple of drawbacks;
 * The ar format doesn't support special files or symlinks.
 * The Linux ar tool don't extract with directory paths (list fine).

This library only supports the
[BSD variant](https://en.wikipedia.org/wiki/Ar_(Unix)#BSD_variant)
for long file names.

# TODO

 - [ ] Actually check this package can be used.
 - [ ] Improve the test suite.
 - [ ] Add some benchmarks.
 - [ ] Add Travis CI.
 - [ ] Add support for other variants.
 - [ ] Add a "artool" which allows you to test the ar commands for creation /
       extraction.
 - [ ] Full support the archive interfaces.
