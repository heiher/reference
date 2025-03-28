r[lex.keywords]
# Keywords

Rust divides keywords into three categories:

* [strict](#strict-keywords)
* [reserved](#reserved-keywords)
* [weak](#weak-keywords)

r[lex.keywords.strict]
## Strict keywords

r[lex.keywords.strict.intro]
These keywords can only be used in their correct contexts. They cannot
be used as the names of:

* [Items]
* [Variables] and function parameters
* Fields and [variants]
* [Type parameters]
* Lifetime parameters or [loop labels]
* [Macros] or [attributes]
* [Macro placeholders]
* [Crates]

r[lex.keywords.strict.list]
> **<sup>Lexer:<sup>**\
> KW_AS             : `as`\
> KW_BREAK          : `break`\
> KW_CONST          : `const`\
> KW_CONTINUE       : `continue`\
> KW_CRATE          : `crate`\
> KW_ELSE           : `else`\
> KW_ENUM           : `enum`\
> KW_EXTERN         : `extern`\
> KW_FALSE          : `false`\
> KW_FN             : `fn`\
> KW_FOR            : `for`\
> KW_IF             : `if`\
> KW_IMPL           : `impl`\
> KW_IN             : `in`\
> KW_LET            : `let`\
> KW_LOOP           : `loop`\
> KW_MATCH          : `match`\
> KW_MOD            : `mod`\
> KW_MOVE           : `move`\
> KW_MUT            : `mut`\
> KW_PUB            : `pub`\
> KW_REF            : `ref`\
> KW_RETURN         : `return`\
> KW_SELFVALUE      : `self`\
> KW_SELFTYPE       : `Self`\
> KW_STATIC         : `static`\
> KW_STRUCT         : `struct`\
> KW_SUPER          : `super`\
> KW_TRAIT          : `trait`\
> KW_TRUE           : `true`\
> KW_TYPE           : `type`\
> KW_UNSAFE         : `unsafe`\
> KW_USE            : `use`\
> KW_WHERE          : `where`\
> KW_WHILE          : `while`

r[lex.keywords.strict.edition2018]
The following keywords were added beginning in the 2018 edition.

> **<sup>Lexer 2018+</sup>**\
> KW_ASYNC          : `async`\
> KW_AWAIT          : `await`\
> KW_DYN            : `dyn`

r[lex.keywords.reserved]
## Reserved keywords

r[lex.keywords.reserved.intro]
These keywords aren't used yet, but they are reserved for future use. They have
the same restrictions as strict keywords. The reasoning behind this is to make
current programs forward compatible with future versions of Rust by forbidding
them to use these keywords.

r[lex.keywords.reserved.list]
> **<sup>Lexer</sup>**\
> KW_ABSTRACT       : `abstract`\
> KW_BECOME         : `become`\
> KW_BOX            : `box`\
> KW_DO             : `do`\
> KW_FINAL          : `final`\
> KW_MACRO          : `macro`\
> KW_OVERRIDE       : `override`\
> KW_PRIV           : `priv`\
> KW_TYPEOF         : `typeof`\
> KW_UNSIZED        : `unsized`\
> KW_VIRTUAL        : `virtual`\
> KW_YIELD          : `yield`

r[lex.keywords.reserved.edition2018]
The following keywords are reserved beginning in the 2018 edition.

> **<sup>Lexer 2018+</sup>**\
> KW_TRY   : `try`

The following keywords are reserved beginning in the 2024 edition.

> **<sup>Lexer 2024+</sup>**\
> KW_GEN   : `gen`

r[lex.keywords.weak]
## Weak keywords

r[lex.keywords.weak.intro]
These keywords have special meaning only in certain contexts. For example, it
is possible to declare a variable or method with the name `union`.

> **<sup>Lexer</sup>**\
> KW_MACRO_RULES    : `macro_rules`\
> KW_UNION          : `union`\
> KW_STATICLIFETIME : `'static`\
> KW_SAFE           : `safe`\
> KW_RAW            : `raw`
>
> **<sup>Lexer 2015</sup>**\
> KW_DYN            : `dyn`

r[lex.keywords.weak.macro_rules]
* `macro_rules` is used to create custom [macros].

r[lex.keywords.weak.union]
* `union` is used to declare a [union] and is only a keyword when used in a
  union declaration.

r[lex.keywords.weak.lifetime-static]
* `'static` is used for the static lifetime and cannot be used as a [generic
  lifetime parameter] or [loop label]

  ```compile_fail
  // error[E0262]: invalid lifetime parameter name: `'static`
  fn invalid_lifetime_parameter<'static>(s: &'static str) -> &'static str { s }
  ```

r[lex.keywords.weak.dyn]
* In the 2015 edition, [`dyn`] is a keyword when used in a type position
  followed by a path that does not start with `::` or `<`, a lifetime, a question mark, a `for`
  keyword or an opening parenthesis.

  Beginning in the 2018 edition, `dyn` has been promoted to a strict keyword.

r[lex.keywords.weak.safe]
* `safe` is used for functions and statics, which has meaning in [external blocks].

r[lex.keywords.weak.raw]
* `raw` is used for [raw borrow operators], and is only a keyword when matching a raw borrow operator form (such as `&raw const expr` or `&raw mut expr`).

[items]: items.md
[Variables]: variables.md
[Type parameters]: types/parameters.md
[loop labels]: expressions/loop-expr.md#loop-labels
[Macros]: macros.md
[attributes]: attributes.md
[Macro placeholders]: macros-by-example.md
[Crates]: crates-and-source-files.md
[union]: items/unions.md
[variants]: items/enumerations.md
[`dyn`]: types/trait-object.md
[loop label]: expressions/loop-expr.md#loop-labels
[generic lifetime parameter]: items/generics.md
[external blocks]: items/external-blocks.md
[raw borrow operators]: expressions/operator-expr.md#raw-borrow-operators
