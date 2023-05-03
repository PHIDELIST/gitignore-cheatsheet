|Pattern    |Explanation/Matches                              |Examples|
|-----------|-------------------------------------------------|--------|
|*.env      |All files with extension of .env will be ignored |workspace.env, example.env|
|**/envs    |All file in first level ,second level and third level in the envs directory will be ignored|````envs/example.txt, envs/jitu/week1.logs, envs/jitu/cohort1/week1.logs```|
|**/envs/debug.log| Double asterisk will match files based on their name and the name of their parent directories and all will be ignored| ```envs/debug.log , build/envs/debug.log ``` but not ```envs/build/debug.log```|

