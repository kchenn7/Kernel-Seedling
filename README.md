# A Kernel Seedling
proc_count.c creates a /proc/count file and prints the number of processes 
running on the kernel to the file.

## Building
```shell
make #this command compiles the modules needed for proc_count
```

## Running
```shell
sudo insmod proc_count.ko #inserts kernel module and runs the program
cat /proc/count #prints the result from /proc/count
```
177 is the result from cat /proc/count

## Cleaning Up
```shell
make clean #removes all created files from previous make, if there aren't any then it returns error
sudo rmmod proc_count.ko #removes inserted kernel module, if there isn't then it returns error
```

## Testing
```python
python -m unittest
```
I used python -m unittest after cleaning up everything previously generated.
output:
cs111% python -m unittest
...
----------------------------------------------------------------------
Ran 3 tests in 3.764s

OK

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
Kernel Release version: Linux 5.14.8-arch1-1. I used uname -r specifically to find the kernel version. 
-r -s -v provides more information.