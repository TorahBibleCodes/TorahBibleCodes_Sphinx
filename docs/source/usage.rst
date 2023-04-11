Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes, first install it on your local computer by downloading the ZIP file or cloning the GitHub repo:

.. code-block:: console

   git clone https://github.com/TorahBibleCodes/TorahBibleCodes.git

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the Global Search Object (gso)'s ``gso.Letters`` property:

.. autofunction:: gso.Letters

Activate your ``ipython`` interactive python development environment by typing ``"ipython"`` at your Python command prompt.

Otherwise, :py:func:`gso.Letters` will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> ipython

In [1]: %run p.py

WITHIN FUNCTION:  BEGIN FUNCTION #1 - GET USER INPUT; CHOOSE TEXT TO SEARCH

Please select text to search:

1 - Genesis
2 - Exodus
3 - Leviticus
4 - Numbers
5 - Deuteronomy
6 - Joshua
7 - Judges
8 - I Samuel
9 - II Samuel
10 - I Kings
11 - II Kings
12 - Isaiah
13 - Jeremiah
14 - Ezekiel
15 - Hosea
16 - Joel
17 - Amos
18 - Obadiah
19 - Jonah
20 - Micah
21 - Nahum
22 - Habakkuk
23 - Zephaniah
24 - Haggai
25 - Zechariah
26 - Malachi
27 - Psalms
28 - Proverbs
29 - Job
30 - Song of Songs
31 - Ruth
32 - Lamentations
33 - Ecclesiastes
34 - Esther
35 - Daniel
36 - Ezra
37 - Nehemiah
38 - I Chronicles
39 - II Chronicles
40 - Pentateuch (Torah)
41 - Prophets (Nevi'im)
42 - Writings (K'tuvim)
43 - Hebrew Bible (Tanach)


Please select text to search:

