Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes, first install Python on your local computer, and then download the TorahBibleCodes GitHub Repo ZIP file or clone the GitHub repo to your local computer.

.. code-block:: console

   git clone https://github.com/TorahBibleCodes/TorahBibleCodes.git

WARNING
----------------

There are criminal squatters who are infringing on our TorahBibleCodes international copyright. We are not associated with any current PyPi projects.  DO NOT PIP INSTALL - YOU DO SO AT YOUR OWN RISK OF VIRUSES AND MALICIOUS CODE BY CRIMINAL SQUATTERS WHO ARE SQUATTING, INFRINGING, AND VIOLATING THE TORAHBIBLECODES COPYRIGHT AT PYPI.ORG: https://pypi.org/.

.. code-block:: console

   pip install TorahBibleCodes ## DANGER ## DO NOT PIP INSTALL ## INSTALL AT YOUR OWN RISK! 


Run the App
----------------

After installing Python as well as cloning the TorahBibleCodes GitHub Repo to your local computer:

Navigate to the local folder to where you have cloned TorahBibleCodes.

Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices.

Activate your ``ipython`` interactive python development environment by typing ``ipython`` at your CLI prompt.

After your IPython development environment has been activated in the CLI Window, type ``%run p.py`` at the IPython command prompt.

You will be prompted to select a text from the Hebrew Bible via the :py:func:`fn_GetUserInput` function.


For example::

   C:\TorahBibleCodes> ipython
   
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

Equidistant Letter Sequences (ELSs)
----------------

The essential objects in TorahBibleCodes are native Python data objects (i.e. strings, lists, tuples, and dictionaries).

For any text chosen (e.g. Genesis, Exodus, Leviticus, Numbers, Deuteronomy, or all five (5) together, or all twenty-one (21) books of the Prophets, or all thirteen (13) books of the Writings, or all thirty-nine (39) books of the entire Hebrew Bible), the text is parsed and a Python dictionary D (and DS) is created that allows one to access each verse by 3-digit Tuple Key (Book, Chapter, Verse). After choosing the text(s) to be searched, a Python dictionary D (and DS) is created to contain each verse - accessible by 3-digit Tuple Key.

D Object - Dictionary of Verses (with No Spaces), accessible as data with a 3-digit Tuple Key

``D`` Object: Dictionary of Verses Object ::

   D[1,1,1] --> GENESIS 1:1 - 1st Book, 1st Chapter, 1st Verse
   D[1,1,2] --> GENESIS 1:2 - 1st Book, 1st Chapter, 2nd Verse
   D[1,1,3] --> GENESIS 1:3 - 1st Book, 1st Chapter, 3rd Verse



Data Objects (and derivative Data Objects) with Info for Each Letter in Text:

Custom Letter Objects (LO)

Custom Equidistant Letter Objects (ELSO)

Custom Global Search Object (GSO)

These Python data objects are subsequently incorporated with a custom Global Search Object :py:func:`GSO`::

   gso = GSO()


``gso.S``
``gso.D``
``gso.DS``
``gso.DL``
``gso.D5``
``gso.D5K``

you can use the Global Search Object (gso)'s ``gso.Letters`` property:


