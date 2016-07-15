# logHandler
A *very* simple logging system for java. No levels or anything fancy, this is to get initial effort logging underway when we start out a project.

# Usage
Usage is simple. First, initialize the log file:
```java
logPath = LogHandler.createLog(Instant.now(),
                logFolderLocation, 
                logFileName);
                ```
where logFolderLocation is the folder where we want the log, logFileName is the filename itself. The function returns a String of the complete address of the file. If no logFolderLocation and logFilename are given, default ones are chosen.

Typically, the filename will contain a timestamp. Instant.now() is ideal for this, but contains illegal characters, so logHandler includes the function cleanNow(Instant.now()), which returns a cleaned up string of the Instant.

```java
String logFileName = "log-" + cleanNow(Instant.now()) + ".log";
```

In order to log to an existing file, call the log function:

```java
LogHandler.log(Instant.now(), "Log anything that can go in a string!", logPath);
```
