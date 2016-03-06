Simple JS parser to strip comments

<pre>
// this is a comment

/* this
 * is a multiline
 * comment
*/
</pre>

Usage is simple - create an instance and call .strip(string) to get back the de-commented string...

<pre>var cs = new CommentStripper();
console.log( cs.strip(someString) );</pre>

Or specify an option to preserve all newlines within multiline comments (e.g. to support sourcemaps)...

<pre>var cs = new CommentStripper({'preserveNewlines': true});
console.log( cs.strip(someString) );</pre>

It's *intended* to be 100% effective - catching any valid comment, including:

<pre>var a = 10; // comment
var a = "http://www.github.com"; // more comments
var a = function(arg /*, ...rest */)</pre>

etc.

I've tested it a bit against use-cases I could think of, and tried it against a few common libraries (e.g., the dev version of jQuery), and it seems fine, but I'd be interested to hear if anyone breaks it.
