----------

**Language EBNF:**

BLOCK = "{", { STATEMENT }, "}" ;  
STATEMENT = ( { ASSIGNMENT | PRINT }, ";") | BLOCK | WHILE | IF | TYPE ;  
WHILE = "loop", "(", RELEXPRESSION, ")" , STATEMENT ;  
IF = "condition", "(", RELEXPRESSION, ")" , STATEMENT) , { "exception", STATEMENT } ;  
TYPE = "var", IDENTIFIER, { ",", OIDENTIFIER }, { ":", ("i32" | "String" | "Float") } ;  
OIDENTIFIER = IDENTIFIER, "," ;  
ASSIGNMENT = IDENTIFIER, "=", RELEXPRESSION ;  
PRINT = "out", "(", RELEXPRESSION, ")" ;  
EXPRESSION = TERM, { ("+" | "-" | "or" ), TERM } ;  
RELEXPRESSION = FACTOR, { ("==" | "!=" | ">" | "<" | ">=" | "<=" | "+"), FACTOR } ;  
TERM = FACTOR, { ("\*" | "/" | "and"), FACTOR } ;  
FACTOR = NUMBER | STRING | IDENTIFIER | ("+" | "-" | "not"), FACTOR) | "in", "(", ")" | "(", RELEXPRESSION, ")" ;  
IDENTIFIER = LETTER, { LETTER | "\_" } ;  
NUMBER = DIGIT, { DIGIT }, {",", DIGIT};  
STRING = LETTER, { LETTER } ;  
LETTER = ( a | ... | z  ) ;  
DIGIT = ( 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 ) ;

-----------
