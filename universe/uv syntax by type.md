# Rocket UniVerse (U2) mvbasic syntax by type

Keywords with ~~strikethrough~~ are either redundant or ancient legacy and should be deprecated.

## Compiler directives

The following table describes compiler directive statements.

| Command     | Type       | Description                                                                                                                                                  |
| -           | -          | -                                                                                                                                                            |
| $*          | statement  | Identifies a line as a comment line. Same as the !, $*, and REM statements.                                                                                  |
| !           | statement  | Identifies a line as a comment line. Same as the *, $*, and REM statements.                                                                                  |
| #INCLUDE    | statement  | Inserts and compiles UniVerse BASIC source code from another program into the program being compiled. Same as the $INCLUDE and INCLUDE statements.           |
| $*          | statement  | Identifies a line as a comment line. Same as the *, !, and REM statements.                                                                                   |
| $CHAIN      | statement  | Inserts and compiles UniVerse BASIC source code from another program into the program being compiled.                                                        |
| $COPYRIGHT  | statement  | Inserts comments into the object code header. (UniVerse supports this statement for compatibility with existing software.)                                   |
| $DEFINE     | statement  | Defines a compile time symbol.                                                                                                                               |
| $EJECT      | statement  | Begins a new page in the listing record. (UniVerse supports this statement for compatibility with existing software.) Same as the $PAGE statement.           |
| $IFDEF      | statement  | Tests for the definition of a compile time symbol.                                                                                                           |
| $IFNDEF     | statement  | Tests for the definition of a compile time symbol.                                                                                                           |
| $INCLUDE    | statement  | Inserts and compiles UniVerse BASIC source code from another program into the program being compiled. Same as the #INCLUDE and INCLUDE statements.           |
| $INSERT     | statement  | Performs the same operation as $INCLUDE; the only difference is in the syntax. (UniVerse supports this statement for compatibility with existing software.)  |
| $MAP        | statement  | In NLS mode, specifies the map for the source code.                                                                                                          |
| $OPTIONS    | statement  | Sets compile time emulation of UniVerse flavors.                                                                                                             |
| $PAGE       | statement  | Begins a new page in the listing record. (UniVerse supports this statement for compatibility with existing software.) Same as the $EJECT statement.          |
| EQUATE      | statement  | Assigns a symbol as the equivalent of a variable, function, number, character, or string.                                                                    |
| EQU         | statement  | Assigns a symbol as the equivalent of a variable, function, number, character, or string.                                                                    |
| INCLUDE     | statement  | Inserts and includes the specified BASIC source code from another program into the program being compiled. Same as the #INCLUDE and $INCLUDE statements.     |
| NULL        | statement  | Indicates that no operation is to be performed.                                                                                                              |
| REM         | statement  | Identifies a line as a comment line. Same as the *, !, and $* statements.                                                                                    |
| $UNDEFINE   | statement  | Removes the definition for a compile time symbol.                                                                                                            |

## Declarations

The following table describes Declaration statements.

| Command     | Type       | Description                                                                                         |
| -           | -          | -                                                                                                   |
| COMMON      | statement  | Defines a storage area in memory for variables commonly used by programs and external subroutines.  |
| COM         | statement  | Alternate form of COMMON.                                                                           |
| DEFFUN      | statement  | Defines a user-written function.                                                                    |
| DIMENSION   | statement  | Declares the name, dimensionality, and size constraints of an array variable.                       |
| DIM         | statement  | Alternate form of DIMENSION.                                                                        |
| FUNCTION    | statement  | Identifies a user-written function.                                                                 |
| PROGRAM     | statement  | Identifies a program.                                                                               |
| PROG        | statement  | Alternate form of PROGRAM.                                                                          |
| SUBROUTINE  | statement  | Identifies a series of statements as a subroutine.                                                  |
| SUB         | statement  | Alternate form of SUBROUTINE.                                                                       |

## Assignments

The following table describes Assignment functions and statements.

| Command     | Type       | Description                                                           |
| -           | -          | -                                                                     |
| ASSIGNED    | function   | Determines if a variable is assigned a value.                         |
| CLEAR       | statement  | Assigns a value of 0 to specified variables.                          |
| ~~LET~~     | statement  | Assigns a value to a variable. [Rarely used]                          |
| MAT         | statement  | Assigns a new value to every element of an array with one statement.  |
| UNASSIGNED  | function   | Determines if a variable is unassigned.                               |

## Program flow control

The following table describes Program Flow Control functions and statements.

