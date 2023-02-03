.. _sort_command:

sort
====

============
Introduction
============

The ``sort`` command allow to sort a list of colors given a color palette file (see :ref:`file_specification`).

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

Which represent the following colors:

.. image:: ../_static/images/sort-1.png

Let's sort it using all the default values::

    $ harmony sort colors.txt

And we generate a file ``colors_hillbert.txt`` with the following content::

    RGB(84, 16, 13) Dark Red
    RGB(84, 62, 115) Violet
    #b52871 Dark Pink
    RGB(201, 118, 6) Orange
    #0f8fb3 Light Blue
    RGB(49, 6, 210) Dark Blue

Which represent the following colors:

.. image:: ../_static/images/sort-3.png


=========
Arguments
=========

.. program:: harmony sort

.. option:: colors-file

    The Harmony color palette file with the list of colors to be sorted (see :ref:`file_specification`).


=======
Options
=======

.. program:: harmony sort

.. option:: --sorting-algorithm <algorithm>, -a <algorithm>

    Default\: herbert. Determine which algorithm should be used to sort the colors:

    * rgb: Sort the colors based on their RGB values;
    * hsv: Sort the colors based on their HSV values;
    * hsl: Sort the colors based on their HSL values;
    * luminosity: Sort the colors based on their perceived luminosity;
    * step: Sort the colors based on their hue, luminosity and *value* splitting them in 8 steps and sorting them separately;
    * step-alternated: Same as step, but the luminosity step is alternated forward and backward, bringing a sensation of continuity;
    * hillbert: Sort the colors based on their proximity in Hillbert Curves calculated on top of the RGB values;

    .. versionchanged:: 0.4.2

        Added short name ``-a``.

    #######
    Example
    #######

    Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(49, 6, 210) Dark Blue
        #0f8fb3 Light Blue
        RGB(201, 118, 6) Orange
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(84, 16, 13) Dark Red

    Let's sort it with the ``hsl`` algorithm::

        $ harmony sort colors.txt -a hsl

    Which represent the following colors:

    .. image:: ../_static/images/sort-1.png

    And we generate a file ``colors_hsl.txt`` with the content::

        RGB(84, 16, 13) Dark Red
        RGB(201, 118, 6) Orange
        #0f8fb3 Light Blue
        RGB(49, 6, 210) Dark Blue
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink

    Which represent the following colors:

    .. image:: ../_static/images/sort-2.png


.. option:: --direction <direction>, -d <direction>

    Default\: forward. Determine if the colors will be sorted in its natural order or in reverse:
    
    * forward: the colors will be sorted in its natural order
    * backward: the colors will be sorted in reverse

    .. versionadded:: 0.2.0

        Added ``--direction`` option;

    .. versionchanged:: 0.4.2

        Added short name ``-d``.

    #######
    Example
    #######

    Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(49, 6, 210) Dark Blue
        #0f8fb3 Light Blue
        RGB(201, 118, 6) Orange
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(84, 16, 13) Dark Red

    Which represent the following colors:

    .. image:: ../_static/images/sort-1.png

    Let's sort it forward::

        $ harmony sort colors.txt

    And we generate a file ``colors_hillbert.txt`` with the following content::

        RGB(84, 16, 13) Dark Red
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(201, 118, 6) Orange
        #0f8fb3 Light Blue
        RGB(49, 6, 210) Dark Blue

    Which represent the following colors:

    .. image:: ../_static/images/sort-3.png

    Now, we will sort it backwards::

        $ harmony sort colors.txt -d backward

    And we generate a file ``colors_hillbert.txt`` with the following content::

        RGB(49, 6, 210) Dark Blue
        #0f8fb3 Light Blue
        RGB(201, 118, 6) Orange
        #b52871 Dark Pink
        RGB(84, 62, 115) Violet
        RGB(84, 16, 13) Dark Red

    Which represent the following colors:

    .. image:: ../_static/images/sort-4.png


