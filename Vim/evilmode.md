 # Vim tutor notes

**Lesson 1**

- Move Around with J/down K/up H/left L/right
- To delete the character you are standing on in normal mode press x
- To insert text while in normal mode press i. To exit press esc

**Lesson 2**

- To delete a word while in normal mode press dw. A similar command is de except it will preserve the spaces when deleting
- To delete to the end of the line press d$
- The delete command can be exectued numerous times in a row by typing the number before or after d. Eg. 3dw/d3w will delete the next 3 words and the spaces.
- To delete a whole line type dd. Remember you can delete multiple lines by using numbers.
- If you mess up while inserting or deleting text, you can undo by pressing u.
- You can also redo an undo by pressing ctrl-r.

**Lesson 3** // things are getting a bit more complex here

- To insert the last deleted word/line press p.
- To replace a character press r and type your new character.
- To change a word press cw. Eg To correct "speluyg" to "spelling" we would place the cursor on u, press cw and type "ling".
- To change until the end of the line press c$.
- The change (c) command works in the same way as the delete command (d), you can add numbers to iterate multiple times. Eg. 3cw/c3w changes the next 3 words.

**Lesson 4**

- Press G to go to the bottom of a buffer (document).
- Press gg to go to the beggining of a buffer.
- Press :followedbyanumber to go to a specific line. Eg. to go to this line we would press :30.
- Press / followed by a word/phrase and enter to search this in your buffer. After you can keep searching the same word forward by using n and backwards with N. 
- If you want to search for a word/phrase in the backwards direction use ?.
- To find an ending/opening ({[]}) press % while on the starting closing one. You can also press it again to go to the back to the original ({[]}).
- We can use :s to substitute, on the correct line, usage for 1 word goes like so :s/wordreplaced/newword. This can be extended in several ways: We can add /g at the end to replace that word everytime on that line. 
