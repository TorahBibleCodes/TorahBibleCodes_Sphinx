Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes:

1.) DOWNLOAD and INSTALL PYTHON on your local computer: https://www.python.org/downloads/

2.) In the folder where Python has been installed, Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices, and then INSTALL ``ipython`` interactive python (IPython) development environment via ``pip install`` at the command prompt.

.. code-block:: console

   C:\python> pip install ipython
   
3.) DOWNLOAD the TorahBibleCodes GitHub Repo ZIP file or clone the GitHub repo to your local computer: https://github.com/torahbiblecodes/torahbiblecodes

.. code-block:: console

   C:\GitHubRepoClones> git clone https://github.com/TorahBibleCodes/TorahBibleCodes.git
   

WARNING
----------------

There are criminal squatters who are infringing on our TorahBibleCodes international copyright. We are not associated with any current PyPi projects.  DO NOT PIP INSTALL - YOU DO SO AT YOUR OWN RISK OF VIRUSES AND MALICIOUS CODE BY CRIMINAL SQUATTERS WHO ARE SQUATTING, INFRINGING, AND VIOLATING THE TORAHBIBLECODES COPYRIGHT AT PYPI.ORG: https://pypi.org/.

.. code-block:: console

   ## DANGER pip install TorahBibleCodes ## DANGER ## DO NOT PIP INSTALL ## INSTALL AT YOUR OWN RISK! 


Run the App
----------------

After installing Python, ``ipython``, as well as cloning the TorahBibleCodes GitHub Repo to your local computer:

1.) Navigate to the local folder to where you have cloned TorahBibleCodes.

2.) Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices.

3.) Activate your ``ipython`` interactive python (IPython) development environment by typing ``ipython`` at your CLI prompt.

After your ``ipython`` interactive python (IPython) development environment has been activated in the CLI Window:

4.) Type ``%run p.py`` at the ``ipython`` (IPython) command prompt.

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

Witztum, Rips, and Rosenberg (WRR 1994) define an Equidistant Letter Sequence (ELS) as a sequence of letters in the text whose positions - not counting spaces - form an arithmetic progression. That is to say the letters are found at the positions::

   n, (n + d), (n + 2d), (n + 3d) ..., (n + (k - 1)d)

WRR define *n* as the start, *d* as the skip between letters in the search-term, and *k* as the length of the ELS. These three parameters uniquely identify the ELS which is denoted (*n*, *d*, *k*).

For example::

   ELS1 = 'משיח' == 'Mashiach' == 'Messiah'

   ELS2 = 'המשיח' == 'HaMashiach' == 'The Messiah'

*k* = length of an ELS Search-Term, ELS, i.e. the number of letters in the word; here:

1.) The length *k* of ELS1 is 4.

2.) The length *k* of ELS2 is 5.

*n* = index number starting position for each instance for each first (or last) letter in the ELS;

For example, if you are searching for a word that begins (or ends) with the letter Mem (מ/ם) in the text (e.g. משיח), index
number *n* is the index position number(s) for each instance found (i.e. for each *n*) of the letter Mem (מ/ם), and for each
instance of these letters Mem (מ/ם) found, there is the potential to find multiple ELSs beginning (or
ending) on that letter.

Because the letter Mem (מ) is one of the five Hebrew letters with an alternate form if coming as the final letter (ם) of a word, the central algorithm efficiently handles this eventuality of ELS Searches: instead of search for either ("regular letter form or final letter form") of the two possible letter formats, it is more efficient to convert all Hebrew letters to their equivalent Hebrew Gematria Numerical values and then search for these integer numbers. 

*d* = equidistant skip distance(s) between each letter in the ELS successfully found within the
selected text that is searched (i.e. for each *n*); For each instance of a letter found at index number position *n*, there may
potentially be multiple instances of skip distances *d* possible to the next letter(s) in that ELS.



Program Concepts: Native Python Data Objects
----------------

The essential objects in TorahBibleCodes are native Python data objects (i.e. strings, lists, tuples, and dictionaries).

The source texts are digitized versions of the Leningrad Codex provided by https://Sefaria.org. 

For any text chosen (e.g. Genesis, Exodus, Leviticus, Numbers, Deuteronomy, or all five (5) books of the Torah together, or all twenty-one (21) books of the Prophets, or all thirteen (13) books of the Writings, or all (or any of) thirty-nine (39) books of the entire Hebrew Bible), the text is parsed and Python dictionary objects ``D`` and ``DS`` are created that allow one to access each verse by 3-digit Tuple-Key (Book, Chapter, Verse).

