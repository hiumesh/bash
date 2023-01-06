## Multi Line And Command

To write command in multiple line use **'\\'** just before pressing enter key
```sh
cp -i \
from/file/location \
destination/file/location
``` 

To run multiple commands in a sequence use **';' or '&&'**
```sh
ls ; date ; who
ls && date && who
```
EXECUTION SEQUENCE: ls -> date -> who <br>
**Note:** ';' will the run the next command even if previous command fail wherease '&&' will stop the executing further commands ones any command throw error

## Keyboard Shortcuts

| Movement Commands | Operation                          |
| :---------------- | :--------------------------------- |
| CTRL-A or HOME    | Move to beginning of line          |
| CTRL-E or END     | Move to end of line                |
| ALT-F             | Move forward a word                |
| ALT-B             | Move backward a word               |
| CTRL-L            | Clear screen and place line at top |


| Editing Commands | Operation                                      |
| :--------------- | :--------------------------------------------- |
| CTRL-D or DEL    | Delete character cursor is on                  |
| CTRL-K           | Cut remainder of line from cursor position     |
| CTRL-U           | Cut from cursor position to beginning of line  |
| CTRL-W           | Cut previous word                              |
| CTRL-C           | Cut entire line                                |
| CTRL-D           | Cut the remainder of a word                    |
| CTRL-DEL         | Cut from the cursor to the beginning of a word |
| CTRL-Y           | Paste previous cut text                        |
| ALT-Y            | Paste from set of previously cut text          |
| CTRL-V           | Insert quoted text                             |
| ALT-T            | Transpose current and previous word            |
| ALT-L            | Lowercase current word                         |
| ALT-U            | Uppercase current word                         |
| ALT-C            | Capitalize current word                        |
| CTRL-SHIFT-_     | Undo pervious changes                          |


| Auto Complete Commands | Operation                                          |
| :--------------------- | :------------------------------------------------- |
| TAB                    | Automatic completion                               |
| TAB TAB or ESC         | List possible completions                          |
| ALT-/, CTRL-R-/        | Filename completion, normal text for automatic     |
| ALT-$, CTRL-R-$        | Shell variable completion $ for automatic          |
| ALT-~, CTRL-R-~        | Username completion, ~ for automatic               |
| ALT-@, CTRL-R-@        | Host name completion, @ for automatic              |
| ALT-!, CTRL-R-!        | Command name completion, normal text for automatic |

| History Commands       | Desciption                                                     |
| :--------------------- | :------------------------------------------------------------- |
| ALT-<                  | Move to the beginning of the history event list                |
| ALT->                  | Move to the end of the history event list                      |
| ALT-N                  | Forward search, next matching item                             |
| ALT-P                  | Backward search, previous matching item                        |
| CTRL-S                 | Forward search history, forward incremental search             |
| CTRL-R                 | Reverse search history, reverse incremental search             |
| fc **event-reference** | Edits an event with the standarad editor and then executes it. |

| History Event Reference | Desciption                                                  |
| :---------------------- | :---------------------------------------------------------- |
| **!** eventnum          | References an event by its event number                     |
| **!!**                  | References the previous command                             |
| **!** characters        | References an event beginning with the specified characters |
| **! ?** pattern **?**   | References an event containing the specified pattern        |
| **! -** event num        | References an event with an offset from the first event     |
| **!** num-num           | References a range of events                                |