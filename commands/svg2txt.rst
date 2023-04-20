svg2txt
=========

============
Introduction
============

The ``svg2txt`` command allow to extract the colors from an SVG file and write them into a color palette file (see :ref:`file_specification`).

    .. versionadded:: 1.0.0

        Added command ``svg2txt``

=======
Example
=======

Given the file ``colors.svg`` with the following image:

.. image:: ../_static/images/svg2txt-1.svg

Let's generate a harmony file (see :ref:`file_specification`) with the color palette::

    $ harmony svg2txt colors.svg

And we generate a file ``colors.txt`` with the following content (see :ref:`file_specification`)::

    RGB(221, 228, 236) Alice Blue
    RGB(137, 144, 163) Manatee
    RGB(155, 166, 188) Rock Blue
    RGB(164, 172, 191) Echo Blue
    RGB(169, 178, 193) Mischka
    ...

=========
Arguments
=========

.. program:: harmony svg2txt

.. option:: colors-file

    An SVG file or a directory with SVG files to extract colors (see :ref:`file_specification`).


=======
Options
=======

.. option:: --color-format <format>, -f <format>

    Default\: input. Determine the format the colors are going to be written in the output file:

    * input: The output format will be the same as the input format;
    * rgb: The output for all colors will be in RGB format;
    * hexcode: The output for all colors will be in Hexcode format;
    * hsl: The output for all colors will be in HSL format;

    .. versionadded:: 1.0.0

        Added ``--color-format`` option to ``svg2txt``

    #######
    Example
    #######

    Given the file ``colors.svg`` with the following image:

    .. image:: ../_static/images/svg2txt-1.svg

    Let's generate a harmony file (see :ref:`file_specification`) with the output color format set to ``rgb``::

        $ harmony svg2txt colors.svg -f rgb

    And we generate a file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(221, 228, 236) Alice Blue
        RGB(137, 144, 163) Manatee
        RGB(155, 166, 188) Rock Blue
        RGB(164, 172, 191) Echo Blue
        RGB(169, 178, 193) Mischka
        ...

    Now let's generate a harmony file (see :ref:`file_specification`) the output color format set to ``hexcode``::

        $ harmony svg2txt colors.svg -f hexcode

    And we generate a file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        #dde4ec Alice Blue
        #8990a3 Manatee
        #9ba6bc Rock Blue
        #a4acbf Echo Blue
        #a9b2c1 Mischka
        ...

    Now let's generate a harmony file (see :ref:`file_specification`) the output color format set to ``hsl``::

        $ harmony svg2txt colors.svg -f hsl

    And we generate a file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        HSL(212, 6%, 89%) Alice Blue
        HSL(223, 15%, 58%) Manatee
        HSL(220, 17%, 67%) Rock Blue
        HSL(222, 14%, 69%) Echo Blue
        HSL(217, 12%, 70%) Mischka
        ...


.. option:: --recursively, -r

    Default\: ``False``. If a directory is passed, ``Harmony`` is going to read every image recursively inside the directory passed.


.. option:: --help

    Display the options and information about the command;