After choosing the text(s) to be searched, a Python dictionary ``D`` (with no spaces) and ``DS`` (with spaces) are created to contain each verse - accessible by 3-integer Tuple-Key.

The ``DS`` Dictionary Object may be useful for the interactive user-developer to access the specific verses with the words readable with spaces; The ``D`` Dictionary Object will be more useful to a computer - but these two Python Dictionary Objects contain the same text(s).

Each verse (and letter) of the thirty-nine (39) books of the Hebrew Bible is accessible via the Python dictionaries ``D`` and ``DS`` with a unique 3-digit Tuple Key as per following examples:

``D`` Object - Dictionary of Verses (with No Spaces), accessible as data with a 3-digit Tuple Key::

   ## 3-INTEGER-TUPLE-BASED DICTIONARY KEY POSITION OF (BOOK#, CHAPTER#, VERSE#) - NO SPACES BETWEEN WORDS/LETTERS
   
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

   ## 3-INTEGER-TUPLE-BASED DICTIONARY KEY POSITION OF (BOOK#, CHAPTER#, VERSE#) - WITH SPACES BETWEEN WORDS/LETTERS
   
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
   
``D`` Object - Dictionary of Verses/Letters, accessible as data with a 3-digit Tuple Key + sub-element (0-indexed) in sequence of letters within each verse::

   ## 3-INTEGER-TUPLE-BASED DICTIONARY KEY POSITION OF (BOOK#, CHAPTER#, VERSE#) - NO SPACES BETWEEN WORDS/LETTERS
   ## FOR EACH VERSE: THERE IS NATIVE PYTHON 0-BASED INDEX LIST OF LETTERS IN EACH VERSE
   
   D[1,1,1][0] --> 1st element (letter) in string/verse sequence --> 'ב'
   D[1,1,1][1] --> 2nd element (letter) in string/verse sequence --> 'ר'
   D[1,1,1][2] --> 3rd element (letter) in string/verse sequence --> 'א'
   D[1,1,1][-1] --> Last element (letter) in string/verse sequence --> 'ץ'
   
   D[5,34,12][0] --> 1st element (letter) in string/verse sequence --> 'ו'
   D[5,34,12][1] --> 2nd element (letter) in string/verse sequence --> 'ל'
   D[5,34,12][2] --> 3rd element (letter) in string/verse sequence --> 'כ'
   D[5,34,12][-1] --> Last element (letter) in string/verse sequence --> 'ל'

Data Objects (and derivative Data Objects)
----------------

From the ``D`` and ``DS`` Objects, all other Python Data Objects are derived:

``DL`` Object - Dictionary of Letters (with 4-integer tuple-key) with 4th element of tuple being the (non-0-indexed; 1-indexed) position of letter in verse::

   ## 4-INTEGER-TUPLE-BASED DICTIONARY KEY POSITION OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE) - NO SPACES BETWEEN WORDS/LETTERS
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   DL[1, 1, 1, 1] --> 'ב'
   DL[1, 1, 1, 2] --> 'ר'
   DL[1, 1, 1, 3] --> 'א'
   DL[1, 1, 1, 4] --> 'ש'
   DL[1, 1, 1, 5] --> 'י'
   DL[1, 1, 1, 6] --> 'ת'

   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   DL[5,34,12,43] --> 'י'
   DL[5,34,12,44] --> 'ש'
   DL[5,34,12,45] --> 'ר'
   DL[5,34,12,46] --> 'א'
   DL[5,34,12,47] --> 'ל'

``D5`` Object - Dictionary of Letters (with 5-integer tuple key) with 5th element of tuple being the *n* position (cf. WRR Algorithm above) of letter in total sequence of text.

For example:

1.) One (1) text only (# of letters varies).

2.) All five (5) texts of the Torah (304850 letters) together.

3.) All twenty-one (21) texts of the Prophets (553785 letters) together.

4.) All thirteen (13) texts of the Writings (338407 letters) together.

5.) All thirty-nine (39) texts of the entire Hebrew Bible (1197042 letters) together.

The 5-Integer Tuple-Key / Tuple-Value
----------------

It is this 5th number of this 5-integer tuple-key of the ``D5`` Object (as well as the 5-integer tuple-value of the ``D5K`` Object) that serves as the primary key - and thus the unique identifier - for every letter object in the selected text(s).

It is this 5th integer by which we will uniquely identify each letter position *n* in the selected text(s).

Humans may find it easier to refer to the same letter position *n* by its complete 5-integer tuple-key that allows quick reference to the Book#, Chapter#, Verse#, Letter#InVerse, and Letter#InText.

**Critical Concept:** For any letter in the selected text(s), it is this 5th integer that is the primary key - and unique identifier - by which one identify any one Letter Object ``LO`` (see below). Through this letter position index *n*, one can return (via the ``D5K`` Object) the entire 5-integer tuple-key letter position *n* which can then be used to return that specific Hebrew letter (via the ``D5`` Object).

Thus if one knows either the letter position *n* via the entire 5-integer tuple-number key/value or simply via the 5th number only, it is possible to retrieve that unique letter object at that position.

**Assuming 304850 letters for entire Torah selected**::

   ## 5-INTEGER-TUPLE-BASED DICTIONARY KEY POSITION OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE, LETTER#INTEXT) - NO SPACES BETWEEN WORDS/LETTERS
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   D5[1, 1, 1, 1, 1] --> 'ב'
   D5[1, 1, 1, 2, 2] --> 'ר'
   D5[1, 1, 1, 3, 3] --> 'א'
   D5[1, 1, 1, 4, 4] --> 'ש'
   D5[1, 1, 1, 5, 5] --> 'י'
   D5[1, 1, 1, 6, 6] --> 'ת'

   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   D5[5, 34, 12, 43, 304846] --> 'י'
   D5[5, 34, 12, 44, 304847] --> 'ש'
   D5[5, 34, 12, 45, 304848] --> 'ר'
   D5[5, 34, 12, 46, 304849] --> 'א'
   D5[5, 34, 12, 47, 304850] --> 'ל'
   
``D5K`` Object - Dictionary of 5-integer tuple keys::

   ## 1-BASED DICTIONARY KEY-POSITIONS: RETURNS ## 5-DIGIT-TUPLE-BASED DICTIONARY VALUE OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE, LETTER#INTEXT)
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   D5K[1] --> (1, 1, 1, 1, 1)
   D5K[2] --> (1, 1, 1, 2, 2)
   D5K[3] --> (1, 1, 1, 3, 3)
   D5K[4] --> (1, 1, 1, 4, 4)
   D5K[5] --> (1, 1, 1, 5, 5)
   D5K[6] --> (1, 1, 1, 6, 6)
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   D5K[304846] --> (5, 34, 12, 43, 304846)
   D5K[304847] --> (5, 34, 12, 44, 304847)
   D5K[304848] --> (5, 34, 12, 45, 304848)
   D5K[304849] --> (5, 34, 12, 46, 304849)
   D5K[304850] --> (5, 34, 12, 47, 304850)

``L`` Object - List of Letters::

   ## 0-BASED INDEX POSITIONS
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   L[0:6] --> ['ב', 'ר', 'א', 'ש', 'י', 'ת']
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   L[-5:] --> ['י', 'ש', 'ר', 'א', 'ל']
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   L[304845:304850] --> ['י', 'ש', 'ר', 'א', 'ל']

``S`` Object - String of Letters::

   ## 0-BASED INDEX POSITIONS
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   S[0:6] --> 'בראשית'
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   S[-5:] --> 'ישראל'
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   S[304845:304850] --> 'ישראל'

Hebrew Gematria Numerical Values
----------------

Because of the possibility of five (5) Hebrew letters to have a second, alternate (final letter) form, all Hebrew Unicode letters are converted to their numerical equivalent so that search for ELSs is via Gematria Integer Number value::

   ## HEBREW GEMATRIA NUMERICAL VALUES FOR EQUIVALENT HEBREW LETTERS
   
   א = 1
   ב = 2
   3 = ג
   4 = ד
   5 = ה
   6 = ו
   7 = ז
   8 = ח
   9 = ט
   10 = י
   20 = כ / ך
   30 = ל
   40 = מ / ם
   50 = נ / ן
   60 = ס
   70 = ע
   80 = פ / ף
   90 = צ / ץ
   100 = ק
   200 = ר
   300 = ש
   400 = ת

Each letter's Hebrew Kabbalah Numerical Gematria Value is obtainable by passing a string-sequence to a :py:func:`mod_9A_GetNumberValues4Letters.fn_GetNumberValues` MODULE.FUNCTION() call.