| Command         | Type       | Description                                                                                                                                                                      |
| -               | -          | -                                                                                                                                                                                |
| ABORT           | statement  | Terminates all programs and returns to the UniVerse command level.                                                                                                               |
| BEGIN CASE      | statement  | Indicates the beginning of a set of CASE statements.                                                                                                                             |
| CALL            | statement  | Executes an external subroutine.                                                                                                                                                 |
| CASE            | statement  | Alters program flow based on the results returned by expressions.                                                                                                                |
| CHAIN           | command    | Terminates a BASIC program and executes a UniVerse command.                                                                                                                      |
| CONTINUE        | statement  | Transfers control to the next logical iteration of a loop.                                                                                                                       |
| END             | statement  | Indicates the end of a program or a block of statements.                                                                                                                         |
| END CASE        | statement  | Indicates the end of a set of CASE statements.                                                                                                                                   |
| ~~ENTER~~       | statement  | Executes an external subroutine.                                                                                                                                                 |
| EXECUTE         | statement  | Executes UniVerse sentences and paragraphs from within the BASIC program.                                                                                                        |
| EXIT            | statement  | Quits execution of a LOOP…REPEAT or FOR…NEXT loop and branches to the statement following.                                                                                       |
| FOR             | statement  | Allows a series of instructions to be performed in a loop a given number of times.                                                                                               |
| GOSUB           | statement  | Branches to and returns from an internal subroutine.                                                                                                                             |
| ~~GO SUB~~      | statement  | Alternate form of GOSUB.                                                                                                                                                         |
| GOTO            | statement  | Branches unconditionally to a specified statement within the program or subroutine.                                                                                              |
| ~~GO~~          | statement  | Alternate form of GOTO.                                                                                                                                                          |
| ~~GO TO~~       | statement  | Alternate form of GO TO.                                                                                                                                                         |
| IF              | statement  | Determines program flow based on the evaluation of an expression.                                                                                                                |
| LOOP            | statement  | Repeatedly executes a sequence of statements under specified conditions.                                                                                                         |
| NEXT            | statement  | Defines the end of a FOR…NEXT loop.                                                                                                                                              |
| ON              | statement  | Transfers program control to a specified internal subroutine or to a specified statement, under specified conditions.                                                            |
| PERFORM         | statement  | Executes a specified UniVerse sentence, paragraph, menu, or command from within the BASIC program, and then returns execution to the statement following the PERFORM statement.  |
| REPEAT          | statement  | Repeatedly executes a sequence of statements under specified conditions.                                                                                                         |
| RETURN          | statement  | Transfers program control from an internal or external subroutine back to the calling program.                                                                                   |
| RETURN(value)   | statement  | Returns a value from a user-written function.                                                                                                                                    |
| STOP            | statement  | Terminates the current program.                                                                                                                                                  |
| SUBR            | function   | Returns the value of an external subroutine.                                                                                                                                     |
| UNTIL           | statement  | Provides conditions under which the LOOP…REPEAT statement or FOR…NEXT terminates                                                                                                 |
| WHILE           | statement  | Provides conditions under which the LOOP…REPEAT statement or FOR…NEXT terminates                                                                                                 |

## File I/O

The following table describes File I/O functions and statements.

| Command                          | Type       | Description                                                                                                                                                         |
| -                                | -          | -                                                                                                                                                                   |
| AUTHORIZATION                    | statement  | Specifies the effective run-time UID (user identification) number of the program.                                                                                   |
| BEGIN TRANSACTION                | statement  | Indicates the beginning of a set of statements that make up a single transaction.                                                                                   |
| BSCAN                            | statement  | Scans the leaf-nodes of a B-tree file (type 25) or a secondary index.                                                                                               |
| CLEARFILE                        | statement  | Erases all records from a file.                                                                                                                                     |
| CLOSE                            | statement  | Writes data written to the file physically on the disk and releases any file or update locks.                                                                       |
| COMMIT                           | statement  | Commits all changes made during a transaction, writing them to disk.                                                                                                |
| DELETE                           | statement  | Deletes a record from a UniVerse file.                                                                                                                              |
| DELETEU                          | statement  | Deletes a record from a previously opened file retaining any active update locks                                                                                    |
| END TRANSACTION                  | statement  | Indicates where execution should continue after a transaction terminates.                                                                                           |
| FILELOCK                         | statement  | Sets a file update lock on an entire file to prevent other users from updating the file until this program releases it.                                             |
| FILEUNLOCK                       | statement  | Releases file locks set by the FILELOCK statement.                                                                                                                  |
| INDICES                          | function   | Returns information about the secondary key indexes in a file.                                                                                                      |
| MATREAD                          | statement  | Assigns the data stored in successive fields of a record from a UniVerse file to the consecutive elements of an array.                                              |
| MATREADL                         | statement  | Sets a shared read lock on a record, then assigns the data stored in successive fields of the record to the consecutive elements of an array.                       |
| MATREADU                         | statement  | Sets an exclusive update lock on a record, then assigns the data stored in successive fields of the record to the consecutive elements of an array.                 |
| MATWRITE                         | statement  | Assigns the data stored in consecutive elements of an array to the successive fields of a record in a UniVerse file.                                                |
| MATWRITEU                        | statement  | Assigns the data stored in consecutive elements of an array to the successive fields of a record in a UniVerse file, retaining any update locks set on the record.  |
| OPEN                             | statement  | Opens a UniVerse file to be used in a BASIC program.                                                                                                                |
| OPENPATH                         | statement  | Opens a file to be used in a BASIC program.                                                                                                                         |
| PROCREAD                         | statement  | Assigns the contents of the primary input buffer of the proc to a variable.                                                                                         |
| PROCWRITE                        | statement  | Writes the specified string to the primary input buffer of the proc that called your BASIC program.                                                                 |
| READ                             | statement  | Assigns the contents of a record to a dynamic array variable.                                                                                                       |
| READL                            | statement  | Sets a shared read lock on a record, then assigns the contents of the record to a dynamic array variable.                                                           |
| READU                            | statement  | Sets an exclusive update lock on a record, then assigns the contents of the record to a dynamic array variable.                                                     |
| READV                            | statement  | Assigns the contents of a field of a record to a dynamic array variable.                                                                                            |
| READVL                           | statement  | Sets a shared read lock on a record, then assigns the contents of a field of a record to a dynamic array variable.                                                  |
| READVU                           | statement  | Sets an exclusive update lock on a record, then assigns the contents of a field of the record to a dynamic array variable.                                          |
| RECORDLOCKED                     | function   | Establishes whether or not a record is locked by a user.                                                                                                            |
| RECORDLOCKL                      | statement  | Sets a shared read-only lock on a record in a file.                                                                                                                 |
| RECORDLOCKU                      | statement  | Locks the specified record to prevent other users from accessing it.                                                                                                |
| RELEASE                          | statement  | Unlocks records locked by READL, READU, READVL, READVU, MATREADL, MATREADU, MATWRITEV, WRITEV, WRITEVU, RECORDLOCK. statements.                                     |
| ROLLBACK                         | statement  | Rolls back all changes made during a transaction. No changes are written to disk.                                                                                   |
| SET TRANSACTION ISOLATION LEVEL  | statement  | Sets the default transaction isolation level for your program.                                                                                                      |
| TRANS                            | function   | Returns the contents of a field in a record of a UniVerse file.                                                                                                     |
| TRANSACTION ABORT                | statement  | Discards changes made during a transaction. No changes are written to disk.                                                                                         |
| TRANSACTION COMMIT               | statement  | Commits all changes made during a transaction, writing them to disk.                                                                                                |
| TRANSACTION START                | statement  | Indicates the beginning of a set of statements that make up a single transaction.                                                                                   |
| WRITE                            | statement  | Replaces the contents of a record in a UniVerse file.                                                                                                               |
| WRITEU                           | statement  | Replaces the contents of the record in a UniVerse file without releasing the record lock                                                                            |
| WRITEV                           | statement  | Replaces the contents of a field of a record in a UniVerse file.                                                                                                    |
| WRITEVU                          | statement  | Replaces the contents of a field in the record without releasing the record lock.                                                                                   |
| XLATE                            | function   | Returns the contents of a field in a record of a UniVerse file.                                                                                                     |

