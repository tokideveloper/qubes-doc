Translation Workflow (PROPOSAL)
===============================

This page describes the translation workflow.
There are these roles: controller, lister, beautifier, uploader, translator, reviewer, downloader and tester.
Of course, one person may have different roles at a time and one role may be owned by different people.

When you like to get or give up a role (except translator and reviewer), tell us at the [qubes-translation mailing list][mailing list qubes-translation].
When you like to get or give up the translator or reviewer role, join the [Qubes OS translation project at Transifex][qubes on transifex].
If there are any questions you don't know whom to ask then also write to the [qubes-translation mailing list][mailing list qubes-translation].

The Controller
--------------

The controller has to

- watch and improve this workflow and
- be available for problems, questions etc. which could not become solved in other ways.

**Current controllers:** &hellip;, &hellip; *at least contact details or a (nick)name*

The Lister
----------

The lister has to update the ranking list of the most urgent webpages to translate.
To do so, he/she has to keep in mind:

- As a rule of thumb: Higher visitor access rate means higher priority.
- New files have to be added to the list.
- Deleted files have no priority and thus, have to be listed below all other files.
- However, the lister has to decide which *order* seems appropriate.
- The lister has also to keep the columns `Source file path and name` and `Last commit` of the list up-to-date.

Thus, the lister needs access to information concerning visitor access rate.

**Current beautifiers:** &hellip;, &hellip; *at least contact details or a (nick)name*

### Translation Priority List ###

**(TO BE EXTRACTED TO ITS OWN FILE)**

The following list is sorted by priority of translation, highest proirity first.
This list is also for keeping tracking of each single file at its current version(s) (old/new, (untranslated)/(translated into languages X, Y, Z), etc.)

| Source file path and name | Last commit<br>(as a link or `(deleted)`) | Beautified<br>yes/no | Uploaded version to Transifex<br>(as a Git link) | Downloaded versions from Transifex<br>(link to original Git file with its languages of downloaded versions) | Tested<br>(languages whose translated files have been tested) |
| ------------------------- | -------------------------------------- | ---------- | ----------------------------------------- | ---------------------------------- | ---------------- |

The Beautifier
--------------

The beautifier has to prepare the source files for translation. This includes:

- checking the [Translation Priority List] to decide which file to beautify first,
- transforming them into correct English,
- following the [Markdown Conventions],
- checking links if they work properly
- update the column `Beautified` in the [Translation Priority List] and
- updating the official webpages if an English phrase has been proposed to be improved. (This includes proposals given at Transifex, thus, the beautifier has to watch the issues and comments there.)

Thus, the beautifier

- needs to have full access to the Qubes project at Transifex and
- should be a native English speaker.

The beautifier may also beg the writers for following the Markdown conventions.

**Current beautifiers:** &hellip;, &hellip; *at least contact details or a (nick)name*

The Uploader
------------

An uploader keeps the files uploaded to Transifex up-to-date as good as possible.
This includes:

- Check the [Translation Priority List] to decide which file to upload first.
- Upload new beautified files if there are any.
- Upload modified beautified files if the modification is significant (totally different content, translation-significant beautifying etc.).
- Delete files uploaded to Transifex if they are not needed anymore.
- Update the column `Uploaded version to Transifex` in the [Translation Priority List].
- If there are source files at Transifex that have not been translated yet, not even partially into any language, replace them with their up-to-date versions.
- The documentation changes frequently, around one time a day. Thus, translations will never be up-to-date. Additionally, translated versions are not officially signed. That's why you should push partially or fully translated files as soon as possible to the website. (The more people (website visitors) we attract, the more translators we might attract, too.)

**Current uploaders:** &hellip;, &hellip; *at least contact details or a (nick)name*

The Translator
--------------

This is a [Transifex role][Transifex Translators] and thus, a [Transifex account] is necessary.
His/her job includes:

- Check the [Translation Priority List] to decide which file to translate first.
- Translate the files by using the Transifex interface and following the [Translation Conventions] (see below).
- Help a file to become fully translated rather than partially.

### Translation Conventions ###

Please pay attention to the following conventions when translating the website of Qubes OS:

1.  Keep in mind that the documentation uses **Markdown** files as source files to translate.
    Thus, any character string with special Markdown meaning has to be kept untranslated or to be adapted if necessary.
    See [here][daringfireball Markdown] and [here][github Markdown] for general manuals how to write in Markdown.
    Also see our [Markdown Conventions] followed in this documentation.