**NOTE:** 

In previous, older versions of Python, Hebrew letters stored in Python memory as the ``L`` Object were right-to-left (R-T-L); However, in development version of Python 3.9+, these same Hebrew letters returned are left-to-right (L-T-R); However, in our version of ``ipython``, they are presented in the UI as R-T-L as shown here; Thus in current versions of Python, the Hebrew letter order is consistent with all other orders in sequences of Strings, Lists, and Tuples, i.e. left-to-right L-T-R. Numbers returned in the ``N`` Object are left-to-right L-T-R, and although they are presented as R-T-L here, they are stored in Python memory as L-T-R.

``N`` Object - List of Gematria Number Values::

   ## 0-BASED INDEX POSITIONS
   
   ## FIRST SIX LETTERS OF TORAH: GENESIS
   L[0:6] --> ['ב', 'ר', 'א', 'ש', 'י', 'ת']
   N[0:6] --> [2, 200, 1, 300, 10, 400]
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   L[-5:] --> ['י', 'ש', 'ר', 'א', 'ל']
   N[-5:] --> [10, 300, 200, 1, 30]
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   L[304845:304850] --> ['י', 'ש', 'ר', 'א', 'ל']
   N[304845:304850] --> [10, 300, 200, 1, 30]

``DW`` Object - Dictionary of Words::

   ## NOTE: BECAUSE OF BUGS IN PRESENTING UNICODE STRINGS ON READ THE DOCS, QUOTES HAVE BEEN REMOVED FROM
   ## THE HEBREW TEXT STRINGS BELOW TO PRESERVE PRESENTATION  OF THESE TUPLES OF DATA;
   ## ACTUAL TEXT STRINGS WILL INCLUDE ENCLOSING QUOTATION MARKS.
   
   ## 1-BASED DICTIONARY KEY-POSITIONS
   
   ## QUIRK IN READ THE DOCS PRESENTING UNICODE HEBREW TEXT WITHIN COMPLEX TUPLE OF NUMBERS
   ## LEFT-TO-RIGHT ORDER WOULD LOOK LIKE THIS:
   In [1]: DW[1] --> ('HebrewWord' , [1, 2, 3, 4, 5, 6], (1, [2, 200, 1, 300, 10, 400], 913))
   
   ## ERROR WITH PRESENTING UNICODE HEBREW TEXT WITHIN COMPLEX TUPLE OF NUMBERS)
   ## RIGHT-TO-LEFT ORDER
   --> ('בראשית' , [1, 2, 3, 4, 5, 6], (1, [2, 200, 1, 300, 10, 400], 913))
   
   ## THUS THE NEED TO PRESENT THIS INFO WITHOUT QUOTES TO PRESERVE THE ORDER
   ## YET THIS RIGHT-TO-LEFT (RTL) TUPLE IS ACTUALLY STORED IN PYTHON MEMORY
   ## AS LEFT-TO-RIGHT.
   --> (בראשית , [1, 2, 3, 4, 5, 6], (1, [2, 200, 1, 300, 10, 400], 913))
      
   In [2]: DW[2] --> (ברא , [7, 8, 9], (2, [2, 200, 1], 203))
   
   In [3]: DW[3] --> (אלהים, [10, 11, 12, 13, 14], (3, [1, 30, 5, 10, 40], 86))
   
   In [4]: DW[4] --> (את , [15, 16], (4, [1, 400], 401)) 

   In [5]: DW[5] --> (השמים , [17, 18, 19, 20, 21], (5, [5, 300, 40, 10, 40], 395))

   In [6]: DW[6] --> (ואת , [22, 23, 24], (6, [6, 1, 400], 407))

   In [7]: DW[7] --> (הארץ , [25, 26, 27, 28], (7, [5, 1, 200, 90], 296))
   
``DW4ELS`` Object - Dictionary of Words for ELSs:

The TorahBibleCodes app can be used as a Hebrew Gematria Number calculator for Hebrew words (i.e. ELSs) that you wish to search for::

   ## PLEASE NOTE BUG IN READ THE DOC'S PRESENTATION OF THE HEBREW UNICODE TEXT STRING WITHIN THIS COMPLEX TUPLE
   
   In [1]: DW4ELS --> {1: ('משיח', (1, [40, 300, 10, 8], 358)),
                       2: ('המשיח', (2, [5, 40, 300, 10, 8], 363))}
   
   In [2]: DW4ELS[1] --> ('משיח', (1, [40, 300, 10, 8], 358)) ## (משיח , (1, [40, 300, 10, 8], 358))
   
   In [3]: DW4ELS[2] --> ('המשיח', (2, [5, 40, 300, 10, 8], 363)) ## (המשיח , (2, [5, 40, 300, 10, 8], 363))
   


