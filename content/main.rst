.. warning:: Please note that at this time, this document is a work in progress that is not intended to be read by anyone other than its authors.

.. TODO: one section per tool or one section per usage ? -> per (concrete) usage ! should add a "Tools list" section at the beginning with links to following sections ?

Tools list
==========

- ``otool``

  - `Display the names and version numbers of the shared libraries that an object file uses`_

- ``install_name_tool``

  - `Changes the dynamic shared library install names in a Mach-O binary`_
  - Adds, changes or deletes the rpaths recorded in a Mach-O binary

Display the names and version numbers of the shared libraries that an object file uses
======================================================================================

::

    otool -L FILE

File can be an executable, a library or an object file.

Changes the dynamic shared library install names in a Mach-O binary
===================================================================

::

    install_name_tool -change "OLD_PATH" "NEW_PATH" FILE

Example::

    install_name_tool -change "@rpath/./bar.dylib" "/Users/john/bar.dylib" foo.so