2.  Do not split a single translation sentence over multiple lines. (This should not be possible when using the Transifex interface.)
3.  If a source sentence is split over several lines then comment it or open a new issue via the Transifex interface.
    You can do this by commenting that phrase or opening a new issue using the Transifex interface in both cases.
4.  If there are multiple source sentences in a single line then comment it or open a new issue via the Transifex interface.
5.  Translate a file line-by-line with respect to the context.
    Do not translate random lines without regarding the context.
6.  Address formally.
7.  Don't forget final periods etc. if given in the source phrase.
8.  Pay attention to the differences between diacritics, apostrophes, quotation marks, backticks and so on.
9.  As Andrew David Wong mentioned in a Transifex comment:
    > Comma placement relative to quotation marks is determined by regional convention. See, e.g.,
    > http://blog.apastyle.org/apastyle/2011/08/punctuating-around-quotation-marks.html
    > https://owl.english.purdue.edu/owl/resource/577/03/
    > http://www.quickanddirtytips.com/education/grammar/how-to-use-quotation-marks
    > (Edited to add: The above remark applies to English.)"
10. Follow language-dependent guidelines you should work out in advance and write them down on a new page here.
    (E.g. in German, a typical question is about which quotation marks to use: either `„“` or `»«`.)

Also follow these conventions:

| Type | Source string | Translated string (e.g. German (de))| Note |
| ---- | ------------- | ----------------------------------- | ---- |
| **an internal server path** | /doc/path/to/some/file | **/de**/doc/path/to/some/file | Adapt the prefix with regard to the target language (see the list below). |
| **an external URL** | http://somewhere.on.the.internet/some/path/ | http://somewhere.on.the.internet/some/path/ | Keep it as is. |
| **a local path** | /etc/passwd | /etc/passwd | Keep it as is. |
| **a command** | cp /etc/passwd . | cp /etc/passwd . | Keep it as is. |
| **YAML header** | \-\-\-<br>layout: doc<br>title: VM Tools<br>permalink: /doc/vm-tools/<br>redirect_from:<br>- /en/doc/vm-tools/<br>- /doc/VmTools/<br>- /wiki/VmTools/<br>\-\-\- | \-\-\-<br>layout: doc<br>title: **VM-Werkzeuge**<br>permalink: **/de**/doc/vm-tools/<br>redirect_from:<br>- <br>- **/de**/doc/VmTools/<br>- **/de**/wiki/VmTools/<br>\-\-\- | Remove the /en/&hellip; path as given in the example.|
| **inline-style link**<br>*(no space between *`](`*)* | \[An internal file\](/doc/internal/link/to/file/) | \[**Eine interne Datei**\](**/de**/doc/internal/link/to/file/) | |
| **inline-style link with title**<br>*(no space between *`](`*, but a space after the URL and before *`"`*)* | \[An internal file\](/doc/internal/link/to/file/ "Click here to get to the internal file!") | \[**Eine interne Datei**\](**/de**/doc/internal/link/to/file/ "**Klicken Sie hier, um zur internen Datei zu gelangen!**") | |
| **reference-style link**<br>*(no space between *`][`* and between *`]:`*)* | \[An internal file\]\[any non-visible reference text\]<br>&hellip;<br>\[any non-visible reference text\]: /doc/internal/link/to/file/ | \[**Eine interne Datei**\]\[any non-visible reference text\]<br>&hellip;<br>\[any non-visible reference text\]: **/de**/doc/internal/link/to/file/ | |
| **reference-style link without special link text** | \[An internal file\]<br>&hellip;<br>\[An internal file]: /doc/internal/link/to/file/ | \[**Eine interne Datei**\]<br>&hellip;<br>\[**Eine interne Datei**\]: **/de**/doc/internal/link/to/file/ | |
| **quote** | A quote:<br>&nbsp;&nbsp;&nbsp;&nbsp;This is a quote example. | **Ein Zitat**:<br>&nbsp;&nbsp;&nbsp;&nbsp;**Dies ist ein Zitatbeispiel.** | Translate quotes. |
| **leading and trailing spaces** | \* AAA<br>&nbsp;&nbsp;\* BBB<br>\* CCC<br><br>A quote:<br>&nbsp;&nbsp;&nbsp;&nbsp;This is a quote example. | \* **AAA**<br>&nbsp;&nbsp;\* **BBB**<br>\* **CCC**<br><br>**Ein Zitat**:<br>&nbsp;&nbsp;&nbsp;&nbsp;**Dies ist ein Zitatbeispiel.** | Keep them as they are by **just copying them**. |
| **[escape sequence][daringfireball backslash]** | A single backslash: \\\\ | Ein einzelner Backslash: \\\\ | Keep it as is. |
| **terms from the [glossary]** | TemplateVM,<br>DVM | TemplateVM **(»VorlageVM«)**,<br>DVM | This way, it doesn't matter if the software has been translated or not since both cases are considered. |
| **(button) labels** | Click on "Copy". | **Klicken Sie auf »**Copy**« (»Kopieren«).** | This way, it doesn't matter if the software has been translated or not since both cases are considered. |
| **underlinings** | Section Title<br>&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;<br><br>Subsection Title<br>\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\- | **Abschnittstitel**<br>**&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;&#61;**<br><br>**Unterabschnittstitel**<br>**\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-** | The number of `=` and `-` characters for underlining (sub)sections shall match the number of characters in that (sub)section title. |
| **screenshot** | \!\[edit-button-desktop\](/attachment/wiki/doc-edit/03-button2.png) | \!\[edit-button-desktop\](/attachment/wiki/doc-edit/03-button2.png) | Keep it as is. |

