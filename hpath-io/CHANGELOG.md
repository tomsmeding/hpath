# Revision history for hpath-io

## 0.11.0 -- 2020-01-18

* `writeFile` not allows to set file mode and create file if it does not exist (this broke API)
* added various new functions:
	* createDirIfMissing
	* writeFileL (for lazy bytestring)
	* isReadable
	* isExecutable
	* getModificationTime
	* setModificationTime
	* setModificationTimeHiRes
	* getDirsFiles' (returns filenames instead of paths)
	* withRawFilePath
	* withHandle

## 0.10.1 -- 2020-01-13

* Move file check functions to HPath.IO
* Add 'doesExist'
* Exception handling of `doesExist`, `doesFileExist`, `doesDirectoryExist` has changed: only eNOENT is catched
* Exception handling of `isWritable` has changed: just a wrapper around `access` now
* switch exception handling to `safe-exceptions`
* Redo file reading API (readFileEOF dropped and now using streamly under the hood, added `readFileStream`)


## 0.10.0 -- 2020-01-04

* First version. Split from 'hpath', contains only the IO parts.
* Now uses streamly for 'copyFile'
* Fixed tmpdir in hspec