.. option:: --color-format <format>, -f <format>

    Default\: input. Determine the format the colors are going to be written in the output file:

    * input: The output format will be the same as the input format;
    * rgb: The output for all colors will be in RGB format;
    * hexcode: The output for all colors will be in Hexcode format;
    * hsl: The output for all colors will be in HSL format;

    .. versionchanged:: 0.4.2

        Added short name ``-f``.

    .. versionchanged:: 1.0.0
        
        Added ``hsl`` format

    #######
    Example
    #######

    Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(49, 6, 210) Dark Blue
        #0f8fb3 Light Blue
        RGB(201, 118, 6) Orange
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(84, 16, 13) Dark Red

    Let's sort with the output color format set to ``input``::

        $ harmony sort colors.txt

    And we generate a file ``colors_hillbert.txt`` with the following content::

        RGB(84, 16, 13) Dark Red
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(201, 118, 6) Orange
        #0f8fb3 Light Blue
        RGB(49, 6, 210) Dark Blue

    Now we will sort with the output color format set to ``rgb``::

        $ harmony sort colors.txt -f rgb

    And we generate a file ``colors_hillbert.txt`` with the following content::

        RGB(84, 16, 13) Dark Red
        RGB(84, 62, 115) Violet
        RGB(181, 40, 113) Dark Pink
        RGB(201, 118, 6) Orange
        RGB(15, 143, 179) Light Blue
        RGB(49, 6, 210) Dark Blue

    Now we will sort with the output color format set to ``hsl``::

        $ harmony sort colors.txt -f hsl

    And we generate a file ``colors_hillbert.txt`` with the following content::

        HSL(2, 84%, 19%) Dark Red
        HSL(264, 46%, 34%) Violet
        HSL(328, 77%, 43%) Dark Pink
        HSL(34, 97%, 40%) Orange
        HSL(193, 91%, 38%) Light Blue
        HSL(252, 97%, 42%) Dark Blue


.. option:: --suffix <suffix>, -s <suffix>

    The suffix to be append to the file's name.

    .. versionchanged:: 0.4.2

        Added short name ``-s``.

    #######
    Example
    #######

    Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(49, 6, 210) Dark Blue
        #0f8fb3 Light Blue
        RGB(201, 118, 6) Orange
        RGB(84, 62, 115) Violet
        #b52871 Dark Pink
        RGB(84, 16, 13) Dark Red

    Let's sort with the suffix ``_example``::

        $ harmony sort colors.txt -s _example

    And the output file will be called ``colors_hillbert_example.txt``.


.. option:: --no-generate-color-names, -G
    
    Disables the color name generation for the unlabelled colors.

    .. versionadded:: 0.5.0
        
        Added ``--no-generate-color-names`` option

    #######
    Example
    #######

    Given the file ``colors.txt`` with the following content (see :ref:`file_specification`)::

        RGB(49, 6, 210)
        #0f8fb3
        RGB(201, 118, 6)
        RGB(84, 62, 115)
        #b52871
        RGB(84, 16, 13)

    Which represent the following colors:

    .. image:: ../_static/images/sort-1.png

    Now we will sort with the ``-G`` flag off::

        $ harmony sort colors.txt

    And we generate a file ``colors_hillbert.txt`` with the following content::

        RGB(84, 16, 13) Falu Red
        RGB(84, 62, 115) Meteorite
        #b52871 Deep Cerise
        RGB(201, 118, 6) Tenne (Tawny)
        #0f8fb3 Pacific Blue
        RGB(49, 6, 210) Medium Blue

    But if we sort with the ``-G`` flag on::

        $ harmony sort colors.txt -G

    We generate a file ``colors_hillbert.txt`` with the following content::

        RGB(84, 16, 13) 
        RGB(84, 62, 115) 
        #b52871 
        RGB(201, 118, 6) 
        #0f8fb3 
        RGB(49, 6, 210)


.. option:: --help

    Display the options and information about the command;