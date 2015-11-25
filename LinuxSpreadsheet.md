##Linux Shell Spreadsheet

*Any code command with an underscore refers to a variable in the real situation*
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
1.`./_program > _test 2>&1` direct standard output of  program to test, also redirecting standard error to standard output. Then the standard error is also directed to test. **Note: the order of the stream cannot be swapped.**

`./_program < _test` gets the input from test.file

`./_program &> _test` a short way of saying redirecting both the standard output and standard error to test 

*This introduce a new way to create an empty file on Linux `> _NewFile` Other two ways including `touch _NewFile` and `cat > _NewFile`with CTRL-D*

2.For IO stream between commands and commands, use vertical bar "|" to create the pipe between two programs
 
 `./_program | program2`


###String handling

