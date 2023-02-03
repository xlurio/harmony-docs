txt2clr
=======

============
Introduction
============

Command to convert a given color palette file (see :ref:`file_specification`) to Apple ``.clr`` format.

.. versionadded:: 0.4.0

    Created the command with the name ``txt2clr``


=======
Example
=======

Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

    RGB(49, 6, 210) Dark Blue
    #0f8fb3 Light Blue
    RGB(201, 118, 6) Orange
    RGB(84, 62, 115) Violet
    #b52871 Dark Pink
    RGB(84, 16, 13) Dark Red


All we need to do is run the following command::

    $ harmony txt2clr colors.txt


And we have a ``colors.clr`` in the MacOS CLR format.

=========
Arguments
=========

.. program:: harmony txt2clr

.. option:: colors-file

    The Harmony color palette file (see :ref:`file_specification`) to be converted to ``.clr`` format.


=======
Options
=======

.. program:: harmony txt2clr

.. option:: --no-generate-color-names, -G
    
    Disables the color name generation for the unlabelled colors. Better demonstrated on :ref:`sort_command`.

    .. versionadded:: 0.5.0
        
        Added ``--no-generate-color-names`` option


.. option:: --help

    Display the options and information about the command;