YAML is a text based format allowing to store structured data in a hierarchy. YAML is designed to be human and machine readable with a minimum of overhead. The YAML specification can be found at [yaml.org](http://yaml.org/spec/1.2/spec.html). There is also a [reference card](http://www.yaml.org/refcard.html)

Comments start with `#` and go till newline, comments must be separated from other tokens by whitespace. Whitespace isn't free, indentation must be spaces, not tabs. YAML will consider that lines prefixed with more spaces than the parent key are contained inside it. Moreover, all lines must be prefixed with the same amount of spaces to belong to the same map.

YAML has sequences and mappings as collection types, both can be represented in flow and block style.

An sequence of scalar strings in YAML looks like:

    [ one, two, three ]   # flow style

    # or block style

    - one
    - two
    - three
    
A mapping consists of key/value pairs:

    index: 4  # block style
    name: nali

    # or 

    { index: 4, name: nali }   # flow style

    # or nested (equivalent of { level: { one: { two: fun } } }):

    level:

      one:

        two: fun




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


>I've been producing and consuming YAML lately. If you have objects serialized to text, you need some form of introspection to reconstruct them with a generic parser. The YAML parser does not know or care about the code in those other modules. It just assumes that the names in the input correspond to classes currently loaded by whomever called the parser. It relies on the language's introspection system to convert the strings in the YAML into calls to constructors.

## References
http://docs.racket-lang.org/yaml/
https://news.ycombinator.com/item?id=17358103