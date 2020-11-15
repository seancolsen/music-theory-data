# Music Theory Data

This repository is a human-editable and machine-readable data source for names and details about many music theory entities including: scales, chords, intervals, and notes.

Most of the scale name data came from Francesco Balena's fantastic self-published PDF, [The Scale Omnibus](http://www.saxopedia.com/the-scale-omnibus/).

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

