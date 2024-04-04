Description
===========

Perl script for listing, unpacking, viewing .mht / .mhtml files (MIME-encoded
HTML archives).

Based on [unmht](http://www.volkerschatz.com/unix/uware/unmht.html).

Usage
=====

`mhtml-tool [ -l | --list | -o <dir/ or name> | --output <dir/ or name> ] <MHT file>`

By default, unpack an MHTML archive (an archive type saved by some browsers)
to the current directory.  The first HTML file in the archive is taken for the
primary web page, and all other contained files are written to a directory
named after that HTML file.

The `-e` option provides a way to use `lynx` (or other text browser) on a
temporary copy of the archive.

Options:

 * -e, --exec    Unpack in temporary directory, run program there.
 * -l, --list    List archive contents (filename, MIME-type, size, URL)
 * -o, --output  Unpack to directory *&lt;dir/&gt;* or to file *&lt;name&gt;*.html

The primary web page is written to the output directory (the current directory
by default), and the requisites are written to a subdirectory named after the
primary HTML file name without extension, with "_files" appended.

URLs in all HTML files referring to requisites are rewritten to point to the
saved files.
