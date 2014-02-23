---
layout: post
title:  "Windows Batch Script to Write to a Daily Log File"
date:   2010-07-26 18:45:00
tags: batchscript windows
---

Here is a Windows batch script to append a passed line of text to the specified file (prepending the text with a date/time stamp).  The idea is to use it to capture your day's activities in a [daily log](http://lifehacker.com/5582372/use-a-daily-log-to-keep-yourself-focused-on-productivity) format. It's especially useful when combined with a tool like [Launchy](http://www.launchy.net/).

{% highlight text %}
@echo off
setlocal

set MYDOCSPATH=[replace]
set LOGSUBPATH=[replace]
set FILENAME=DailyLog
set FILEEXT=txt

:: Generate date/time stamp
for /F "tokens=1 delims=/ " %%G in ('echo %DATE%') do set WEEKDAY=%%G
for /F "tokens=2 delims=/ " %%G in ('echo %DATE%') do set MONTH=%%G
for /F "tokens=3 delims=/ " %%G in ('echo %DATE%') do set DAY=%%G
for /F "tokens=4 delims=/ " %%G in ('echo %DATE%') do set YEAR=%%G
set YMD=%YEAR%%MONTH%%DAY%
for /F "tokens=1 delims=:." %%G in ('echo %TIME%') do set HOUR=%%G
for /F "tokens=2 delims=:." %%G in ('echo %TIME%') do set MIN=%%G
for /F "tokens=3 delims=:." %%G in ('echo %TIME%') do set SEC=%%G
if %HOUR% LSS 10 set HOUR=0%HOUR%
set HMS=%HOUR%%MIN%%SEC%
set DATETIMESTAMP=%YMD%-%HMS%

set LOGFILE=%MYDOCSPATH%\%LOGSUBPATH%\%FILENAME%.%FILEEXT%
set MESSAGE=%WEEKDAY% %YEAR%-%MONTH%-%DAY% %HOUR%:%MIN%:%SEC% \\ %*
if "%*"=="" (
echo No log message provided.  Displaying contents of log file.
) else (
echo Writing log message: %*

echo %MESSAGE% &gt;&gt; "%LOGFILE%"
)
echo ----------------------------------------------------------------------
type "%LOGFILE%"
echo ----------------------------------------------------------------------
pause

endlocal
{% endhighlight %}
