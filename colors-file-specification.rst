.. _file_specification:

Color Palette File Specification
================================

============
Introduction
============

Most of the commands of Harmony receives the colors through a special text file. this tutorial shows how to write colors in this file.


==========
The Colors
==========

To pass colors to the file, all you need to do is pass the hexcode, RGB or HSL format in to it. Every color must be in a separated line::

    RGB(49, 6, 210)
    #0f8fb3
    HSL(300, 11%, 6%)


RGB format must be written in the format ``RGB(X, X, X)`` being ``X`` the components red, green and blue as an integer from 0 to 255. The hexcode format must be in the format ``#XXXXXX`` or ``#XXX`` being ``X`` the components red, green and blue as hex digits. Lastly, the HSL format must be written int the format ``HSL(X, X%, X%)`` being  ``X`` the components hue as an integer from 0 to 365, and saturation and luminosity as integers from 0 to 100.

.. versionadded:: 0.1.0

    Created the Harmony Color Specification

.. versionchanged:: 1.0.0

    Changed RGB format to CSS RGB() function and added HSL format

======
Labels
======

Being to facilitate the reading or to generate files as `.clr` and `.ase`, you can add labels to the colors. For that just write it after the color spefication, separated by a whitespace::

    RGB(49, 6, 210) Dark Blue
    #0f8fb3 Light Blue
    RGB(201, 118, 6) Orange