## Sequential file I/O

The following table describes the Sequential File I/O statements.

| Command    | Type       | Description                                                                                                                      |
| -          | -          | -                                                                                                                                |
| CLOSESEQ   | statement  | Writes an end-of-file mark at the current location in the record and then makes the record available to other users.             |
| CREATE     | statement  | Creates a record in a UniVerse type 1 or type 19 file or establishes a path.                                                     |
| FLUSH      | statement  | Immediately writes all buffers.                                                                                                  |
| GET        | statement  | Reads a block of data from an input stream associated with a device, such as a serial line or terminal.                          |
| GETX       | statement  | Reads a block of data from an input stream associated with a device, and returns the characters in ASCII hexadecimal format.     |
| NOBUF      | statement  | Turns off buffering for a sequential file.                                                                                       |
| OPENSEQ    | statement  | Prepares a UniVerse file for sequential use by the BASIC program.                                                                |
| READBLK    | statement  | Reads a block of data from a UniVerse file open for sequential processing and assigns it to a variable.Printer and terminal I/O  |
| READSEQ    | statement  | Reads a line of data from a UniVerse file opened for sequential processing and assigns it to a variable.                         |
| SEEK       | statement  | tba                                                                                                                              |
| SEND       | statement  | Writes a block of data to a device that has been opened for I/O using OPENDEV or OPENSEQ.                                        |
| STATUS     | statement  | Determines the status of a UniVerse file.                                                                                        |
| TIMEOUT    | statement  | Terminates READSEQ or READBLK if no data is read in the specified time.                                                          |
| TTYCTL     | statement  | Controls sequential file interaction with a terminal device.                                                                     |
| TTYGET     | statement  | Gets a dynamic array of the terminal characteristics of a terminal, line printer channel, or magnetic tape channel.              |
| TTYSET     | statement  | Sets the terminal characteristics of a terminal, line printer channel, or magnetic tape channel.                                 |
| WEOFSEQ    | statement  | Writes an end-of-file mark to a UniVerse file open for sequential processing at the current position.                            |
| WRITEBLK   | statement  | Writes a block of data to a record in a sequential file.                                                                         |
| WRITESEQ   | statement  | Writes new values to the specified record of a UniVerse file sequentially.                                                       |
| WRITESEQF  | statement  | Writes new values to the specified record of a UniVerse file sequentially and ensures that the data is written to disk.          |

## Printer and terminal I/O

The following table describes the Printer and Terminal I/O functions and statements.