### A rule of thumb for translating ###

If &hellip; | Then &hellip;
------ | --------
A single character or a string of characters that looks weird or neither like an English sentence nor like an English phrase. | Do not translate it. Take it as is by just copying it.
An English sentence looks wrong. | Write a comment or issue via the Transifex interface.
There is a correct English sentence or phrase. | Translate it.
(something else) | Write a comment or issue via the Transifex interface.

### List of language-specific prefixes ###

&hellip;, /de (German), &hellip;, /en or no prefix (American English), &hellip;, /fr (French), &hellip; (to be completed)

The Reviewer
------------

This is a [Transifex role][Transifex Reviewers] and thus, you will need a [Transifex account].
A reviewer has to check if translations have been done with care and correct them if necessary.
He/she has to follow these points:

- Checking the [Translation Priority List] to decide which file to review first.
- Review fully translated files first if possible.
- Try to review a file fully before you proceed to the next one. (We like fully reviewed files rather than partially ones.)
- Try not to review your own translations.
- Consider all [Translation Conventions] *carefully*.
  (This is, why you are a reviewer!)

The Downloader
--------------

The downloader has to

- check the [Translation Priority List] to decide which file to download from Transifex first.
- download reviewed, translated files from Transifex and put them into the correct folders with their correct file names of a *Test Branch*.
- update the column `Downloaded versions from Transifex` of the [Translation Priority List].

**Current downloaders:** &hellip;, &hellip; *at least contact details or a (nick)name*

The Tester
----------

Reviewing is not enough since links should be checked for plausible working and naming and even reviewers can make mistakes.
Thus, a tester should

- check the priority list [Translation Priority List] to decide which file to test first.
- check the translated files in the *Test branch* for plausible formattings,
- test all links in those files for working correctly,
- move to or merge with the *Master branch* (i.e. getting online) and
- update the column `Tested` in the [Translation Priority List].

After all tests have succeeded, the tester uploads the file to the official online website.
If a test fails, the tester has to comment the mistake or open an issue via the Transifex interface.

**Current testers:** &hellip;, &hellip; *at least contact details or a (nick)name*

[mailing list qubes-translation]: /mailing-lists/#qubes-translation
[qubes on transifex]: https://www.transifex.com/otf/qubes/
[Transifex account]: https://www.transifex.com/signup/
[Translation Priority List]: ./#Translation-Priority-List
[Translation Conventions]: ./#Translation-Conventions
[Transifex Translators] : https://docs.transifex.com/getting-started/translators
[Markdown Conventions]: /doc/doc-guidelines/#markdown-conventions
[daringfireball Markdown]: https://daringfireball.net/projects/markdown/
[github Markdown]: https://help.github.com/articles/basic-writing-and-formatting-syntax/
[daringfireball backslash]: https://daringfireball.net/projects/markdown/syntax#backslash
[glossary]: /doc/glossary/
[Transifex Reviewers]: https://docs.transifex.com/translation/reviewing-strings
