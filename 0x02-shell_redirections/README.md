Use `echo` for a standard output/print

Use `"\"<copied_text> \'"` display a confused smiley face

Use `cat /etc/passwd` to display the content of a file called `passwd`

Use `cat /etc/passwd /etc/hosts` to display the content of two different files `passwd` and `host`

Use `tail` to display the last ten lines in a file

Use `head` to display the first ten lines in a file

Use `head -3 | tail -1` to display the third line of the file

Use `echo "file-content" > "file-name"` create a file and write content in it

Use `ls -la > ls_cwd_content` write into a file `ls_cwd_content` the result of the `ls -la` command

Use `tail -1 < iacta >> iacta` to duplicate the last line of `iacta` file

Use `find -name "*.js" -type f -delete` to delete all regular `.js` files extension present in cwd and subdirectory

Use `find . -type d ! -path . -print | wc -l` count number directories and subdirectories in cwd

Use `ls -1t | head -10` display the 10 newest files in the cwd

Use `sort | uniq -u` print out words tht appear once

Use `grep "root" /etc/passwd` display lines containing pattern `root` in file `passwd`

Use `grep -c "bin" /etc/passwd` display the number of lines that contain the pattern `bin` in the file `/tect/passwd`

Use `grep -A 3 "root" /etc/passwd` display lines conataining the pattern `root` and 3 lines after them in the file `passwd`

Use `grep -v "bin" /etc/passwd`display line in the file that does not contain `bin`