| Command        | Type       | Description                                                                                                                         |
| -              | -          | -                                                                                                                                   |
| @()            | function   | Returns an escape sequence used for terminal control.                                                                               |
| BREAK          | statement  | Enables or disables the Break key on the keyboard.                                                                                  |
| CLEARDATA      | statement  | Clears all data previously stored by the DATA statement.                                                                            |
| CRT            | statement  | Outputs data to the screen.                                                                                                         |
| DATA           | statement  | Stores values to be used in subsequent requests for data input.                                                                     |
| DISPLAY        | statement  | Outputs data to the screen.                                                                                                         |
| ECHO           | statement  | Controls the display of input characters on the terminal screen.                                                                    |
| FOOTING        | statement  | Specifies text to be printed at the bottom of each page.                                                                            |
| HEADING        | statement  | Specifies text to be printed at the top of each page.                                                                               |
| HUSH           | statement  | Suppresses all text normally sent to a terminal during processing.                                                                  |
| INPUT          | statement  | Allows data input from the keyboard during program execution.                                                                       |
| INPUT @        | statement  | Positions the cursor at a specified location and defines the length of the input field.                                             |
| INPUTCLEAR     | statement  | Clears the type-ahead buffer.                                                                                                       |
| INPUTDISP      | statement  | Positions the cursor at a specified location and defines a format for the variable to print.                                        |
| INPUTERR       | statement  | Prints a formatted error message from the ERRMSG file on the bottom line of the terminal.                                           |
| INPUTNULL      | statement  | Defines a single character to be recognized as the empty string in an                                                               |
| INPUTTRAP      | statement  | Branches to a program label or subroutine on a TRAP key.                                                                            |
| KEYEDIT        | statement  | Assigns specific editing functions to the keys on the keyboard to be used with the INPUT statement.                                 |
| KEYEXIT        | statement  | Specifies exit traps for the keys assigned editing functions by the                                                                 |
| KEYEDIT        | statement  | .                                                                                                                                   |
| KEYIN          | function   | Reads a single character from the input buffer and returns it.                                                                      |
| KEYTRAP        | statement  | Specifies traps for the keys assigned specific functions by the KEYEDIT statement.                                                  |
| OPENDEV        | statement  | Opens a device for input or output.                                                                                                 |
| $PAGE          | statement  | Prints a footing at the bottom of the page, advances to the next page, and prints a heading at the top.                             |
| PRINT          | statement  | Outputs data to the terminal screen or to a printer.                                                                                |
| PRINTER CLOSE  | statement  | Indicates the completion of a print file and readiness for the data stored in the system buffer to be printed on the line printer.  |
| PRINTER ON/OFF | statement  | Indicates whether print file 0 is to output to the terminal screen or to the line printer.                                          |
| PRINTER RESET  | statement  | Resets the printing options.                                                                                                        |
| PRINTERR       | statement  | Prints a formatted error message from the ERRMSG file on the bottom line of the terminal.                                           |
| PROMPT         | statement  | Defines the prompt character for user input.                                                                                        |
| TABSTOP        | statement  | Sets the current tabstop width for PRINT statements.                                                                                |
| TERMINFO       | function   | Accesses the information contained in the terminfo files.                                                                           |
| TPARM          | function   | Evaluates a parameterized terminfo string.                                                                                          |
| TPRINT         | statement  | Sends data with delays to the screen, a line printer, or another specified print file (that is, a logical printer).                 |

## Tape I/O

The following table describes the Tape I/O statements.

| Command  | Type       | Description                                                                               |
| -        | -          | -                                                                                         |
| READT    | statement  | Assigns the contents of the next record from a magnetic tape unit to the named variable.  |
| REWIND   | statement  | Rewinds the magnetic tape to the beginning of the tape.                                   |
| WEOF     | statement  | Writes an end-of-file mark to a magnetic tape.                                            |
| WRITET   | statement  | Writes the contents of a record onto magnetic tape.                                       |

## Select lists

The following table describes Select Lists functions and statements.

| Command      | Type       | Description                                                                                                                                                          |
| -            | -          | -                                                                                                                                                                    |
| CLEARSELECT  | statement  | Sets a select list to empty.                                                                                                                                         |
| DELETELIST   | statement  | Deletes a select list saved in the &SAVEDLISTS& file.String handling                                                                                                 |
| GETLIST      | statement  | Activates a saved select list so it can be used by a READNEXT statement.                                                                                             |
| READLIST     | statement  | Assigns an active select list to a variable.                                                                                                                         |
| READNEXT     | statement  | Assigns the next record ID from an active select list to a variable.                                                                                                 |
| SELECT       | statement  | Creates a list of all record IDs in a UniVerse file for use by a subsequent READNEXT statement. SELECT, SELECTN, and SELECTV are included in the SELECT statements.  |
| SELECTE      | statement  | Assigns the contents of select list 0 to a variable.                                                                                                                 |
| SELECTINDEX  | statement  | Creates select lists from secondary key indexes.                                                                                                                     |
| SELECTINFO   | function   | Returns the activity status of a select list.                                                                                                                        |
| SSELECT      | statement  | Creates a sorted list of all record IDs from a UniVerse file.                                                                                                        |
| WRITELIST    | statement  | Saves a list as a record in the &SAVEDLISTS& file.                                                                                                                   |

## String handling

The following table describes the String Handling functions and statements.

