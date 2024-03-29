Usage
=====

.. _installation:

Installation
------------

To use TorahBibleCodes:

1.) DOWNLOAD and INSTALL PYTHON on your local computer: https://www.python.org/downloads/

2.) In the folder where Python has been installed, Open a Command Line Interface (CLI) such as Windows PowerShell or the equivalent on other Apple and Linux devices, and then TEST INSTALL TEST TEST ``ipython`` interactive python (IPython) development environment via ``pip install`` at the command prompt.

.. code-block:: console

   C:\python> pip install ipython

3.) DOWNLOAD the TorahBibleCodes GitHub Repo ZIP file or clone the GitHub repo to your local computer:

GITHUB: https://github.com/torahbiblecodes/torahbiblecodes

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
   
   WITHIN FUNCTION:  BEGIN FUNCTION #1A - GET USER INPUT; CHOOSE CODEX TO SEARCH

   Please select Hebrew Bible codex to search:

   1 - Koren - Claremont Michigan Transliteration
   2 - Leningrad Codex

   Please select codex to search:

After choosing the Codex, you will be prompted to select a text from the Hebrew Bible via the :py:func:`fn_GetUserInput` function.

For example::
   
   WITHIN FUNCTION:  BEGIN FUNCTION #1B - GET USER INPUT; CHOOSE TEXT TO SEARCH
   
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

As an *a priori* working hypothesis, to test the validity of the 'Torah Code Hypothesis' (Haralick: CITE CITATION), let's propose that if anything is an agreed central concept within both Judaism and Christianity, the terms 'Messiah' and 'The Messiah' are reasonable and logical as initial *a priori* keywords to begin our ELS Search for encoded ELSs within the Torah and Hebrew Bible; Furthermore, as part of defining our scientific criteria for our research experiment(s), we will expect to find these ELS Search Terms specifically within the context of Messianic passages; Therefore we will choose the following as initial ELS search term variables to search for::

   ELS1 = 'משיח' == 'Mashiach' == 'Messiah'

   ELS2 = 'המשיח' == 'HaMashiach' == 'The Messiah'

*k* = length of an ELS Search-Term, ELS, i.e. the number of letters in the word; here:

1.) The length *k* of ELS1 is 4.

2.) The length *k* of ELS2 is 5.

*n* = index number starting position for each instance for each first (or last) letter in the ELS;

For example, if you are searching for a word that begins (or ends) with the letter Mem (מ/ם) in the text (e.g. משיח), index
number *n* is the letter position index number(s) for each instance found (i.e. for each letter position index *n*) of the letter Mem (מ/ם).

For each instance of these letters Mem (מ/ם) found, there is the potential to find multiple ELSs beginning (or
ending) on that letter via multiple instance of *d* (see below).

Because the letter Mem (מ) is one of the five Hebrew letters with an alternate form if coming as the final letter (ם) of a word, the central algorithm efficiently handles this eventuality for ELS Searches: instead of search for either ("regular letter form or final letter form") of the two possible letter formats, it is more efficient to convert all Hebrew letters to their equivalent Hebrew Gematria Number values and then search for these integer numbers. 

*d* = equidistant skip distance(s) between each letter in the ELS successfully found within the
selected text that is searched (i.e. for each letter position index number *n*); For each instance of a letter found at letter position index number *n*, there may potentially be multiple instances of skip distances *d* possible to the next letter(s) in that ELS.



Program Concepts: Native Python Data Objects
----------------

The essential objects in TorahBibleCodes are native Python data objects (i.e. strings, lists, tuples, and dictionaries).

The source texts are digitized versions of the Leningrad Codex provided by https://Sefaria.org, available here: https://github.com/TorahBibleCodes/Sefaria-Export/tree/master/json/Tanakh .

For any text chosen (e.g. Genesis, Exodus, Leviticus, Numbers, Deuteronomy, or all five (5) books of the Torah together, or all twenty-one (21) books of the Prophets, or all thirteen (13) books of the Writings, or all (or any of) thirty-nine (39) books of the entire Hebrew Bible), the text is parsed and Python dictionary objects ``D`` and ``DS`` are created that allow one to access each verse by 3-digit Tuple-Key (Book, Chapter, Verse).

After choosing the text(s) to be searched, a Python dictionary ``D`` (with no spaces) and ``DS`` (with spaces) are created to contain each verse - accessible by 3-integer Tuple-Key.

