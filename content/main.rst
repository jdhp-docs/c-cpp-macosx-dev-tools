.. warning:: Please note that at this time, this document is a work in progress that is not intended to be read by anyone other than its authors.

.. TODO: one section per tool or one section per usage ? -> per (concrete) usage ! should add a "Tools list" section at the beginning with links to following sections ?

.. TODO: as(1), ar(1), cc(1), nm(1), otool(1) lipo(1), arch(3), dyld(3), Mach-O(5), strip(1), rebase(1), stab(5), nlist(3), install_name_tool(1), dyld(1), libtool(1), dyldinfo(1), 

Tools list
==========

- ``install_name_tool``

  - `Changes the dynamic shared library path in a Mach-O binary`_
  - Adds, changes or deletes the rpaths recorded in a Mach-O binary

- ``nm``

- ``otool``

  - `Display the shared libraries used by an object file`_

Display the shared libraries used by an object file
===================================================

::

    otool -L FILE

File can be an executable, a library or an object file.

Changes the dynamic shared library path in a Mach-O binary
==========================================================

::

    install_name_tool -change "OLD_PATH" "NEW_PATH" FILE

Example::

    install_name_tool -change "@rpath/./bar.dylib" "/Users/john/bar.dylib" foo.so