| Command     | Type       | Description                                                                                                                                                                           |
| -           | -          | -                                                                                                                                                                                     |
| ALPHA       | function   | Determines whether the expression is an alphabetic or non-alphabetic string.                                                                                                          |
| CATS        | function   | Concatenates elements of two dynamic arrays.                                                                                                                                          |
| CHANGE      | function   | Substitutes an element of a string with a replacement element.                                                                                                                        |
| CHECKSUM    | function   | Returns a cyclical redundancy code (a checksum value).                                                                                                                                |
| COL1        | function   | Returns the column position immediately preceding the selected substring after a BASIC FIELD function is executed.                                                                    |
| COL2        | function   | Returns the column position immediately following the selected substring after a BASIC FIELD function is executed.                                                                    |
| COMPARE     | function   | Compares two strings for sorting.                                                                                                                                                     |
| CONVERT     | statement  | Converts specified characters in a string to designated replacement characters.                                                                                                       |
| CONVERT     | function   | Replaces every occurrence of specified characters in a variable with other specified characters.                                                                                      |
| COUNT       | function   | Evaluates the number of times a substring is repeated in a string.                                                                                                                    |
| COUNTS      | function   | Evaluates the number of times a substring is repeated in each element of a dynamic array.                                                                                             |
| DCOUNT      | function   | Evaluates the number of delimited fields contained in a string.                                                                                                                       |
| DEL         | statement  | Deletes the specified field, value, or subvalue from a dynamic array.                                                                                                                 |
| DELETE      | function   | Deletes a field, value, or subvalue from a dynamic array.                                                                                                                             |
| DOWNCASE    | function   | Converts all uppercase letters in an expression to lowercase.                                                                                                                         |
| DQUOTE      | function   | Encloses an expression in double quotation marks.                                                                                                                                     |
| EREPLACE    | function   | Substitutes an element of a string with a replacement element.                                                                                                                        |
| EXCHANGE    | function   | Replaces one character with another or deletes all occurrences of a specific character.                                                                                               |
| EXTRACT     | function   | Extracts the contents of a specified field, value, or subvalue from a dynamic array.                                                                                                  |
| FIELD       | function   | Examines a string expression for any occurrence of a specified delimiter and returns a substring that is marked by that delimiter.                                                    |
| FIELDS      | function   | Examines each element of a dynamic array for any occurrence of a specified delimiter and returns substrings that are marked by that delimiter.                                        |
| FIELDSTORE  | function   | Replaces, deletes, or inserts substrings in a specified character string.                                                                                                             |
| FIND        | statement  | Locates a given occurrence of an element within a dynamic array.                                                                                                                      |
| FINDSTR     | statement  | Locates a given occurrence of a substring.                                                                                                                                            |
| FOLD        | function   | Divides a string into a number of shorter sections.                                                                                                                                   |
| GETREM      | function   | Returns the numeric value for the position of the REMOVE pointer associated with a dynamic array.                                                                                     |
| GROUP       | function   | Returns a substring that is located between the stated number of occurrences of a delimiter.                                                                                          |
| GROUPSTORE  | statement  | Modifies existing character strings by inserting, deleting, or replacing substrings that are separated by a delimiter character.                                                      |
| INDEX       | function   | Returns the starting column position of a specified occurrence of a particular substring within a string expression.                                                                  |
| INDEXS      | function   | Returns the starting column position of a specified occurrence of a particular substring within each element of a dynamic array.                                                      |
| INS         | statement  | Inserts a specified field, value, or subvalue into a dynamic array.                                                                                                                   |
| INSERT      | function   | Inserts a field, value, or subvalue into a dynamic array.                                                                                                                             |
| LEFT        | function   | Specifies a substring consisting of the first n characters of a string.                                                                                                               |
| LEN         | function   | Calculates the length of a string.                                                                                                                                                    |
| LENS        | function   | Calculates the length of each element of a dynamic array.                                                                                                                             |
| LOCATE      | statement  | (IDEAL and REALITY syntax) Searches a dynamic array for a particular value or string, and returns the index of its position.                                                          |
| LOWER       | function   | Converts system delimiters that appear in expressions to the next lower-level delimiter.                                                                                              |
| MATBUILD    | statement  | Builds a string by concatenating the elements of an array.                                                                                                                            |
| MATCHFIELD  | function   | Returns the contents of a substring that matches a specified pattern or part of a pattern.                                                                                            |
| MATPARSE    | statement  | Assigns the elements of an array from the elements of a dynamic array.                                                                                                                |
| QUOTE       | function   | Encloses an expression in double quotation marks.                                                                                                                                     |
| RAISE       | function   | Converts system delimiters that appear in expressions to the next higher-level delimiter.                                                                                             |
| REMOVE      | statement  | Removes substrings from a dynamic array.                                                                                                                                              |
| REMOVE      | function   | Successively removes elements from a dynamic array. Extracts successive fields, values, etc., for dynamic array processing.                                                           |
| REVREMOVE   | statement  | Successively removes elements from a dynamic array, starting from the last element and moving right to left. Extracts successive fields, values, etc., for dynamic array processing.  |
| REPLACE     | function   | Replaces all or part of the contents of a dynamic array.                                                                                                                              |
| REUSE       | function   | Reuses the last value in the shorter of two multivalue lists in a dynamic array operation.                                                                                            |
| RIGHT       | function   | Specifies a substring consisting of the last n characters of a string.Data conversion and formatting                                                                                  |
| SETREM      | statement  | Sets the position of the REMOVE pointer associated with a dynamic array.                                                                                                              |
| SOUNDEX     | function   | Returns the soundex code for a string.                                                                                                                                                |
| SPACE       | function   | Generates a string consisting of a specified number of blank spaces.                                                                                                                  |
| SPACES      | function   | Generates a dynamic array consisting of a specified number of blank spaces for each element.                                                                                          |
| SPLICE      | function   | Inserts a string between the concatenated values of corresponding elements of two dynamic arrays.                                                                                     |
| SQUOTE      | function   | Encloses an expression in single quotation marks.                                                                                                                                     |
| STR         | function   | Generates a particular character string a specified number of times.                                                                                                                  |
| STRS        | function   | Generates a dynamic array whose elements consist of a character string repeated a specified number of times.                                                                          |
| SUBSTRINGS  | function   | Creates a dynamic array consisting of substrings of the elements of another dynamic array.                                                                                            |
| TRIM        | function   | Deletes extra blank spaces and tabs from a character string.                                                                                                                          |
| TRIMB       | function   | Deletes all blank spaces and tabs after the last non-blank character in an expression.                                                                                                |
| TRIMBS      | function   | Deletes all trailing blank spaces and tabs from each element of a dynamic array.                                                                                                      |
| TRIMF       | function   | Deletes all blank spaces and tabs up to the first non-blank character in an expression.                                                                                               |
| TRIMFS      | function   | Deletes all leading blank spaces and tabs from each element of a dynamic array.                                                                                                       |
| TRIMS       | function   | Deletes extra blank spaces and tabs from the elements of a dynamic array.                                                                                                             |
| UPCASE      | function   | Converts all lowercase letters in an expression to uppercase.                                                                                                                         |