The ``DS`` Dictionary Object may be useful for the interactive user-developer to access the specific verses with the words readable with spaces; The ``D`` Dictionary Object will be more useful to a computer - but these two Python Dictionary Objects contain the same text(s).

Each verse (and letter) of the thirty-nine (39) books of the Hebrew Bible is accessible via the Python dictionaries ``D`` and ``DS`` with a unique 3-digit Tuple Key as per following examples:

``D`` Object - Dictionary of Verses (with No Spaces), accessible as data with a 3-digit Tuple Key:

**Assuming 304850 letters for entire Torah selected**::

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
   
``DS`` Object - Dictionary of Verses (with Spaces), accessible as data with a 3-digit Tuple Key:

**Assuming 304850 letters for entire Torah selected**::

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
   
``D`` Object - Dictionary of Verses/Letters, accessible as data with a 3-digit Tuple Key + sub-element (0-indexed) in sequence of letters within each verse:

**Assuming 304850 letters for entire Torah selected**::

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

``DL`` Object - Dictionary of Letters (with 4-integer tuple-key) with 4th element of tuple being the (non-0-indexed; 1-indexed) position of letter in verse:

**Assuming 304850 letters for entire Torah selected**::

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

Unique Identifier: The 5-Integer Tuple-Key / Tuple-Value
----------------

It is this **5th number of this 5-integer tuple-key** of the ``D5`` Object (as well as the 5-integer tuple-value of the ``D5K`` Object) that serves as the **primary key** - and thus the **unique identifier** - for every letter object in the selected text(s).

It is this 5th integer by which we will **uniquely identify each letter position (n)** in the selected text(s).

Humans may find it easier to refer to the same letter position *n* by its complete 5-integer tuple-key that allows quick reference to::

   ## (Book#, Chapter#, Verse#, Letter#InVerse, and Letter#InText)

**Critical Concept:** For any letter in the selected text(s), the **5th integer is the primary key - and unique identifier -** by which one identify any one Letter Object ``LO`` (see below). Through this letter position index *n*, one can return (via the ``D5K`` Object) the entire 5-integer tuple-key letter position *n* which can then be used to return that specific Hebrew letter (via the ``D5`` Object).

**Key Insight:** Thus if one knows either the letter position *n* via the entire 5-integer tuple-number key/value or simply via the 5th number only, it is possible to retrieve any and all data associated with that unique letter object at that unique letter position *n*.

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

Hebrew Gematria Number Values
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
   
**NOTE:** 

In previous, older versions of Python, Hebrew letters stored in Python memory as the ``L`` Object were right-to-left (R-T-L); However, in development version of Python 3.9+, these same Hebrew letters returned are left-to-right (L-T-R); However, in our version of ``ipython``, they are presented in the UI as R-T-L as shown here; Thus in current versions of Python, the Hebrew letter order is consistent with all other orders in sequences of Strings, Lists, and Tuples, i.e. left-to-right L-T-R. Numbers returned in the ``N`` Object are left-to-right L-T-R, and although they are presented as R-T-L here, they are stored in Python memory as L-T-R.


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

``ELSO`` Object - Equidistant Letter Sequence (ELS) Object:

For each ELS Search Term that is inputted by the user, an instance of the Custom Class of Equidistant Letter Sequence (ELS) Object (``ELSO``) is created to bind and contain critical information for that ELS Search Term, e.g. Letters (i.e. Gematria Number Values) for that ELS Search Term, the length *k* of that ELS Search Term, Maximum Possible Skip Distance (defined by Haralick [CITE CITATION]), Lists of Lists of Index Matches for each letter of each ELS Search Term.

**Assuming 304850 letters for entire Torah selected**::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח' ## DICTIONARY OF ELSO OBJECTS [ELEMENT #1]
   
   ## ELSO #1 
   In [1]: DELSO[1].ELSSearchTermNumber --> 1
   In [2]: DELSO[1].Letters --> [40, 300, 10, 8] ## ACTUALLY: GEMATRIA NUMBER VALUES [40, 300, 10, 8] == [ח, י, ש, מ] == [מ, ש, י, ח]
   In [3]: DELSO[1].k --> 4 ## INTEGER : LENGTH OF ELS SEARCH TERM ## 4
   In [4]: DELSO[1].MaxSkipDistance --> 76212 ## (LengthOfTextToSearch / k)
   In [5]: DELSO[1].ListOfListsOfIndexMatches --> ## 0-BASED INDEX POSITIONS ## ONE (1) LIST PER LETTER MATCH FOR EACH LETTER IN EACH (MULTIPLE) ELS SEARCH TERM; MATCHES OF INDEX POSITIONS ## len(DELSO[1].ListOfListsOfIndexMatches) --> 4
   




``DELSO`` Object - Dictionary of Equidistant Letter Sequence (ELS) Objects:

Each Equidistant Letter Sequence (ELS) Object (``ELSO``) is stored in a Python Dictionary of Equidistant Letter Sequence (ELS) Objects ``DELSO`` with 1-Based Dictionary Key-Positions.

**Assuming 304850 letters for entire Torah selected**::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח'

   ## 40 == מ / ם
   In [1]: len(DELSO[1].ListOfListsOfIndexMatches[0]) --> 25090 ## NUMBER OF MATCHES FOR 1ST LETTER IN 1ST ELS SEARCH TERM

   ## 300 == ש
   In [2]: len(DELSO[1].ListOfListsOfIndexMatches[1]) --> 15595 ## NUMBER OF MATCHES FOR 2ND LETTER IN 1ST ELS SEARCH TERM
        
   ## 10 == י
   In [3]: len(DELSO[1].ListOfListsOfIndexMatches[2]) --> 31556 ## NUMBER OF MATCHES FOR 3RD LETTER IN 1ST ELS SEARCH TERM
        
   ## 8 == ח
   In [4]: len(DELSO[1].ListOfListsOfIndexMatches[3]) --> 7189 ## NUMBER OF MATCHES FOR 4TH LETTER IN 1ST ELS SEARCH TERM


   ## ELS SEARCH TERM: 'המשיח' - 'HaMashiach' - 'The Messiah'
   ## DELSO[2] ~ 'המשיח'

   ## 5 == ה
   In [5]: len(DELSO[2].ListOfListsOfIndexMatches[0]) --> 28055 ## NUMBER OF MATCHES FOR 1ST LETTER IN 2ND ELS SEARCH TERM

   ## 40 == מ / ם
   In [6]: len(DELSO[2].ListOfListsOfIndexMatches[1]) --> 25090 ## NUMBER OF MATCHES FOR 2ND LETTER IN 2ND ELS SEARCH TERM

   ## 300 == ש
   In [7]: len(DELSO[2].ListOfListsOfIndexMatches[2]) --> 15595 ## NUMBER OF MATCHES FOR 3RD LETTER IN 2ND ELS SEARCH TERM
        
   ## 10 == י
   In [8]: len(DELSO[2].ListOfListsOfIndexMatches[3]) --> 31556 ## NUMBER OF MATCHES FOR 4TH LETTER IN 2ND ELS SEARCH TERM
        
   ## 8 == ח
   In [9]: len(DELSO[2].ListOfListsOfIndexMatches[4]) --> 7189 ## NUMBER OF MATCHES FOR 5TH LETTER IN 2ND ELS SEARCH TERM
   
The Central Search Algorithm
----------------

There are several ways one can implement WRR's Central Search Algorithm (i.e. Formula) in Python.

For our purposes it is most efficient to convert all Hebrew letters to their Gematria Number equivalent, and then search for either the first or last letter in each ELS Search term - or both.

We can search for the first letter Mem (מ/ם) for ELS Search Term #1 and Hey (ה) for each ELS Search Term #2, and then search both forwards (+) and backwards (-) in the selected text(s) for ELS Matches, i.e. doing two (2) searches for each ELS Search Term: 1.) From the first letter searching forwards (+); 2.) From the first letter searching backwards (-).

**AND/OR:** We can search for the first letter Mem (מ/ם) for ELS Search Term #1 and Hey (ה) for ELS Search Term #2 AS WELL AS the last letter Het (ח) for each ELS Search Term, and search only forwards for ELS Matches, i.e. doing two (2) searches for each ELS Search Term: 1.) From the first letter searching forwards (+) only; 2.) From the last letter search forwards (+) only.   

Therefore, we can obtain the letter position index numbers *n* of matches for each of these critical first and/or last letter objects for each ELS Search Term:

