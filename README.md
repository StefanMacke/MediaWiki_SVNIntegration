# What can this extension do?
This extension adds the following custom tags which allow an integration of files from Subversion repositories into the wiki: 

* `SVNPrintFile`: Prints the contents of the given file using GeSHi for syntax highlighting if existent. 
* `SVNFileInfo`: Prints some information about the given file (e.g. name, path, last author, last revision message etc.).
* `SVNFileHistory`: Prints the revision history for the given file.
* `SVNTodo`: Prints a list of TODO/FIXME/XXX comment tags found in the given file.

# Usage

Some examples:

    <svnFileInfo username="user" password="pass">http://svn.example.com/File.php</svnFileInfo>
    <svnPrintFile revision="1" filetype="ini">http://svn.example.com/File.txt</svnPrintFile>
    <svnFileHistory>http://svn.example.com/File.php</svnFileHistory>
    <svnFileHistory r="103:HEAD">http://svn.example.com/File.php</svnFileHistory>

# Screenshots

* See the `svnFileInfo` tag in action: http://f.macke.it/SVNIntegrationExample1
* See the `svnTodo` tag in action: http://f.macke.it/SVNIntegrationExample2

# Prerequisites

* **MediaWiki >= 1.11** due to use of function `wfLoadExtensionMessages`.
* [VersionControl_SVN](http://pear.php.net/package/VersionControl_SVN "VersionControl_SVN") PEAR package must be installed to be able to use this extension.
* You **need to apply the patch** from `Info.php.patch` to `VersionControl/SVN/Info.php` to get this extension to work.
* If you would like to get the file output syntax highlighted you also need the [GeSHiHighlight](http://www.mediawiki.org/wiki/Extension:GeSHiHighlight "GeSHiHighlight") extension for MediaWiki.

# Installation

* Extract the files from the archive to `extensions/SVNIntegration`.
* Configure some needed values in `SVNIntegration.setup.php`.
* Insert the following line into your `LocalSettings.php` (behind GeSHi inclusion if existent):

        include("extensions/SVNIntegration/SVNIntegration.setup.php");

* (optional) Insert the following line into your `main.css`:

        @import "/extensions/SVNIntegration/SVNIntegration.css";
