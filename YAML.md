Splitting text strings over multiple lines
```
- Without quotes:
   You can just
   split a long piece of text like this.
- With quotes:
    "[But be careful:
     if you \"need\" punctuation, put double quotes around it. You can ev\
     en split without spaces by using backslashes."
- Or single quotes:
    'This works
     but isn''t as flexible'
- If you want to keep those new line characters: | 
    Then do
    it this way with 
    a pipe (|) character. (This string has three \n characters)
- Or you can have just the one final new line: >
    This string has
    just one \n character, at the very end.
- Block indicators:
    Look up >-, >+, |- and |+ for fine tuning.
```

Basic YAML types

    integer: 25
    string: "25"
    float: 25.0
    boolean: true
    null type: null

YAML supports three styles of escape notation:

1. Entity Escapes 

   a. space: "&amp;#x20;"

   b. colon: "&amp;#58;"

   c. ampersand: "&amp;amp;"

2. Unicode Escapes

   a. space: "\u0020"

   b. single quote: "\u0027"

   c. double quote: "\u0022"

3. Quoted Escapes

   a. double quote in single quote: 'Is "I always lie" a true statement?'

   b. nested double quote: " She said, \"I quit\" "

   c. nested single quote: ' He was speechless: '' '