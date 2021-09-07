# CLI Snippets 

These are list of linux snippets that has eased my job by automating few tasks that would have taken days manually but can be done in seconds with help of simple commands


## Find files that do not have a certain pattern. 

These will be useful in scenarios where we would find that a certain documentation or license to be included in all files are missed or to do a standard check for the source code.

    grep -irL 'pattern' $path

### Explaination

The grep command is used to match the patterns efficiently and effectively. 

* i for case insensitive
* r for recursively looping through file list
* L for suppressing normal output and print non matched files
* $path can be any path you might want to search in
* 'pattern' will be the pattern to find the patterns to be matched, this can be in regex or a normal string

## Remove special characters from multiple files. 

These will be useful in scenarios where we would want to remove characters from multiple files like the infamous ctrl m characters

    grep -rl pattern $path | xargs sed -i '...'

### Explaination

The grep command is used to match the files recursively and list the files. xargs takes the list of files and pass it to the sed command where we do inline conversion

* r for recursively looping through file list
* l for suppressing normal output and print matched files
* $path can be any path you might want to search in
* 'pattern' will be the pattern to find the patterns to be matched, this can be in regex or a normal string
* i to replace contents inline for sed