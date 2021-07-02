# Cascade

The cascade is the name for this set of rules. It determines how conflicts are resolved, and it’s a fundamental part of how the language works.

## Understanding Stylesheet Origin.

    1. Author Styles -- styles we write.
    2. User agent styles -- Which are the browser’s default styles.

User agent styles have lower priority, so your styles override them.

## Understanding specificity.

    1. INLINE STYLES -- These have highest priority, they can be overridden only by *!improtant*
    2. SELECTOR SPECIFICITY --
        1. If a selector has more IDs, it wins (that is, it’s more specific).
        2. If that results in a tie, the selector with the most classes wins.
        3. If that results in a tie, the selector with the most tag names wins.

        ### Calculating Specifity using Notation.
        Selector                    | IDs| Classes | Tags  | Notation |
        --------------------------  | ---|---------|-------|--------- |
        html body header h1         | 0  | 0       | 4     | 0,0,4    |
        body header.page-header h1  | 0  | 1       | 3     | 0,1,3    |
        .page-header .title         | 0  | 2       | 0     | 0,2,0    |
        #page-title                 | 1  | 0       | 0     | 1,0,0    |

## Understanding source order.

    The third and final step to resolving the cascade is source order. If the origin and the specificity are the same, then the declaration that appears later in the stylesheet—or appears in a stylesheet included later on the page—takes precedence.

### Two rules of thumb

    1.Don’t use IDs in your selector. Even one ID ratchets up the specificity a lot.
    2.Don’t use !important. This is even more difficult to override than an ID.

# Inheritance

    If an element has no cascaded value for a given property, it may inherit one from an ancestor element. It’s common to apply a font-family to the <body> element. All the ancestor elements within will then  inherit this font.

# Key Notes

## Special values

    1. inherit -- Sometimes, you’ll want inheritance to take place when a cascaded value is preventing it.
    2. initial -- Resets property to its default value.

## Short hand

    TRouBLe is an mnemonic you can use to remember the order: top, right, bottom, left.