## Data conversion and formatting

The following table describes the Data Conversion and Formatting functions and statements.

| Command    | Type       | Description                                                                                                                                           |
| -          | -          | -                                                                                                                                                     |
| ASCII      | function   | Converts EBCDIC representation of character string data to the equivalent ASCII character code values.                                                |
| CHAR       | function   | Converts a numeric value to its ASCII character string equivalent.                                                                                    |
| CHARS      | function   | Converts numeric elements of a dynamic array to their ASCII character string equivalents.                                                             |
| DTX        | function   | Converts a decimal integer into its hexadecimal equivalent.                                                                                           |
| EBCDIC     | function   | Converts data from its ASCII representation to the equivalent code value in EBCDIC.                                                                   |
| FIX        | function   | Rounds an expression to a decimal number having the accuracy specified by the PRECISION statement.                                                    |
| FMT        | function   | Converts data from its internal representation to a specified format for output.                                                                      |
| FMTS       | function   | Converts elements of a dynamic array from their internal representation to a specified format for output.                                             |
| ICONV      | function   | Converts data to internal storage format.                                                                                                             |
| ICONVS     | function   | Converts elements of a dynamic array to internal storage format.                                                                                      |
| OCONV      | function   | Converts data from its internal representation to an external output format.                                                                          |
| OCONVS     | function   | Converts elements of a dynamic array from their internal representation to an external output format.                                                 |
| PRECISION  | statement  | Sets the maximum number of decimal places allowed in the conversion from the internal binary format of a numeric value to the string representation.  |
| SEQ        | function   | Converts an ASCII character code value to its corresponding numeric value.                                                                            |
| SEQS       | function   | Converts each element of a dynamic array from an ASCII character code to a corresponding numeric value.                                               |
| XTD        | function   | Converts a hexadecimal string into its decimal equivalent.                                                                                            |

## NLS

The following table describes the NLS functions and statements.

| Command     | Type       | Description                                                                                                                 |
| -           | -          | -                                                                                                                           |
| $MAP        | statement  | Directs the compiler to specify the map for the source code.                                                                |
| AUXMAP      | statement  | Assigns the map for the auxiliary printer to print unit 0 (i.e., the terminal).                                             |
| BYTE        | function   | Generates a string made up of a single byte.                                                                                |
| BYTELEN     | function   | Generates the number of bytes contained in the string value in an expression.                                               |
| BYTETYPE    | function   | Determines the function of a byte in a character.                                                                           |
| BYTEVAL     | function   | Retrieves the value of a byte in a string value in an expression.                                                           |
| FMTDP       | function   | Formats data for output in display positions rather than character lengths.                                                 |
| FMTSDP      | function   | Formats elements of a dynamic array for output in display positions rather than character lengths.                          |
| FOLDDP      | function   | Divides a string into a number of substrings separated by field marks, in display positions rather than character lengths.  |
| GETLOCALE   | function   | Retrieves the names of specified categories of the current locale.                                                          |
| INPUTDISP   | statement  | Lets the user enter data in display positions rather than character lengths.                                                |
| LENDP       | function   | Returns the number of display positions in a string.                                                                        |
| LENSDP      | function   | Returns a dynamic array of the number of display positions in each element of a dynamic array.                              |
| LOCALEINFO  | function   | Retrieves the settings of the current locale.                                                                               |
| SETLOCALE   | function   | Changes the setting of one or all categories for the current locale.                                                        |
| UNICHAR     | function   | Generates a character from a Unicode integer value.                                                                         |
| UNICHARS    | function   | Generates a dynamic array from an array of Unicode values.                                                                  |
| UNISEQ      | function   | Generates a Unicode integer value from a character.                                                                         |
| UNISEQS     | function   | Generates an array of Unicode values from a dynamic array.Mathematical functions                                            |
| UPRINT      | statement  | Prints data without performing any mapping. Typically used with data that has already been mapped using OCONV (mapname).    |

