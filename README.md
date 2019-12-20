# Hierarchical Planning System

## Immediate features (within scope of this SOS quarter)

* Use case
	* Optimized for security conscious people with good computer skills executive function problems (i.e., OCD autistic computer science majors, like myself)
	* Should be entirely managable via terminal with very intuitive and discoverable features (e.g., see [FISH's law of discoverability](https://fishshell.com/docs/current/design.html))
	* Performs functions of TODO lists & calendars, in one system
* Storage
	* Calendar/TODO is stored as a set of human-readable config files  (probably modified markdown syntax)
	* Recursive parsing
	* Syntax includes mechanism for marking tasks as done
	* Seperate files for completed tasks and in-progress tasks. Files for completed tasks serve as a productivity log. Completed tasks are automatically moved to the completed task file to minimize clutter.
* Client-server model
	* Chosen for architectural simplicity
	* Capable of synchronizing with multiple clients on the fly
	* Text-only daemon with a packaged systemd unit
	* Include `--dameon` option with forking & PID file, for people who prefer using `init.d`, to make their lives easier
	* End-to-end encryption system. Server has no knowledge of client data.
* Interfaces
	* Textmode interface with robust error handling and reasonably intuitive arguments
	* Interactive textmode "console" interface
	* Direct conf file editing/adding -- client must automatically detect these changes and load them in real time.
	* API for easy integration with other software
* Distribution
	* Compatible with most Linux operating systems
	* Robust build system
	* Semi-professional packaging
	* AUR package for Arch Linux systems
	* Build system should have option to automatically compress a tarball for binary distribution 
	* Run-in-place mode allows installation
	
## Things to consider

* What language should the first piece of software be implemented in? I am leaning toward Python, but C++ would probably be good practice for me and result in a leaner implementation.
	* Would, however, increase risk of exploits.
* How will I optimize data being sent? A fluid human-readable syntax limits the applicability of database-type piecemeal synchronization, thus requiring synchronization of entire file.
	* Consider implementing a crude minimal version control system.
		That is, find differences between files and send those differences, to have them reassembled on the other end.
* Format of metadata? Raw binary or compressed json?
* Should I implement TLS on top of PGP?
* Should interactive textmode interface use ncurses, or be plain command line?
* What's the directory structure layout of the configs?
* Should calendar config files go under `$HOME/.config` or `$HOME/.local/share`?
## Later features (perhaps for future SOS projects?)

* Add native Windows support via Cygwin?
* Add ability to import/export `ical`/`ics` files.
* Robust, semi-intuitive GUI interface
	* TK GUI, GTK, or WxWidgets?
* Android app
	* Will probably never support Apple devices (unless this app catches on and people are willing to pay me to implement it -- but I doubt that)


