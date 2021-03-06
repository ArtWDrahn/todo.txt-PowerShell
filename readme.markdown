TODO.TXT for PowerShell
===============================

A simple PowerShell module for managing your todo.txt file.

The goal of this project is to provide a version of the [todo.txt CLI](https://github.com/ginatrapani/todo.txt-cli) for Windows PowerShell. 
Sub-goals include:

1. Providing full compatibility between todo.txt files managed by this project and by the original todo.txt CLI and the Android and iOS versions. Users should be able to move seamlessly between either version.
2. Providing (as closely as possible) the same command interface so that users of both versions can switch back and forth easily. 
3. Allowing PowerShell users to take advantage of PowerShell's affinity for .NET objects.

Requirements
------------

* PowerShell 2.04
* .NET Framework 3.5 or higher

Dependencies
------------

* [TodotxtLib.Net](https://github.com/hartez/todotxtlib.net) 

Installation
------------

Download and extract the files; open up PowerShell in that directory and run the 'deploy.ps1' script. This will build and deploy the module to the appropriate folder (usually 'C:\\Users\\username\\Documents\\WindowsPowerShell\\Modules\\todo', though you can change this by passing in a different path as the first argument to 'deploy.ps1').

After the deployment script runs, you'll need to restart PowerShell. 

You can manually import the module using 'import-module todo', or you can add it your PowerShell profile so it's always available when you start PowerShell. Just add the following line to your profile.ps1 file:

    Import-Module todo

You'll also want to set the location of your todo.txt and done.txt files. If you use Dropbox to keep them synced up, the lines you'll add to profile.ps1 look something like this:

    Set-Variable -name TODO_FILE -value 'C:\Users\username\Dropbox\todo\todo.txt'
    Set-Variable -name DONE_FILE -value 'C:\Users\username\Dropbox\todo\done.txt'

And you can alias the function 'ToDo' to 't' to save some typing, if you'd like:

    Set-Alias -name t -value todo

Your profile.ps1 file is typically located in C:\Users\username\Documents\WindowsPowerShell

Disclaimer
----------

While the goal is interoperability with todo.txt files managed by other implementations, not all features of the sh version of the CLI have been implemented yet, and some features haven't been tested against todo.txt files created by other tools. So for the time being, use at your own risk.