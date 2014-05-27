Title: Literary Demo Doc
Author: You!
Date: Now

# Literary Demonstrations

Verily and forsooth, this document shall endeavor to set forth all manner of rightful features to demonstrate unto thee the full power of vim and MultiMarkdown combined. So let's throw in some footnotes[^ I really like footnotes. I use footnotes basically everywhere] and while we're at it let's include a table:

| Words!  | Meanings? |  
|  ------ | ------  |  
| Bob | A person  |  
| Why?  | A question  |  
| World | Round!  |  

And that's about all we have to say about that. 

But fear not! Lest you worry that this document is all fluff and no stuff (AFNS) here's some actually useful information!

## Writer Friendly Plugins

Once you’ve got vim outfitted with a Markdown syntax file and line wrapping you are pretty much good to go. But let me share with you one gem that I have found, and a way to make it really sparkle if you’re using MultiMarkdown in your writing.

You see, one of the (many) benefits that comes with using MultiMarkdown over regular Markdown is the ability to create tables. You can format data

	|  Like  |  this |  
	|  ------ | ------  |   
	| And |  it | 
	| Becomes |  a  | 
	| Table |  !  | 


Which gives you something like this:

| Like  |  this |  
|  ------ | ------  |   
| And |  it | 
| Becomes |  a  | 
| Table |  !  | 


Which is awesome. But in your source file it’s kinda messy. We can fix that with a plugin. 

[Tabular](https://github.com/godlygeek/tabular) is that plugin. It's a simple enough little beast. Install it using Pathogen and then start up vim. Remember to run `:Helptags` so that Pathogen will import the help file for Tabular, although it's pretty simple.

*Anyway* Tabular lets you line things up so they look nice and neat. the way you do this is type 
`:Tab /` and then the character that needs to be lined up. In this case we want all the pipe symbols (`|`) to line up in our tables, so we would  type `:Tab /|` and suddenly our table looks 

    | Like    | this   |
    | ------  | ------ |
    | And     | it     |
    | Becomes | a      |
    | Table   | !      |
  
Which is nice, because you spend a lot of time reading and editing your source Markdown files, and having them all clean like that makes them much easier to scan. 

But wait, there's more! (there's always more). You can assign this to a `<leader>` key command, so you can line up your tables with just a couple of keys instead of a huge and hard to remember command. 

I would suggest adding lines like the following to your `.vimrc`:
 
	if exists(":Tabularize")
    	vmap <leader>at :Tabularize /\|<CR>
    	nmap <leader>at :Tabularize /\|<CR>
	endif


In this you use the long form of the `:Tabularize` command because you don't have to type it out and this way it ensures that it won't interfere with any other plugin that might want to use the `:Tab` shortcut someday. Incidentally, when you use the `|` character in key maps like this you have to escape it with the backslash, which is why it says `:Tabularize /\|` where earlier I just typed `:Tab /|`. I learned that the hard way.

If you're a programmer you could update that block to look like this:

	if exists(":Tabularize")
    	vmap <leader>at :Tabularize /\|<CR>
    	nmap <leader>at :Tabularize /\|<CR>
    	vmap <leader>a= :Tabularize /=<CR>
    	nmap <leader>a= :Tabularize /=<CR>

	endif

Which will allow you to line up assignments in programs:

	var a = 1;
	var bb = 4;
	var frog =12;

becomes

	var a    = 1;
	var bb   = 4
	var frog = 12;

So, there you go! All kinds of information about a very useful plugin, tucked away nicely in this practice file! 