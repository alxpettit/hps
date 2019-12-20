# Hi! This is an example calconfig file to test out syntax ideas. :)

// It's markdown-compatible, so you can easily view this as a human-friendly markdown note file.
// This specification is still a WIP, so things may change drastically. I'm not even sure I'll go with this solution.


// Begin line with `//` or `#` for comment

// Main syntax is either bullet points or numbers
// Nodes that begin with valid time will be added to time data for entry below that time.
// If time data is contradictory, an error is thrown, unless you give an override -- thus preventing users accidentally overriding time data for parent node.
// Nodes without time data are assumed to be pure metadata (event description strings, etc)
// Time data and metadata string can be included in single node line via `-` delimiter

* Monday
    * foo
    * 24:00 - sleep
    
 // Applies to all instances of 12:20
 // Adding a root-level node without a date descriptor means that event `bar` is to be sent each day at 12:20
 
*  12:20 - bar
