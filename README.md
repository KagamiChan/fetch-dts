# fetch-dts

Download typings from inside npm packages

## Why you may need `fetch-dts`

Currently there're 2 major ways for package maintainers to provide TypeScript type decarations (typings, d.ts files)

- Published in [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) and released as a standalone package under `@types` scope,
- Bundled in package and defined in `package.json`.

Sometimes you may need a typing file without adding the package in dependencies or dev dependencies (yeah, such use cases do exist, at least for me). For the former way, it is OK because if the `@types` scope package exists, TypeScript will not complain. But the latter way we should pick the file out from the package. This tool is aimed to automate the process to save time.

## Installation

TBD

## How to

Microsoft's [types-publisher](https://github.com/Microsoft/types-publisher) provides [a list](https://typespublisher.blob.core.windows.net/typespublisher/data/search-index-min.json) for typings hosted in DefinitelyTyped, note that some `@types` scoped packages are just placeholders, and they are omitted from the list.

So the tool will do the following process

1. Check if the list contains the given package,
1. Resolve the package version, download and extract the tarball,
1. generate d.ts file.

### `fetch-dts.yml`

Since d.ts files itself have versions, `fetch-dts.yml` will record file versions. It's similar to `package.json`. But you won't be able to update this file from existing d.ts since the version info is lost.

### cli commands

TBD

## License

MIT
