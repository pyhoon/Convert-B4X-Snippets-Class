# Convert Class.bas to Class.txt

This script converts file with `.bas` extension to `.txt` and place it inside `/Snippets` folder to be included into `B4X library` or `B4X template` as `code snippets`.

The following lines are not visible inside B4J Code Editor but are visible if you open the `.bas` file using a text editor.
```B4X
B4J=true
Group=Handlers
ModulesStructureVersion=1
Type=Class
Version=10.5
@EndOfDesignText@
```

In order to create a `Code Snippet`, line of code as seen above need to be removed. \
Different from Class template, we also want to remove the first line of `Sub Class_Globals` and last line of `End Sub`. \
With this, we can start typing 'Code' in the IDE to invoke the **Code Snippets**.
This script will remove the lines for us so we don't need to edit the files one by one.

## How to use​ create Class.txt
1. Download `create_snippets.bat`.
2. Put the file at the same path as `.b4j` project file.
3. The command to run it:
    ```
    create_snippets.bat class1.bas class2.bas
    ```
4. We can use `#Macro` to call this batch file.

### Example
   ```
   #Macro: Title, Create Template, ide://run?File=%PROJECT%\create_snippets.bat&Args=..\Model.bas&Args=..\View.bas
   ```
## How to apply Code Snippets
1. Create a standard class from menu `Add New Module` > `Class Module` > `Standard Class`.
2. If your Code Snippet starts from `Class_Global` sub then remove the `Initialize` sub.
3. Put the cursor in between `Sub Class_Globals` and `End Sub`
4. Start typing `code`.
5. Code Snippets will be listed if any is available.
6. Use arrow key `up`/`down` and press `Enter` or use mouse to select the Snippet you want.

## Note
1. Code Snippets may contains invalid symbols such as `$key$` and `$end$`.
2. Add the class to the project
3. Make modification to the code and save it.
4. Remove the file from the project so it won't interfere with the compilation.

## Assumption
1. My Code Snippet starts from Class_Global sub so I need to remove the Initialize sub when applying the Code Snippet.
2. If your Code Snippet doesn't have any variable declaration in the class then you can replace 'Sub Class_Globals' with 'Public Sub Initialize' in the script.
3. If your Code Snippet is in the middle of code then you may need to replace the starting marker 'Sub Class_Globals' with something else in the script. I am not sure it works.
