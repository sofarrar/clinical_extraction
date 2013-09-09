java -jar MedExtractor_v1.jar [0] [1] [2] [3] 
Argument 0 requires to be a file or a directory. If reading the input as a buffer, it will need to be written to a file before being passed to the extraction program. MM, CTAKES both operate on files, not buffered readers.
Arguments:
[0] : Clinical note location directory or file
[1] : ouput directory for parse files
[2] : location of root ctakes directory
[3] : location of root metamap directory

Temp directory is created out of user directory home/tmp and is used for creating a xml ctakes configuration file. 
Testing is still needed for cTAKES to properly run from command line. bat (windows) are being used and in production these will need to be changed to sh.
Both archive and runnable jar files are included in this code upload. (9-8-2013)