##Linux Shell Spreadsheet

###Run Options
1.`./_program &`  Run silently, always in background running

2.`CTRL-C` sending `SIGNAL_INT` to the program

3.`CTRL-D` sending EOF to the standard input. This is especially useful when we want to end the input stream

4.`CTRL-Z` sending `SIGNAL_SUSPEND` to the program.The program itself will be hung up. The suspending program can be found at `jobs`. 

&nbsp;&nbsp;&nbsp;&nbsp;`fg %_jobID` move the background job to front. Automatically resume suspending jobs

&nbsp;&nbsp;&nbsp;&nbsp;`bg %_jobID` resume the job. However the job is running in the background 

5.`kill _pid` The process will end according to the signal handling of SIGNAL_INT, This may involves the saving and safely quitting the program. If no responses, try `kill -9 _pid` which forces the program to stop.


###File Manipulation
`cd -` Returns to the previous directory

###IO redirect
`./program > test.file 2>` 

