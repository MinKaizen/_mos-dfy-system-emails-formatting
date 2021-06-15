
Regex basics:
=======================
Regex means `Regular Expression`. It's like Ctrl+F Find and Replace but on steroids. Instead of finding a string and replacing it, you can find a string based on a pattern. With Regex, you can do stuff like: 

- "Find and replace ___ but only if it appears in the beginning of as sentence"
- "Find something [that looks like a URL], and replace the http with https"
- "Find something that looks like an american date (06/15/1995) and turn it into an Australian date (15/06/1995)"
- "Find all numbers with a preceding 0 (like 08 and 009) and remove the 0's"
- "Find all places in a document that start with `<div` and end in `</div>` and add a `style=""` property to it"

Requirements
=======================

- See input.html
- IMPORTANT: record all the replacements you did and in what order. I'm gonna ask you turn this process into a script afterwards
- Convert the document into a JSON file (see output-sample.json)
- Inside the "content" string, format everything in HTML according to template/content-template.html
- Remove leading and trailing spaces at start/end of a subject line or content string (e.g. " Hello world" has a leading space, or "Hello world  " has two trailing spaces)
- Content should be ONE line.

Content requirements (template/content-template.html)

- replace `__SUBJECT_LINE__` with the email subject line
- replace `__BODY__` with the actual email body (see /samples/body-sample.html)
- replace `__PS__` with /partials/ps.html
- Make everything fit in one line

Body requirements (/samples/body-sample.html)

- Add `<br><br>` tag at the end of each line (including the very last line)
- Wrap links in a link tag:
`<a href="__LINK_#__">__TEXT__</a>`
- Where # is the number of the email and `__TEXT__` is the actual text. For example:
`<a href="__LINK_42__">Click here.</a>`
- Remove all other html tags and attributes
- Make everything fit in one line

Tips
=======================

You shouldn't need to do any manual work. Everything can be regex-replaced. If you're not sure, ask me.

You can tell something is a link because in your Google doc you made the text blue. That means you should see something in the HTML that resembles:
style="color:blue"
(but there might be more styles and the actual color code is not "blue")

In your JSON file, there might be a place where you need to put in quotes. Make sure to "escape" them properly.
If you're not sure, google "how to escape quotes in JSON"
And if you want to check that you JSON file is correctly formatted, google "json validator"

In VS code, if you hit `command+f`, the normal "search" box will appear. You can tick the box with a star on it to turn it into `regex search`. Then click the arrow on the left to drop down the "replace" option

In VS Code, make sure your lines don't wrap (i.e. if there's a really long line, let it go off the screen instead of going down a line). It will be easier to do your stuff this way

If you YouTube regex basics, you should be able to learn all that you can do with regex within 20 minutes or so. After that, just search up `regex cheatsheet` so you know what symbols mean what.

This is a site you can use to test out regex rules:
`https://regex101.com/`
You can copy and paste a small portion of your document in there and see if the regex rule you came up with does what you expected.