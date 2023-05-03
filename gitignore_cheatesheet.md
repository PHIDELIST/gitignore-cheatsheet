|Pattern    |Explanation/Matches                              |Examples|
|-----------|-------------------------------------------------|--------|
|*.env      |All files with extension of .env will be ignored |```workspace.env```, ```example.env```|
|**/ec2s    |All file in first level ,second level and third level in the ec2s directory will be ignored|```ec2s/example.txt, ec2s/jitu/week1.log, ec2s/jitu/cohort1/week1.log```|
|**/ec2s/debug.log| Double asterisk will match files based on their name and the name of their parent directories and all will be ignored| ```ec2s/debug.log , build/ec2s/debug.log ``` but not ```ec2s/build/debug.log```|
|.env !important.log|If a file matches a pattern and also matches a negating pattern defined later in the file, it will not be ignored|```ec2.env``` ```gitpod.env``` but ```important.env``` and ```ec2s/important.env``` will not be ignored|
|*.env !important/*.env trace.*| The parttterns defined after a negating pattern will re-ignore any previously negated files|```debug.env``` ```important/trace.env``` while ```important/debug.env``` will not be ignored|
|/debug.env| prepending a slash matches files only in the root repository while others are not ignored| ```debug.env``` bot not ```ec2s/debug.env```|
|debug?.env| A question mark matches exactly one character while others with two character are not ignored|```debugk.env``` ```debug5.env``` but not ```debug45.env```|
|debug[0-9].env| square brackets can also be used to match a single character from a specified range, All file file single character within the range will be ignored| ```debugk.env``` but not ```debug10.env``` |
|debug[01].env| Square brackets matches a single character from the specified set| ```debug0.env``` ```debug1.env``` but not ```debug2.env``` or ```debug01.env```|
|debug[!01].env| An exclamation mark can be used to match any character except ane from the specified set| ```debug2.env``` but not ```debug0.log``` ```debug1.env``` ```debug01.env```|
|debug[a-z].env| This ranges can be numeric or alphanumeric, All file within the range will be ignored|```debug.enva``` ```debug.envk``` but not ```debgu1.env```|
|ec2s     |If pattern is not appended by a slash the pattern will match bot files and the content of the directories with that name| Matches on the left, both directories and files named ec2s will be ignored ```ec2s``` ```ec2s/userdata.bat```|
|ec2s/ |Appending a slash indicates the pattern is a directory. The entire content of any directory in the repository matching name including all of its files and subdirectories are ignored| ```ec2s/debug.log``` ```ec2s/latest/logs.txt```|
|ec2s/**/data.log | A double asterisk matches zero or more directories containing the file to be ignored| ```ec2s/data.log``` ```ec2s/os/data.log``` ```ec2s/os/runtime/data.log```|
|ec2s/*time/debug.log| Wildcards can be used in directory to indicate files that will be ignored by the gitignore| ```ec2s/sec/debug.log``` ```ec2s/microsec/debug.log``` but not ```ec2s/runtime/debug.log```|
|ec2s/debug.log|Patterns specifying a file in a particular directory are relative to the repository root, All file with the defined pattern relative to the root will be ignored| ```ecs/debug.log``` but not  ```debug.log``` ```docker/ec2s/debug.log```|


