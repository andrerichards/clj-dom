# Change Log
All notable changes to this project will be documented in this file. This change log follows the conventions of [keepachangelog.com](http://keepachangelog.com/).


## 1.3.0
### Added

- `indent-str` : Emit element as indented (pretty printed) XML string

## 1.2.0
### Added

- `emit-str` : Emit element as XML string

### Fixed

- NullPointerException in `get-value`

## 1.1.0
### Added

- `get-value` now supports namespaces

## 1.0.0
### Added

- `parse-str->Document` : Parse xml string into JDOM Document
- `parse-str` :  Parse xml string into JDOM Document and return the root element
- `find-first` : Return the first element at the XPath
- `find-all` : Return collection of elements at the XPath
- `get-value` : Return the value at the XPath as a String, regardless of whether the XPath points to a element or attribute


