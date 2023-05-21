Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes:

1.) DOWNLOAD and INSTALL PYTHON on your local computer: https://www.python.org/downloads/

2.) In the folder where Python has been installed, Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices, and then INSTALL ``ipython`` via ``pip install`` at the command prompt.

.. code-block:: console

   C:\python> pip install ipython
   
3.) DOWNLOAD the TorahBibleCodes GitHub Repo ZIP file or clone the GitHub repo to your local computer.

.. code-block:: console

   C:\GitHubRepoClones> git clone https://github.com/TorahBibleCodes/TorahBibleCodes.git
   

WARNING
----------------

There are criminal squatters who are infringing on our TorahBibleCodes international copyright. We are not associated with any current PyPi projects.  DO NOT PIP INSTALL - YOU DO SO AT YOUR OWN RISK OF VIRUSES AND MALICIOUS CODE BY CRIMINAL SQUATTERS WHO ARE SQUATTING, INFRINGING, AND VIOLATING THE TORAHBIBLECODES COPYRIGHT AT PYPI.ORG: https://pypi.org/.

.. code-block:: console

   ## DANGER pip install TorahBibleCodes ## DANGER ## DO NOT PIP INSTALL ## INSTALL AT YOUR OWN RISK! 


Run the App
----------------

After installing Python as well as cloning the TorahBibleCodes GitHub Repo to your local computer:

1.) Navigate to the local folder to where you have cloned TorahBibleCodes.

2.) Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices.

3.) Activate your ``ipython`` interactive python development environment by typing ``ipython`` at your CLI prompt.

After your IPython development environment has been activated in the CLI Window:

4.) Type ``%run p.py`` at the IPython command prompt.

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

Witztum, Rips, and Rosenberg (WRR) define an Equidistant Letter Sequence (ELS) as a sequence of letters in the text whose positions - not counting spaces - form an arithmetic progression. That is to say the letters are found at the positions

n, (n + d), (n + 2d), (n + 3d) ..., (n + (k - 1)d)

WRR define *n* as the start, *d* as the skip between letters in the search-term, and *k* as the length of the ELS. These three parameters uniquely identify the ELS which is denoted (*n*, *d*, *k*).

For example:

ELS1 = “משיח” == “Mashiach” == “Messiah”

ELS2 = “המשיח” == “HaMashiach” == “The Messiah”

*k* = length of an ELS Search-Term, ELS, i.e. the number of letters in the word; here: The length
*k* of ELS1 is 4; The length *k* of ELS2 is 5.

*d* = equidistant skip distance(s) between each letter in the ELS successfully found within the
selected text that is searched; For each instance of a letter found at index number position *n*, there may
potentially be multiple instances of skip distances *d* possible to the next letter(s) in that ELS.

*n* = index number starting position for each instance for each first (or last) letter in the ELS; For
example, if you are searching for a word that begins (or ends) with the letter Mem (מ) in the text, index
number n is the index position number for each instance found of the letter Mem (מ), and for each
instance of these letters Mem (מ) found, there is the potential to find multiple ELSs beginning (or
ending) on that letter.



Program Concepts: Native Python Data Objects
----------------

The essential objects in TorahBibleCodes are native Python data objects (i.e. strings, lists, tuples, and dictionaries).

For any text chosen (e.g. Genesis, Exodus, Leviticus, Numbers, Deuteronomy, or all five (5) books of the Torah together, or all twenty-one (21) books of the Prophets, or all thirteen (13) books of the Writings, or all thirty-nine (39) books of the entire Hebrew Bible), the text is parsed and Python dictionary objects ``D`` and ``DS`` are created that allow one to access each verse by 3-digit Tuple Key (Book, Chapter, Verse). After choosing the text(s) to be searched, a Python dictionary ``D`` (with no spaces) and ``DS`` (with spaces) are created to contain each verse - accessible by 3-digit Tuple Key.

Each verse (and letter) of the thirty-nine (39) books of the Hebrew Bible is accessible via the Python dictionaries ``D`` and ``DS`` with a unique 3-digit Tuple Key as per following examples:

``D`` Object - Dictionary of Verses (with No Spaces), accessible as data with a 3-digit Tuple Key::

   D[1,1,1] --> GENESIS 1:1 - 1st Book, 1st Chapter, 1st Verse
   D[1,1,2] --> GENESIS 1:2 - 1st Book, 1st Chapter, 2nd Verse
   D[1,1,3] --> GENESIS 1:3 - 1st Book, 1st Chapter, 3rd Verse

   D[1,1,1] --> GENESIS 1:1
   D[1,1,7] --> GENESIS 1:7
   D[1,50,26] --> GENESIS 50:26
   D[2,1,1] --> EXODUS 1:1
   D[2,40,38] --> EXODUS 40:38
   D[3,1,1] --> LEVITICUS 1:1
   D[3,27,34] --> LEVITICUS 27:34
   D[4,1,1] --> NUMBERS 1:1
   D[4,36,13] --> NUMBERS 36:13
   D[5,1,1] --> DEUTERONOMY 1:1
   D[5,34,12] --> DEUTERONOMY 34:12
   
   D[1,1,1] == 'בראשיתבראאלהיםאתהשמיםואתהארץ'
   D[1,1,7] == 'ויעשאלהיםאתהרקיעויבדלביןהמיםאשרמתחתלרקיעוביןהמיםאשרמעללרקיעויהיכן'
   D[1,50,26] == 'וימתיוסףבןמאהועשרשניםויחנטואתוויישםבארוןבמצרים'
   D[2,1,1] == 'ואלהשמותבניישראלהבאיםמצרימהאתיעקבאישוביתובאו'
   D[2,40,38] == 'כיענןיהוהעלהמשכןיומםואשתהיהלילהבולעיניכלביתישראלבכלמסעיהם'
   D[3,1,1] == 'ויקראאלמשהוידבריהוהאליומאהלמועדלאמר'
   D[3,27,34] == 'אלההמצותאשרצוהיהוהאתמשהאלבניישראלבהרסיני'
   D[4,1,1] == 'וידבריהוהאלמשהבמדברסיניבאהלמועדבאחדלחדשהשניבשנההשניתלצאתםמארץמצריםלאמר'
   D[4,36,13] == 'אלההמצותוהמשפטיםאשרצוהיהוהבידמשהאלבניישראלבערבתמואבעלירדןירחו'
   D[5,1,1] == 'אלההדבריםאשרדברמשהאלכלישראלבעברהירדןבמדברבערבהמולסוףביןפארןוביןתפלולבןוחצרתודיזהב'
   D[5,34,12] == 'ולכלהידהחזקהולכלהמוראהגדולאשרעשהמשהלעיניכלישראל'
   
