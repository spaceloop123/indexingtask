# Async indexing
### Task #1
[[pptx]](https://www.dropbox.com/s/87wf7nosd832sk3/Task%201.pptx?dl=0) [[repository]](https://github.com/Andrew414/indexingtask) [[russian]](https://github.com/Andrew414/indexingtask/blob/master/README.rus.md)

### Description
You need to write a program or script that can calculate hashes of blocks inside some file and save them to output file. The program should have [CLI](https://en.wikipedia.org/wiki/Command-line_interface) and accept the following parameters:

Path to exe|Path to file|Block size|Algorithm|Mode
-----------|------------|----------|---------|----
`C:\firsttask.exe`|`C:\Rogue-One.avi`|`1048576`|`md5`|`sync`

`Mode` argument is optional, the program should work if it's not passed.

Program should check input parameters and gracefully exit if something is wrong with them. If arguments are ok it should read `[filesize / blocksize]` blocks, calculate their hashes independently, and then save the list of calculated hashes to output file in the proper order.

###### Input parameters
Parameter|Possible options
---------|----------------
Path to file|Valid path. Program should exit if file doesn't exist or if it can't be read
Block size|Power of 2 (2^n), from 1024 to 1048576 (1KB to 1MB)
Algorithm|md5, sha1
Mode|sync, async (async should be applied if this parameter is not passed)


###### Output file
Output file's name should be same as input with suffix `.hashes_<algorithm>`. For example, for input file name `C:\abc.txt` and md5 algorithm output file will be `C:\abc.txt.hashes_md5`

Example of outputput (file contains 4 blocks)|
---------------------------------------------|
`3a37312509712d4e12d27240137ff377`|
`1b8677ea56b9e7139b4df2ce15b70826`|
`8148ddb015d5ab4d2ff57b4cd7355f7f`|
`7dc98705a83e4156ddc8888203e629af`|

###### Additional requirements
Program should be written using some common [**Codestyle**](https://en.wikipedia.org/wiki/Programming_style). If your chosen language has one main Codestyle, please use it, otherwise please select any suitable one and mention it in Pull Request.

Also, program's code should be covered with [**Unit Tests**](https://en.wikipedia.org/wiki/Unit_testing).

### Additional tasks
There are three additional tasks:
* Add performance measurement to your task
 * This is needed to compare the speed of hashing (working with CPU) and reading (working with Disk)
 * Performance stats should be printed to console and include four characteristics: Average speed of reading (MB/s), Average speed of hashing (MB/s), total time spent on reading (seconds), total time spent on hashing (seconds)
* Add CRC32 and SHA2 (SHA256) algorithms.
 * `crc32` and `sha2` should be another options for `algorithm` parameter
* Add GUI to your task
 * GUI should let you choose the file(s), block size, algorithm and mode, preferrably also show some progress and stats

### Github repository
[Github repository](https://github.com/Andrew414/indexingtask) consists of one main [`README.md`](https://github.com/Andrew414/indexingtask/blob/master/README.md) page and fourteen personal folders. You need to fork the repository and make changes in your personal folder only. All personal folders contain an empty `.gitignore` file that you need to fill in with your project's temp files. The rest of the files should be your code and project files.

### Passing the task
You can choose any programming language, IDE and framework(s) for implementing this task. If some uncommon configurations or installations are required, please provide some instructions for setting up the test environment. 

You can't use libraries or frameworks that do a very similar job that task requires. For example, you can use cryptographic libraries for hash algorithms implementations and some tools for simpler blocked file reading as well as some libraries for simpler work with threads, but can't use tools that can automatically split files into blocks, calculate hashes and dump them to file.

You should create a **pull request** from your forked repository. Your pull request should contain code, project files and informational files. You should not include build results and temp files.

### Score
You can earn up to **10 points** for this task.
- **4 points** for implementing the main task
- **3 points** for finishing in time
- **1 point** for implementing *sha2* and *crc32* hashing
- **1 point** for implementing *performance test* subtask
- **1 point** for implementing *GUI* subtask

### Time frames
You have four weeks (February 20 - March 20) to send the task. Time taken to fix some issues found during review is not counted.

### Good luck!