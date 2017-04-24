# cppreference2mshelp
cppreference.com html archive to microsoft help converter

## Prerequires:

1) Windows x64 (LOL, I'm mad)
2) php al least 5.6.1
3) digital certificate to sign cabs (unsigned cabs will not be installed)
4) cppreference.com offline archive (*Html book*) downloaded from this link: http://en.cppreference.com/w/Cppreference:Archives

## Ok, what's inside?

**compile_c.cmd** and **compile_cpp.cmd** - main command files that do the all job. Use **compile_c.cmd** for c documentation and **compile_cp.cmd** for c++ documentation. 
**compile_c_zip.ps1** and **compile_cpp_zip.ps1** - uses powershell to make zip files.
**config.txt** - config for a great tool *tidy*: http://www.html-tidy.org/ ( we need it to convert htmls to xhtmls and fix errors ).
**cppreference.msha** and **creference.msha** - config files for *Microsoft Help System*. Actually a headers for Help system, *Microsoft Help* will get the info from them to install the help packs.
**make_xhtmls.php** - ugly php preprocessor script that fixes and converts thousands of htmls from cppreference to xhtml and Microsoft Help format.
**makecab.exe** - tool to make a cab file for Microsoft Help System. Can be found in Microsoft SDK.
**signtool.exe** - tool to sign cab files. Can be found in Microsoft SDK.
**tidy.exe** and **tidy.dll** - tool to convert html to xhtml and fix many other problems. Can be downloaded here: http://www.html-tidy.org/ 

## Step-by-step instructions:

1) download [cppreference.com](http://en.cppreference.com/w/Cppreference:Archives) offline archive and unpack it. Only *Html book* format is acceptable.
2) download this repo and unpack it to the **reference** folder inside unpacked archive (from cppreference.com).
3) folders structure should be like this one:

![screenshot](https://github.com/crea7or/cppreference2mshelp/raw/master/folders.png)

Folders **common** and **en** is from archive from cppreference, all other folders is owned by script.

4) now you can start the scripts and build the documentation (200+ seconds for c++ documentation 4000 files and a lot less for c documentation).

5) In result you should have two new files in this folder: **cppreference.cab** and **creference.cab** - use them with appropriate **cppreference.msha** and **creference.msha** files to install created help files.

Enjoy!