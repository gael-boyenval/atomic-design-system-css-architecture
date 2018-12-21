# Our flavor of BEM

## Our flavor of BEM selectors :

If you read the docs you have seen that ther is not one convention but many.

The one that we will use is the following :

```css
.pr-block-name {}
.pr-block-name__element-name {}
.pr-block-name--modifier-name {}
.pr-block-name__element-name--modifier-name {}
```

### To summarize: 

* We need a **prefix** symbolized by `.pr-` here
* **Words** are separated by a `-` in a kebab case fashion
* **Element** entity is preceded by two low dashes `__element-name`
* **Modifiers** are separated by two 'middle' dashes `--modifier-name`

For now, don't care about the prefix `.pr-` part, it will be explained later, in the **BEMIT** related page of this doc.

### Syntactic sugar with SCSS

With SCSS we use the `&` to call the parent selector name and add the required BEM entity at the end :

```css
.pr-block-name {
    /* .pr-block-name {} */
    
    &--modifier-name {
        /* .pr-block-name--modifier-name {} */
    }
    
    &__element-name {
        /* .pr-block-name__element-name {} */
        
        &--modifier-name {
            /* .pr-block-name__element-name--modifier-name {} */
        }
    }
}
```

If you ask me, typing less is always cool, but the coolest part is that it create this kind of nesting structure that illustrate even more the relationship between the different entities.