Custom Class: Letter Object (LO)
----------------

``LO`` Object - Letter Object:

For each letter in the selected text(s), an instance of the Custom Class of Letter Object (``LO``) is created to bind and contain critical information for that letter, e.g. the unique letter position *n* of that letter object, the Boolean Value of whether that letter is a match in one or more ELSs, etc.::

   ## FIRST LETTER OF TORAH: GENESIS
   In [1]: DLO[1].Letter --> 'ב'
   In [2]: DLO[1].LetterGematriaNumberValue --> 2
   In [3]: DLO[1].LetterPositionIndex --> 1 ## 1-BASED DICTIONARY KEY-POSITIONS
   In [4]: DLO[1].LetterCoordinatesD5K --> (1, 1, 1, 1, 1) ## 1-BASED DICTIONARY KEY-POSITIONS: RETURNS ## 5-DIGIT-TUPLE-BASED DICTIONARY VALUE OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE, LETTER#INTEXT)
   In [5]: DLO[1].LetterCoordinatesDL --> (1, 1, 1, 1) ## 1-BASED DICTIONARY KEY-POSITIONS: RETURNS ## 4-DIGIT-TUPLE-BASED DICTIONARY VALUE OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE)
   In [6]: DLO[1].WordNumber --> 1
   
   ## LAST LETTER OF TORAH: DEUTERONOMY
   In [7]: DLO[304850].Letter --> 'ל'
   In [8]: DLO[304850].LetterGematriaNumberValue --> 30
   In [9]: DLO[304850].LetterPositionIndex --> 304850 ## 1-BASED DICTIONARY KEY-POSITIONS
   In [10]: DLO[304850].LetterCoordinatesD5K --> (5, 34, 12, 47, 304850) ## 1-BASED DICTIONARY KEY-POSITIONS: RETURNS ## 5-DIGIT-TUPLE-BASED DICTIONARY VALUE OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE, LETTER#INTEXT)
   In [11]: DLO[304850].LetterCoordinatesDL --> (5, 34, 12, 47) ## 1-BASED DICTIONARY KEY-POSITIONS: RETURNS ## 4-DIGIT-TUPLE-BASED DICTIONARY VALUE OF (BOOK#, CHAPTER#, VERSE#, LETTER#INVERSE)
   In [12]: DLO[304850].WordNumber --> 79982
   
``DLO`` Object - Dictionary of Letter Objects:

Each Letter Object (``LO``) is stored in a Python Dictionary of Letter Objects ``DLO`` with 1-Based Dictionary Key-Positions::

   ## FIRST SIX LETTERS OF TORAH: GENESIS
   In [1]: DLO[1].Letter --> 'ב'
   In [2]: DLO[2].Letter --> 'ר'
   In [3]: DLO[3].Letter --> 'א'
   In [4]: DLO[4].Letter --> 'ש'
   In [5]: DLO[5].Letter --> 'י'
   In [6]: DLO[6].Letter --> 'ת'
   
   ## LAST FIVE LETTERS OF TORAH: DEUTERONOMY
   In [7]: DLO[304846].Letter --> 'י'
   In [8]: DLO[304847].Letter --> 'ש'
   In [9]: DLO[304848].Letter --> 'ר'
   In [10]: DLO[304849].Letter --> 'א'
   In [11]: DLO[304850].Letter --> 'ל'


   
Custom Class: Equidistant Letter Sequence (ELS) Object (ELSO)
----------------

``DELSO`` Object - Dictionary of Equidistant Letter Sequence (ELS) Objects::

Custom Equidistant Letter Sequence Objects (ELSO)


Custom Class: Global Search Object (GSO)
----------------

``gso`` Object - Global Search Object::

Custom Global Search Object (GSO)

These Python data objects are subsequently incorporated with a custom Global Search Object :py:func:`GSO`::

   gso = GSO()


``gso.S``
``gso.D``
``gso.DS``
``gso.DL``
``gso.D5``
``gso.D5K``



