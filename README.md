# Ruby CFF
## Robert Haines

A Ruby library for manipulating CITATION.cff files.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1184077.svg)](https://doi.org/10.5281/zenodo.1184077)
[![Gem Version](https://badge.fury.io/rb/cff.svg)](https://badge.fury.io/rb/cff)
[![Build Status](https://travis-ci.org/citation-file-format/ruby-cff.svg?branch=master)](https://travis-ci.org/citation-file-format/ruby-cff)
[![Maintainability](https://api.codeclimate.com/v1/badges/6bb4c661bfb4971260ba/maintainability)](https://codeclimate.com/github/citation-file-format/ruby-cff/maintainability)
[![Coverage Status](https://coveralls.io/repos/github/citation-file-format/ruby-cff/badge.svg)](https://coveralls.io/github/citation-file-format/ruby-cff)

### Synopsis

This library provides a Ruby interface to manipulate CITATION.cff files. The primary entry points are the Model and File classes.

See the [CITATION.cff documentation](https://citation-file-format.github.io/) for more details.

### Quick start

```ruby
cff = CFF::Model.new("Ruby CFF Library")
cff.version = CFF::VERSION
cff.date_released = Date.today
cff.authors << CFF::Person.new("Robert", "Haines")
cff.license = "Apache-2.0"
cff.keywords << "ruby" << "credit" << "citation"
cff.repository_artifact = "https://rubygems.org/gems/cff"

CFF::File.write("CITATION.cff", cff)
```

Will produce a file that looks something like this:

```
# This CITATION.cff file was created by ruby-cff (v 0.5.0).
# Gem: https://rubygems.org/gems/cff
# CFF: https://citation-file-format.github.io/

cff-version: 1.0.3
message: If you use this software in your work, please cite it using the following metadata
title: Ruby CFF Library
version: 0.3.0
date-released: 2018-03-04
license: Apache-2.0
repository-artifact: https://rubygems.org/gems/cff
authors:
- family-names: Haines
  given-names: Robert
keywords:
- ruby
- credit
- citation
```

### Library versions

Until this library reaches version 1.0.0 the API may be subject to breaking changes. When version 1.0.0 is released, then the principles of [semantic versioning](https://semver.org/) will be applied.

### Licence

[Apache 2.0](http://www.apache.org/licenses/). See LICENCE for details.
