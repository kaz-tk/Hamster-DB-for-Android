
@echo off

if [%JDK%] == [] goto l1
goto start
:l1
set JDK=%JAVA_HOME%
if [%JDK%] == [] goto nojdk

:nojdk
echo Neither JDK nor JAVA_HOME is set, exiting
goto end

:error1
echo Compilation failed, exiting
goto end

:start
for %%F in (Db1 Env3) do (
    echo Compiling %%F.java...
    %JDK%\bin\javac -cp .;..\java %%F.java
    if errorlevel 1 goto error1
    echo Running %%F:
    %JDK%\bin\java -cp .;..\java\hamsterdb-0.0.2.jar %%F
    if errorlevel 1 goto error1
)

echo Done!
goto end

:end