## Mathematical functions

The following table describes mathematical functions and statements

| Command    | Type       | Description                                                                                                                                  |
| -          | -          | -                                                                                                                                            |
| ABS        | function   | Returns the absolute (positive) numeric value of an expression.                                                                              |
| ABSS       | function   | Creates a dynamic array containing the absolute values of a dynamic array.                                                                   |
| ACOS       | function   | Calculates the trigonometric arc-cosine of an expression.                                                                                    |
| ADDS       | function   | Adds elements of two dynamic arrays.                                                                                                         |
| ASIN       | function   | Calculates the trigonometric arc-sine of an expression.                                                                                      |
| ATAN       | function   | Calculates the trigonometric arctangent of an expression.                                                                                    |
| BITAND     | function   | Performs a bitwise AND of two integers.                                                                                                      |
| BITNOT     | function   | Performs a bitwise NOT of two integers.                                                                                                      |
| BITOR      | function   | Performs a bitwise OR of two integers.                                                                                                       |
| BITRESET   | function   | Resets one bit of an integer.                                                                                                                |
| BITSET     | function   | Sets one bit of an integer.                                                                                                                  |
| BITTEST    | function   | Tests one bit of an integer.                                                                                                                 |
| BITXOR     | function   | Performs a bitwise XOR of two integers.                                                                                                      |
| COS        | function   | Calculates the trigonometric cosine of an angle.                                                                                             |
| COSH       | function   | Calculates the hyperbolic cosine of an expression.                                                                                           |
| DIV        | function   | Outputs the whole part of the real division of two real numbers.                                                                             |
| DIVS       | function   | Divides elements of two dynamic arrays.                                                                                                      |
| EXP        | function   | Calculates the result of base "e" raised to the power designated by the value of the expression.                                             |
| INT        | function   | Calculates the integer numeric value of an expression.                                                                                       |
| FADD       | function   | Performs floating-point addition on two numeric values. This function is provided for compatibility with existing software.                  |
| FDIV       | function   | Performs floating-point division on two numeric values.                                                                                      |
| FFIX       | function   | Converts a floating-point number to a string with a fixed precision. FFIX is provided for compatibility with existing software.              |
| FFLT       | function   | Rounds a number to a string with a precision of 14.                                                                                          |
| FMUL       | function   | Performs floating-point multiplication on two numeric values. This function is provided for compatibility with existing software.            |
| FSUB       | function   | Performs floating-point subtraction on two numeric values.                                                                                   |
| LN         | function   | Calculates the natural logarithm of an expression in base "e".                                                                               |
| MAXIMUM    | function   | Returns the element with the highest numeric value in a dynamic array.                                                                       |
| MINIMUM    | function   | Returns the element with the lowest numeric value in a dynamic array.                                                                        |
| MOD        | function   | Calculates the modulo (the remainder) of two expressions.                                                                                    |
| MODS       | function   | Calculates the modulo (the remainder) of elements of two dynamic arrays.                                                                     |
| MULS       | function   | Multiplies elements of two dynamic arrays.                                                                                                   |
| NEG        | function   | Returns the arithmetic additive inverse of the value of the argument.                                                                        |
| NEGS       | function   | Returns the negative numeric values of elements in a dynamic array. If the value of an element is negative, the returned value is positive.  |
| NUM        | function   | Returns true (1) if the argument is a numeric data type; otherwise, returns false (0).                                                       |
| NUMS       | function   | Returns true (1) for each element of a dynamic array that is a numeric data type; otherwise, returns false (0).                              |
| PWR        | function   | Calculates the value of an expression when raised to a specified power.                                                                      |
| RANDOMIZE  | statement  | Initializes the RND function to ensure that the same sequence of random numbers is generated after initialization.                           |
| REAL       | function   | Converts a numeric expression into a real number without loss of accuracy.                                                                   |
| REM        | function   | Calculates the value of the remainder after integer division is performed.                                                                   |
| RND        | function   | Generates a random number between zero and a specified number minus one.                                                                     |
| SADD       | function   | Adds two string numbers and returns the result as a string number.                                                                           |
| SCMP       | function   | Compares two string numbers.                                                                                                                 |
| SDIV       | function   | Outputs the quotient of the whole division of two integers.                                                                                  |
| SIN        | function   | Calculates the trigonometric sine of an angle.                                                                                               |
| SINH       | function   | Calculates the hyperbolic sine of an expression.                                                                                             |
| SMUL       | function   | Multiplies two string numbers.                                                                                                               |
| SQRT       | function   | Calculates the square root of a number.                                                                                                      |
| SSUB       | function   | Subtracts one string number from another and returns the result as a string number.                                                          |
| SUBS       | function   | Subtracts elements of two dynamic arrays.                                                                                                    |
| SUM        | function   | Calculates the sum of numeric data within a dynamic array.                                                                                   |
| SUMMATION  | function   | Adds the elements of a dynamic array.                                                                                                        |
| TAN        | function   | Calculates the trigonometric tangent of an angle.                                                                                            |
| TANH       | function   | Calculates the hyperbolic tangent of an expression.                                                                                          |

## Relational functions

The following table describes the Relational functions.

