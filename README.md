# NAME

	T - a minimal tmux/vim "interactive" bash pipe visualizing filter
## Screenshots

![Screenshot](https://raw.github.com/nkh/ftl/main/screenshots/ss1.png)

# SYNOPSIS
	T [options] name | cmd |cmd | T [options] name | ...

# OPTIONS
	-h	displays this help
	-r	kill preview, remove intermediary files
	-c	kill preview
	-S	skip
	-n	limit the data size, 0 for no limit, default 500 lines
	-s	spell check data
	-A	install AnsiEsc to colorize
	-k	wait for input and kills preview

# DESCRIPTION
	Place T anywhere in a pipeline to visualize it. Each of T opens
	a tab in vi named after it's argument (in a tmux pane). 
	
	T leaves intermediary files for you. cleanup with -r, -c, or -k 

# EXAMPLES

	fd | sed '...' | T sed1 | sed '...' | T -n 10 sed2 | lscolors | T -A
		... | sed1 in vim | ... | sed2 in vim ... | vim colored entries
	
	T -r ; ... | T -k -A result or T -c | ... | T -A -k result
		remove files and pane, run the command, the last T waits for a
		key press to clean up, result is output in the terminal  ftl - file manager using tmux panes and live previews

# LICENSE AND COPYRIGHT

Artistic License 2.0 or GPL 3.0 at your convenience.

© Nadim Khemir 2020-2023
mailto:nadim.khemir@gmail.com
CPAN/Github ID: NKH

# SEE ALSO

up, the ultimate plumber
