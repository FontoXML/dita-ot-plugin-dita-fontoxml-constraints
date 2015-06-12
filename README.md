# com.fontoxml.dita.v1_2.standard.constraints

Most industry standard schemas, including OASIS DITA, are designed with flexibility and extensibility in mind. They try to be as unopinionated as possible which is a good thing since you can choose how you can satisfy your needs without having to copy &amp; paste the whole thing.

However, this flexiblity will unavoidably lead to ambiguous situations in the schema where, for example, character data and paragraph elements are allowed to coexist on the same level in the hierarchy. Have a look at the &lt;[note](http://docs.oasis-open.org/dita/v1.2/os/spec/langref/note.html)&gt; element as defined in the DITA standard; it can contain character data directly as well as block level elements including &lt;p&gt;.

From an XML perspective, these ambiguities might not seem like a problem, maybe rather an aesthetic issue. However, you will most likely run into problems when you create renditions of te content. For example, if you have character data followed by a table followed by a paragraph; is the table supposed to be rendered inline or not? Also from an authoring perspective, these ambiguities will lead to confusion. Most authors, especially subject-matter experts, are not aware of these ambiguities. So they can't consciously make a decision to go one way or the other, which in time will lead to inconsistently structured content.

The good news is that the DITA standard has a constraint facility, which allows unilateral modification of content models and attribute lists for individual elements without breaking compatibility with the base schema. See [http://docs.oasis-open.org/dita/v1.2/os/spec/archSpec/ditaspecialization.html](http://docs.oasis-open.org/dita/v1.2/os/spec/archSpec/ditaspecialization.html) for additional details.

This repository contains a set of **opinionated** constraint modules specifically designed to remove ambiguous scenarios from the DITA standard. The design of the constraints is inspired by the Lightweight DITA thought which states character data and inline elements are only allowed within the paragraph element. This means that the &lt;[note](http://docs.oasis-open.org/dita/v1.2/os/spec/langref/note.html)&gt;, for example, can only contain block level element including the paragraph element.

## What others are saying

Excerpt from [Eliot Kimber](https://github.com/drmacro)s [DITA for practitioners](http://xmlpress.net/publications/dita/practitioners-1/) volume 1:

> In practice, it would be rare for any production use of DITA to use base topic types without any additional domains.
> In part, this is because the base topic types intentionally have very loose content models to make them suitable as a base for specialization.
> For example, both the base &lt;body&gt; and &lt;section&gt; elements allow PCDATA where most users of DITA would never want PCDATA.

## Status

Work in progress, any ideas, comments and feedback is welcome!

## Installation

To install the constraint modules in the 

1. Checkout this repository in ```{DITA_OT_PATH}/plugins/com.fontoxml.dita.v1_2.standard.constraints```
2. From ```{DITA_OT_PATH}``` run ```ant -f integrator.xml```

## License

This project is licensed under [MIT](http://www.opensource.org/licenses/mit-license.php "Read more about the MIT license form"). Refer to LICENCE for more information.
