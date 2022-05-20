# Music Theory Data

This repository is a human-editable and machine-readable data source for names and details about many music theory entities including: scales, chords, intervals, and notes.

Most of the scale name data came from Francesco Balena's fantastic self-published PDF, [The Scale Omnibus](http://www.saxopedia.com/the-scale-omnibus/).

## Goals of this project

* Data should be human editable data in text form.
* Data should be machine parsable.
* Data should be as [normalized](https://en.wikipedia.org/wiki/Database_normalization) as possible. This means we don't store anything that can be computed. For example, if you want to see a list of the modes of a given scale, you'll need to compute that yourself or find a library that does it for you.

## How to use this data

1. Import the code into your project.
    * If your project uses `npm`, then you can install the [music-theory-data](https://www.npmjs.com/package/music-theory-data) package.
    * If your project uses a different package manager (e.g. composer, pip, etc.), then feel free to open an issue here requesting that I create a package for it within that platform.
    * Alternatively, you can import this code using a git submodule, or just copy it directly if you're not concerned with carrying forward subsequent updates made to this data.
1. Find and install a [YAML parser](https://yaml.org/), and use it to extract structured data from the appropriate YAML files within the project.

## How to encode and decode binary values for scales and chords

Basics:

* For equal tempered octave-repeating interval sets (i.e. most scales and chords), this project identifies the set with one number to represent the state of all intervals as being included or excluded.
* You'll see this number stored in decimal format within the `binary` field of scales and chords.
* In binary form, the very last digit is the tonal center. Then the second to last digit is the minor second. And so on.
* When converted to decimal form, the number seems somewhat arbitrary, but serves as an easy way to uniquely identify interval sets.

Examples:

| Scale       | binary representation | Pitch class set | 
| --          | --                    | --              |
| Major Scale | `0b101010110101` = `2741` | {0, 2, 4, 5, 7, 9, 11}
| Tonal Center | `0b000000000001` = `1` | {0}
| Chromatic Scale | `0b111111111111` = `4095` | {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11}

Code:

* [Here are some simple functions *(in TypeScript)*](https://github.com/seancolsen/octave-compass/blob/2aa8b6cc15f7ba5240656826b3a773a816320df9/src/Utils/Music/IntervalSetBinary.ts) to encode and decode this binary representation from an array of interval ordinals (like a pitch set class).

## What about not octave-repeating scales and chords?

This project doesn't yet contain any data for such scales, but contributions to add such data would be welcome! Please discuss in an issue first, since we would need to devise a new schema to store such data.

## What about just intonation?

This is still a work in progress. Please help if you have time! Let's chat in an issue first to agree upon a schema.

## How to help improve this data

* Open issues for problems you notice but don't have the time or knowledge to fix.
* Open pull requests for edits.

## Versioning

This repository uses [Semantic Versioning](https://semver.org/).

* The major version increments when the yaml schema changes in a backwards incompatible manner.
* The minor version increments when new data is added.
* The patch version increments when typos are fixed or source code formatting changes are made.

## Style guidelines

1. Use *Title Case* for names.
1. Use unicode sharp and flat characters (`♯`, `𝄪`, `♭`, `𝄫`) instead of ASCII characters `#` and `b`.
1. Separate top-level entries with an empty line. Don't use empty lines elsewhere.
1. When multiple names exist for an entity, list the primary name first. Which name is primary? The answer is somewhat subjective! But the goal is to choose the name that people throughout the English-speaking world would most commonly use to describe that entity.

## License

This data is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International
](https://creativecommons.org/licenses/by-sa/4.0/) license.

## Projects using this data

* [Octave Compass](https://github.com/seancolsen/octave-compass)
* *(Add your project here by [editing this file](https://github.com/seancolsen/music-theory-data/edit/master/README.md) and submitting a pull request.)*