**Assuming 304850 letters for entire Torah selected**::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח'
   
   ## 40 == מ / ם
   In [1]: len(DELSO[1].ListOfListsOfIndexMatches[0]) --> 25090 ## NUMBER OF MATCHES FOR 1ST LETTER IN 1ST ELS SEARCH TERM
   
   ## FIRST TEN (10) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 1ST LETTER IN 1ST ELS TERM
   In [1]: DELSO[1].ListOfListsOfIndexMatches[0][0] --> 14
   In [2]: DELSO[1].ListOfListsOfIndexMatches[0][1] --> 19
   In [3]: DELSO[1].ListOfListsOfIndexMatches[0][2] --> 21
   In [4]: DELSO[1].ListOfListsOfIndexMatches[0][3] --> 57
   In [5]: DELSO[1].ListOfListsOfIndexMatches[0][4] --> 66
   In [6]: DELSO[1].ListOfListsOfIndexMatches[0][5] --> 67
   In [7]: DELSO[1].ListOfListsOfIndexMatches[0][6] --> 78
   In [8]: DELSO[1].ListOfListsOfIndexMatches[0][7] --> 80
   In [9]: DELSO[1].ListOfListsOfIndexMatches[0][8] --> 84
   In [10]: DELSO[1].ListOfListsOfIndexMatches[0][9] --> 90
   
   ## LAST TEN (10) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 1ST LETTER IN 1ST ELS TERM
   In [11]: DELSO[1].ListOfListsOfIndexMatches[0][25080] --> 304702
   In [12]: DELSO[1].ListOfListsOfIndexMatches[0][25081] --> 304717
   In [13]: DELSO[1].ListOfListsOfIndexMatches[0][25082] --> 304734
   In [14]: DELSO[1].ListOfListsOfIndexMatches[0][25083] --> 304740
   In [15]: DELSO[1].ListOfListsOfIndexMatches[0][25084] --> 304751
   In [16]: DELSO[1].ListOfListsOfIndexMatches[0][25085] --> 304756
   In [17]: DELSO[1].ListOfListsOfIndexMatches[0][25086] --> 304777
   In [18]: DELSO[1].ListOfListsOfIndexMatches[0][25087] --> 304781
   In [19]: DELSO[1].ListOfListsOfIndexMatches[0][25088] --> 304821
   In [20]: DELSO[1].ListOfListsOfIndexMatches[0][25089] --> 304836

**Test Driven Development**:

Let's test the both the first and last results that will be easily confirmable by a human::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח'

   ## 40 == מ / ם
   In [1]: len(DELSO[1].ListOfListsOfIndexMatches[0]) --> 25090 ## NUMBER OF MATCHES FOR 1ST LETTER IN 1ST ELS SEARCH TERM

   ## TEST-DRIVEN DEVELOPMENT: TEST RESULTS FOR FIRST INSTANCE OF LETTER POSITION MATCH (n)
   In [1]: DELSO[1].ListOfListsOfIndexMatches[0][0] --> 14
   In [2]: DLO[14].Letter --> 'ם'
   In [3]: DLO[14].LetterGematriaNumberValue --> 40
   In [4]: DLO[14].WordNumber --> 3
   In [5]: DW[3] --> ('אלהים', [10, 11, 12, 13, 14], (3, [1, 30, 5, 10, 40], 86)) ## (אלהים , [10, 11, 12, 13, 14], (3, [1, 30, 5, 10, 40], 86))
   
   ## TEST-DRIVEN DEVELOPMENT: TEST RESULTS FOR LAST INSTANCE OF LETTER POSITION MATCH (n)
   In [6]: DELSO[1].ListOfListsOfIndexMatches[0][25089] --> 304836
   In [7]: DLO[304836].Letter --> 'מ'
   In [8]: DLO[304836].LetterGematriaNumberValue --> 40
   In [9]: DLO[304836].WordNumber --> 79979
   In [10]: DW[79979] --> ('משה', [304836, 304837, 304838], (79979, [40, 300, 5], 345)) ## (משה , [304836, 304837, 304838], (79979, [40, 300, 5], 345))

**Simplifying the Search Algorithm**:

Since we have all the letter position index numbers *n* for each letter in every ELS Search Term, we do not need to search each letter in the entire selected text for matches; we simply need to use the numbers of the index positions that we already have for only those letters of the ELS Search Term(s): 

