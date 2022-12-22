# Class 3 Reading Note

### Read & Write Files in Python

A file is a contiguous set of bytes used to store data that is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. These byte files are then translated into binary 1 and 0 for easier processing by the computer.

- Header: metadata about the contents of the file (file name, size, type, and so on)
- Data: contents of the file as written by the creator or editor
- End of file (EOF): special character that indicates the end of the file

**File Paths**

- Folder Path: the file folder location on the file system where subsequent folders are separated by a backslash \ (Windows)
- File Name: the actual name of the file
- Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

.write(string) => This writes the string to the file.  
.writelines(seq) => This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).

**Exceptions in Python**

**Exception error** occurs whenever syntactically correct Python code results in an error.  
Use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.  
**Assertion Error Exception** occurs when a certain condition is met. If this condition turns out to be True, then the program can continue. But, if the condition turns out to be False, you can have the program throw an AssertionError exception.  
The **try** and **except** block in Python is used to catch and handle exceptions.

Reference [Read & Write Files in Python](https://realpython.com/read-write-files-python/)  
Reference [Exceptions in Python](https://realpython.com/python-exceptions/)  
Reference [Read & Write Files in Python - Companion Video](https://realpython.com/courses/reading-and-writing-files-python/)

[Back to Home](../../README.md)
