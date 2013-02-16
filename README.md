Simple JS parser to strip comments

// this is a comment

/* this
 * is a multiline
 * comment
*/

Usage is simple - create an instance and call .strip(string) to get back the de-commented string...

<pre>var cs = new CommentStripper();
console.log( cs.strip(someString) );</pre>

It's *intended* to be 100% effective - catching any valid comment, including:

- var a = 10; // comment
- var a = "http://www.github.com"; //
- var a = function(arg /*, ...rest */)

etc.

I've tested it a bit against use-cases I could think of, and tried it against a few common libraries (e.g., the dev version of jQuery), and it seems fine, but I'd be interested to hear if anyone breaks it.
