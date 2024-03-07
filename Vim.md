## To search for an expression just type the / key and then your search result while you are in a vim session. 
## Once you hit enter, you can press "n" to go forward or "N" to go backward in your search results.

    The ? search command will search the text file backwards, so in the previous example, the last pretty would come up first.
    Now you may notice, the mouse is nowhere is use here. To navigate a text document in vim, use the following keys:

    h or the left arrow - will move you left one character
    k or the up arrow - will move you up one line
    j or the down arrow - will move you down one line
    l or the right arrow - will move you right one character

    i - insert text before the cursor
    O - insert text on the previous line
    o - insert text on the next line
    a - append text after the cursor
    A - append text at the end of the line

    x - used to cut the selected text also used for deleting characters
    dd - used to delete the current line
    y - yank or copy whatever is selected
    yy - yank or copy the current line
    p - paste the copied text before the cursor

## Editing Options for editor
    :w - writes or saves the file
    :q - quit out of vim
    :wq - write and then quit
    :q! - quit out of vim without saving the file
    ZZ - equivalent of :wq, but one character faster

    u - undo your last action
    Ctrl-r - redo your last action

You may not think ZZ is necessary, but you'll eventually see that your fingers may tend to lean towards this rather than :wq.
