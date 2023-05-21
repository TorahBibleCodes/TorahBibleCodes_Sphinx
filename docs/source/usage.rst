Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes, first dowload and install Python on your local computer:

DOWNLOAD and INSTALL PYTHON: https://www.python.org/downloads/

After installing Python, then 'pip install' ``ipython``::

Install ``ipython``

.. code-block:: console

   pip install ipython
   
and then download the TorahBibleCodes GitHub Repo ZIP file or clone the GitHub repo to your local computer.

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



Program Concepts: Objects - D (DS), DL, D5, D5K, L (LLL), S (SSS), N (NW), W (DW), ListOfWords, NW4ELS, W4ELS (DW4ELS);
----------------

The essential objects in TorahBibleCodes are native Python data objects (i.e. strings, lists, tuples, and dictionaries).

For any text chosen (e.g. Genesis, Exodus, Leviticus, Numbers, Deuteronomy, or all five (5) together, or all twenty-one (21) books of the Prophets, or all thirteen (13) books of the Writings, or all thirty-nine (39) books of the entire Hebrew Bible), the text is parsed and a Python dictionary ``D`` Object (and ``DS`` Object) is created that allows one to access each verse by 3-digit Tuple Key (Book, Chapter, Verse). After choosing the text(s) to be searched, a Python dictionary D (and DS) is created to contain each verse - accessible by 3-digit Tuple Key.

Each verse (and letter) of the thirty-nine (39) books of the Hebrew Bible is accessible via the Python dictionary ``D`` (or ``DS``) with a unique 3-digit Tuple Key as per following examples:

``D`` Object - Dictionary of Verses (with No Spaces), accessible as data with a 3-digit Tuple Key

``D`` Object: Dictionary of Verses Object ::

   D[1,1,1] --> GENESIS 1:1 - 1st Book, 1st Chapter, 1st Verse
   D[1,1,2] --> GENESIS 1:2 - 1st Book, 1st Chapter, 2nd Verse
   D[1,1,3] --> GENESIS 1:3 - 1st Book, 1st Chapter, 3rd Verse

   D[1,1,1] = GENESIS 1:1
   D[1,1,7] = GENESIS 1:7
   D[1,50,26] = GENESIS 50:26
   D[2,1,1] = EXODUS 1:1
   D[2,40,38] = EXODUS 40:38
   D[3,1,1] = LEVITICUS 1:1
   D[3,27,34] = LEVITICUS 27:34
   D[4,1,1] = NUMBERS 1:1
   D[4,36,13] = NUMBERS 36:13
   D[5,1,1] = DEUTERONOMY 1:1
   D[5,34,12] = DEUTERONOMY 34:12
   
   ((1, 1, 1), 'בראשיתבראאלהיםאתהשמיםואתהארץ')
   ((1, 1, 2), 'והארץהיתהתהוובהווחשךעלפניתהוםורוחאלהיםמרחפתעלפניהמים')
   ((1, 1, 3), 'ויאמראלהיםיהיאורויהיאור')
   ((1, 1, 4), 'ויראאלהיםאתהאורכיטובויבדלאלהיםביןהאורוביןהחשך')
   ((1, 1, 5), 'ויקראאלהיםלאוריוםולחשךקראלילהויהיערבויהיבקריוםאחד')
   ((1, 1, 6), 'ויאמראלהיםיהירקיעבתוךהמיםויהימבדילביןמיםלמים')
   ((1, 1, 7), 'ויעשאלהיםאתהרקיעויבדלביןהמיםאשרמתחתלרקיעוביןהמיםאשרמעללרקיעויהיכן')
   ((1, 1, 8), 'ויקראאלהיםלרקיעשמיםויהיערבויהיבקריוםשני')
   ((1, 1, 9), 'ויאמראלהיםיקווהמיםמתחתהשמיםאלמקוםאחדותראההיבשהויהיכן')
   ((1, 1, 10), 'ויקראאלהיםליבשהארץולמקוההמיםקראימיםויראאלהיםכיטוב')
   ((1, 1, 11), 'ויאמראלהיםתדשאהארץדשאעשבמזריעזרעעץפריעשהפרילמינואשרזרעובועלהארץויהיכן')
   ((1, 1, 12), 'ותוצאהארץדשאעשבמזריעזרעלמינהוועץעשהפריאשרזרעובולמינהוויראאלהיםכיטוב')
   
   
``DS`` Object - Dictionary of Verses (with Spaces), accessible as data with a 3-digit Tuple Key::

   DS[1,1,1] --> GENESIS 1:1 - 1st Book, 1st Chapter, 1st Verse
   DS[1,1,2] --> GENESIS 1:2 - 1st Book, 1st Chapter, 2nd Verse
   DS[1,1,3] --> GENESIS 1:3 - 1st Book, 1st Chapter, 3rd Verse
   
``D`` Object - Dictionary of Verses/Letters, accessible as data with a 3-digit Tuple Key + sub-element (0-indexed) in sequence of letters within each verse.::

   D[1,1,1][0] --> 1st element (letter) in string/verse sequence --> 'ב'
   D[1,1,1][1] --> 2nd element (letter) in string/verse sequence --> 'ר'
   D[1,1,1][2] --> 3rd element (letter) in string/verse sequence --> 'א'
   D[1,1,1][-1] --> Last element in string/verse sequence...

Data Objects (and derivative Data Objects) with Info for Each Letter in Text:

Custom Letter Objects (LO)

Custom Equidistant Letter Sequence Objects (ELSO)

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