**Assuming 304850 letters for entire Torah selected**::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח'
   
   ## 40 == מ / ם
   In [1]: len(DELSO[1].ListOfListsOfIndexMatches[0]) --> 25090 ## NUMBER OF MATCHES FOR 1ST LETTER IN 1ST ELS SEARCH TERM
   
   ## FIRST SIX (6) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 1ST LETTER IN 1ST ELS TERM
   In [2]: DELSO[1].ListOfListsOfIndexMatches[0][0] --> 14
   In [3]: DELSO[1].ListOfListsOfIndexMatches[0][1] --> 19
   In [4]: DELSO[1].ListOfListsOfIndexMatches[0][2] --> 21
   In [5]: DELSO[1].ListOfListsOfIndexMatches[0][3] --> 57
   In [6]: DELSO[1].ListOfListsOfIndexMatches[0][4] --> 66
   In [7]: DELSO[1].ListOfListsOfIndexMatches[0][5] --> 67
   
   ## 300 == ש
   In [8]: len(DELSO[1].ListOfListsOfIndexMatches[1]) --> 15595 ## NUMBER OF MATCHES FOR 2ND LETTER IN 1ST ELS SEARCH TERM
   
   ## FIRST SIX (6) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 2ND LETTER IN 1ST ELS TERM
   In [9]: DELSO[1].ListOfListsOfIndexMatches[1][0] --> 4
   In [10]: DELSO[1].ListOfListsOfIndexMatches[1][1] --> 18
   In [11]: DELSO[1].ListOfListsOfIndexMatches[1][2] --> 47
   In [12]: DELSO[1].ListOfListsOfIndexMatches[1][3] --> 147
   In [13]: DELSO[1].ListOfListsOfIndexMatches[1][4] --> 169
   In [14]: DELSO[1].ListOfListsOfIndexMatches[1][5] --> 245
   
   ## 10 == י
   In [15]: len(DELSO[1].ListOfListsOfIndexMatches[2]) --> 31556 ## NUMBER OF MATCHES FOR 3RD LETTER IN 1ST ELS SEARCH TERM
   
   ## FIRST SIX (6) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 3RD LETTER IN 1ST ELS TERM
   In [16]: DELSO[1].ListOfListsOfIndexMatches[2][0] --> 5
   In [17]: DELSO[1].ListOfListsOfIndexMatches[2][1] --> 13
   In [18]: DELSO[1].ListOfListsOfIndexMatches[2][2] --> 20
   In [19]: DELSO[1].ListOfListsOfIndexMatches[2][3] --> 35
   In [20]: DELSO[1].ListOfListsOfIndexMatches[2][4] --> 53
   In [21]: DELSO[1].ListOfListsOfIndexMatches[2][5] --> 65
   
   ## 8 == ח
   In [22]: len(DELSO[1].ListOfListsOfIndexMatches[3]) --> 7189 ## NUMBER OF MATCHES FOR 4TH LETTER IN 1ST ELS SEARCH TERM
   
   ## FIRST SIX (6) INDEX POSITION MATCHES (n) FOR EACH MATCH IN SELECTED TEXT FOR 4TH LETTER IN 1ST ELS TERM
   In [23]: DELSO[1].ListOfListsOfIndexMatches[3][0] --> 46
   In [24]: DELSO[1].ListOfListsOfIndexMatches[3][1] --> 61
   In [25]: DELSO[1].ListOfListsOfIndexMatches[3][2] --> 69
   In [26]: DELSO[1].ListOfListsOfIndexMatches[3][3] --> 146
   In [27]: DELSO[1].ListOfListsOfIndexMatches[3][4] --> 168
   In [28]: DELSO[1].ListOfListsOfIndexMatches[3][5] --> 196
   
   
   

**Assuming 304850 letters for entire Torah selected**::

   ## ELS SEARCH TERM: 'משיח' - 'Mashiach' - 'Messiah'
   ## DELSO[1] ~ 'משיח'
   

   
Custom Class: Global Search Object (GSO)
----------------

``gso`` Object - Global Search Object::

Custom Global Search Object (GSO)

These Python data objects are subsequently incorporated with a custom Global Search Object :py:func:`GSO`::

   gso = GSO()

``gso.D``
``gso.DS``
``gso.S``
``gso.L``
``gso.N``
``gso.DS``
``gso.DL``
``gso.D5``
``gso.D5K``
``gso.DLO``
``gso.DELSO``
``gso.DW``



