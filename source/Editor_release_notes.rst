The new Pine Script™ Editor is here! 
This is a list of the **new** features added to the editor, and a few of the **changes** made.


New features
^^^^^^^^^^^^^

There are many new options and commands available using the new Command Palette. You can access this by either right-clicking in the editor itself or pressing ``F1``. 
Either you can scroll through all the new options or use keywords to use the new search function.

The new editor is now fully accessible on mobile devices! If your device doesn't support showing the Pine Script™ editor by default, 
you can either view the page in Desktop mode or access it by clicking on the detached editor link.

There is now complete documentation for all built-in functions and their parameters. 
This new feature even works for exported `library <https://www.tradingview.com/pine-script-reference/v5/#fun_library>`__ functions as well as the 
functions and variables declared in the current script, provided that they use the ``//@function``, ``//@param``, and ``//@returns`` annotations.

A new Autocomplete feature has now been added in a helpful popup to give you a list of possible keywords that will help make writing Pine Script™ faster and easier. 
This new feature will also display the full descriptions and examples for each keyword, 
and it works with any custom functions and variables if they use the ``//@function``, ``//@param``, and ``//@returns`` annotations.

The editor can now provide real-time errors and warnings, so you won't need to add the script to your chart to view any potential errors or warnings. 
Lines of code that will produce an error are now underlined in red or orange if they will create a warning.

Lines of code that are indented or wrapped around can now be minimized by using the new Fold function ``(Ctrl + Shift + L)``. 
You can also create minimized code sections by utilizing the new ``//#region`` and ``//#endregion`` annotations.

The Find ``(Ctrl + F)`` and Replace ``(Ctrl + H)`` functions have been completely overhauled in this new editor to provide dynamic results as you type 
and allow you to find matching words easier. In addition, there are now many more options available such as finding matching words in a highlighted section or the entire script.

A new minimap has been added to the Pine Script™ editor, allowing you to see a zoomed-out version of your code. This minimap is especially helpful with larger scripts, 
because it will show you errors and warning highlighted lines of code and highlighting lines when you use the Find and Replace functions.

A color preview window has been added and will appear whenever you hover over a color function, hex value, or a built-in color. 
This color preview window will allow you to quickly and easily change any color on the fly.

The new editor will now store your code locally, so no more losing unsaved code with an accidental page refresh! 

Users can now change all code indentations from tabs to spaces and vice versa. 
A unique hidden bonus is deciding the number of spaces if you want something different than the standard four spaces. Here is how you do that:

 - Hit the ``F1`` key.
 - Type ``Indent`` into the Command Palette search box.
 - Use the ``Up arrow`` or ``Down arrow`` to navigate within the dropdown list.
 - Press the ``Enter`` key to select ``Indent using spaces`` or ``Indent using tabs``.
 - Choose what indentation size you would prefer instead.



Changes
^^^^^^^

``Ctrl + D`` no longer deletes a line of code and now adds the highlighted word to the next Find match.

``Ctrl + /`` no longer highlights multiple lines of code and now collapses all block comments.

``Ctrl + Backspace`` or ``Ctrl + Delete`` used to remove the word to the left and right, respectively, but now there are no matching keyboard shortcuts in the new editor.

The multi-cursor feature that can be accessed on either editor using ``Ctrl + Alt + (Up or Down)`` won't work correctly on lines that use a color swatch.

``Ctrl + Delete`` used to first delete any space between the cursor and the word to the right and you would have to use this combo again to delete the word to the right. 
In the new editor, the space and the word are deleted the first time.

The added functionality of the new editor will sometimes cause it to take more time to respond compared to the previous editor.