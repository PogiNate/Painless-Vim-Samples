Visual mode!

Let's explore some ways you can use visual mode to select and maniuplate different blocks of text. 

## Characterwise

In characterwise visual mode you can move the cursor to add or remove text from the selection with all the standard movement keys. Once you've selected the text you want to change you can issue the command to change it. Let's try it on the following sentence:

All work and no play makes Jack a dull dull dull boy.

Remove two copies of the word "dull" by positioning your cursor at the start of one of them, then do the following:

1. hit `v` to enter visual mode. The status bar down below should say `-- VISUAL --` where it often says `-- INSERT --`
2. you can use pretty much ANY movement key you want to add to your text. if you are at the start of the first "dull" you can hit `w` to select the entire first word, and then use `e` to grab just to the end of the next.
3. Hit `d` to remove the selected text.


## Linewise

There are no real surprises here. The only thing you should remember is that in Linewise mode you can't use `h` or `l` to widen or narrow your selection, you can only select *entire lines*. That's why it's called "linewise mode".


Let's play with it, though. Replace the two lines in the middle of the following block with something useful:

Step 1: Buy lots of cats
Step 2: ???
Step 3: ???
Step 4: Profit!

Once you've figured out the middle section free to email me so I can...uh...check your work.

## Block Select