| Command  | Type      | Description                                                                                                                 |
| -        | -         | -                                                                                                                           |
| ANDS     | function  | Performs a logical AND on elements of two dynamic arrays.                                                                   |
| EQS      | function  | Compares the equality of corresponding elements of two dynamic arrays.System                                                |
| GES      | function  | Indicates when elements of one dynamic array are greater than or equal to corresponding elements of another dynamic array.  |
| GTS      | function  | Indicates when elements of one dynamic array are greater than corresponding elements of another dynamic array.              |
| IFS      | function  | Evaluates a dynamic array and creates another dynamic array on the basis of the truth or falsity of its elements.           |
| ISNULL   | function  | Indicates when a variable is the null value.                                                                                |
| ISNULLS  | function  | Indicates when an element of a dynamic array is the null value.                                                             |
| LES      | function  | Indicates when elements of one dynamic array are less than or equal to corresponding elements of another dynamic array.     |
| LTS      | function  | Indicates when elements of one dynamic array are less than corresponding elements of another dynamic array.                 |
| NES      | function  | Indicates when elements of one dynamic array are not equal to corresponding elements of another dynamic array.              |
| NOT      | function  | Returns the complement of the logical value of an expression.                                                               |
| NOTS     | function  | Returns the complement of the logical value of each element of a dynamic array.                                             |
| ORS      | function  | Performs a logical OR on elements of two dynamic arrays.                                                                    |

## System

The following table describes the System functions and statements.

| Command     | Type       | Description                                                                                                                                                                                                     |
| -           | -          | -                                                                                                                                                                                                               |
| DATE        | function   | Returns the internal system date.                                                                                                                                                                               |
| DATETIMEL   | function   | Returns the local date and time in microseconds in a human readable format. Note: This function is supported on Linux and Solaris platforms only.                                                               |
| DATETIMEZ   | function   | Returns the UTC date and time in microseconds in a human readable format. Note: This function is supported on Linux and Solaris platforms only.                                                                 |
| DEBUG       | statement  | Invokes RAID, the interactive UniVerse BASIC debugger.                                                                                                                                                          |
| ERRMSG      | statement  | Prints a formatted error message from the ERRMSG file.                                                                                                                                                          |
| GCDISTANCE  | function   | Calculates the great-circle distance (in meters) between two points on the surface of Earth.                                                                                                                    |
| INMAT       | function   | Used with the MATPARSE, MATREAD, and MATREADU statements to return the number of array elements or with the OPEN statement to return the modulo of a file.                                                      |
| ITYPE       | function   | Returns the value resulting from the evaluation of an I-descriptor.                                                                                                                                             |
| LOCK        | statement  | Sets an execution lock to protect user-defined resources or events from being used by more than one concurrently running program.                                                                               |
| NAP         | statement  | Suspends execution of a BASIC program, pausing for a specified number of milliseconds.                                                                                                                          |
| NOW         | function   | Returns the numeric value of the internal datetime value. Note: This function is supported on Linux and Solaris platforms only.                                                                                 |
| SENTENCE    | function   | Returns the stored sentence that invoked the current process.                                                                                                                                                   |
| SLEEP       | statement  | Suspends execution of a BASIC program, pausing for a specified number of seconds.                                                                                                                               |
| STATUS      | function   | Reports the results of a function or statement previously executed.                                                                                                                                             |
| SYSTEM      | function   | Checks the status of a system function.                                                                                                                                                                         |
| TIME        | function   | Returns the time in internal format.                                                                                                                                                                            |
| TIMEDATE    | function   | Returns the time and date.                                                                                                                                                                                      |
| TODATE      | function   | Converts the internal datetime value to the internal local date value. Note: This function is supported on Linux and Solaris platforms only.                                                                    |
| TODATETIME  | function   | Converts the internal values of the local date and time (as returned by the DATE() and TIME() functions) to the internal datetime value. Note: This function is supported on Linux and Solaris platforms only.  |
| TOTIME      | function   | Converts the internal datetime value to the internal local time value. Note: This function is supported on Linux and Solaris platforms only.                                                                    |
| UNLOCK      | statement  | Releases an execution lock that was set with the LOCK statement.                                                                                                                                                |
| USERINFO    | function   | Gets the pid, user number, and more for the pid or user number specified.                                                                                                                                       |

## Remote procedure calls

The following table describes Remote Procedure Call functions.

| Command         | Type      | Description                                             |
| -               | -         | -                                                       |
| RPC.CALL        | function  | Sends requests to a remote server.                      |
| RPC.CONNECT     | function  | Establishes a connection with a remote server process.  |
| RPC.DISCONNECT  | function  | Disconnects from a remote server process.               |

## Miscellaneous

The following table describes Miscellaneous functions and statements.

| Command       | Type       | Description                                                                               |
| -             | -          | -                                                                                         |
| CLEARPROMPTS  | statement  | Clears the value of the in-line prompt.                                                   |
| EOF(ARG.)     | function   | Checks whether the command line argument pointer is past the last command line argument.  |
| FILEINFO      | function   | Returns information about the specified file’s configuration.                             |
| ILPROMPT      | function   | Evaluates strings containing in-line prompts.                                             |
| GET(ARG.)     | statement  | Retrieves a command line argument.                                                        |
| SEEK(ARG.)    | statement  | Moves the command line argument pointer.                                                  |
