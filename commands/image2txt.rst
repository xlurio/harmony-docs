image2txt
=========

============
Introduction
============

The ``image2txt`` command allow to extract the colors from an image and write them into a color palette file (see :ref:`file_specification`).

=======
Example
=======

Given the file ``colors.png`` with the following image:

.. image:: ../_static/images/image2txt-1.jpg

Let's generate a image with the color palette::

    $ harmony image2txt colors.png

And we generate a file ``colors.txt`` with the following content (see :ref:`file_specification`)::

    (221, 228, 236) Alice Blue
    (137, 144, 163) Manatee
    (155, 166, 188) Rock Blue
    (164, 172, 191) Echo Blue
    (169, 178, 193) Mischka
    ...

=========
Arguments
=========

.. program:: harmony sort

.. option:: colors-file

    The Harmony color palette file with the list of colors to be represented (see :ref:`file_specification`).


=======
Options
=======

.. option:: --help

    Display the options and information about the command;