``DS`` Object - Dictionary of Verses (with Spaces), accessible as data with a 3-digit Tuple Key::

   DS[1,1,1] --> GENESIS 1:1 - 1st Book, 1st Chapter, 1st Verse
   DS[1,1,2] --> GENESIS 1:2 - 1st Book, 1st Chapter, 2nd Verse
   DS[1,1,3] --> GENESIS 1:3 - 1st Book, 1st Chapter, 3rd Verse
   
   DS[1,1,1] --> GENESIS 1:1
   DS[1,1,7] --> GENESIS 1:7
   DS[1,50,26] --> GENESIS 50:26
   DS[2,1,1] --> EXODUS 1:1
   DS[2,40,38] --> EXODUS 40:38
   DS[3,1,1] --> LEVITICUS 1:1
   DS[3,27,34] --> LEVITICUS 27:34
   DS[4,1,1] --> NUMBERS 1:1
   DS[4,36,13] --> NUMBERS 36:13
   DS[5,1,1] --> DEUTERONOMY 1:1
   DS[5,34,12] --> DEUTERONOMY 34:12
   
   DS[1,1,1] == 'בראשית ברא אלהים את השמים ואת הארץ'
   DS[1,1,7] == 'ויעש אלהים את הרקיע ויבדל בין המים אשר מתחת לרקיע ובין המים אשר מעל לרקיע ויהי כן'
   DS[1,50,26] == 'וימת יוסף בן מאה ועשר שנים ויחנטו אתו ויישם בארון במצרים'
   DS[2,1,1] == 'ואלה שמות בני ישראל הבאים מצרימה את יעקב איש וביתו באו'
   DS[2,40,38] == 'כי ענן יהוה על המשכן יומם ואש תהיה לילה בו לעיני כל בית ישראל בכל מסעיהם'
   DS[3,1,1] == 'ויקרא אל משה וידבר יהוה אליו מאהל מועד לאמר'
   DS[3,27,34] == 'אלה המצות אשר צוה יהוה את משה אל בני ישראל בהר סיני'
   DS[4,1,1] == 'וידבר יהוה אל משה במדבר סיני באהל מועד באחד לחדש השני בשנה השנית לצאתם מארץ מצרים לאמר'
   DS[4,36,13] == 'אלה המצות והמשפטים אשר צוה יהוה ביד משה אל בני ישראל בערבת מואב על ירדן ירחו'
   DS[5,1,1] == 'אלה הדברים אשר דבר משה אל כל ישראל בעבר הירדן במדבר בערבה מול סוף בין פארן ובין תפל ולבן וחצרת ודי זהב'
   DS[5,34,12] == 'ולכל היד החזקה ולכל המורא הגדול אשר עשה משה לעיני כל ישראל'
   
``D`` Object - Dictionary of Verses/Letters, accessible as data with a 3-digit Tuple Key + sub-element (0-indexed) in sequence of letters within each verse.::

   D[1,1,1][0] --> 1st element (letter) in string/verse sequence --> 'ב'
   D[1,1,1][1] --> 2nd element (letter) in string/verse sequence --> 'ר'
   D[1,1,1][2] --> 3rd element (letter) in string/verse sequence --> 'א'
   D[1,1,1][-1] --> Last element (letter) in string/verse sequence --> 'ץ'

Data Objects (and derivative Data Objects)
----------------

From the ``D`` and ``DS`` Objects, all other Python Data Objects are derived:

``DL`` Object - Dictionary of Letters (with 4-digit tuple-key) with 4th element of tuple being the (non-0-indexed; 1-indexed) position of letter in verse::

   DL[1, 1, 1, 1] --> 'ב'
   DL[1, 1, 1, 2] --> 'ר'
   DL[1, 1, 1, 3] --> 'א'
   DL[1, 1, 1, 4] --> 'ש'
   DL[1, 1, 1, 5] --> 'י'
   DL[1, 1, 1, 6] --> 'ת'

   DL[5,34,12,43] --> 'י'
   DL[5,34,12,44] --> 'ש'
   DL[5,34,12,45] --> 'ר'
   DL[5,34,12,46] --> 'א'
   DL[5,34,12,47] --> 'ל'


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


