# Comments

## About comments :

### **General purpose comments in the top of your file :**

If you think this is required you can add a **general purpose comment in the top of your file**, for that, use the SCSS single line comment, so they are not added to the css file :

```css
// These comments are in single line
// They will not appear in the CSS output,
// since they use the single-line comment syntax.

.ga-button {
    /*...*/
}
```

### Supports comment :

You should avoid support comments, but it is possible when required to add comments on code blocks to give information about **what is left to do** or more importantly **what is here for legacy support purpose only.**

Please consider that the **TODOS are not a good practice** and that using the project management tool for that is way better. Still, I have no religion about that.

For this type of comment, **use native CSS comments**  
Add the **capitalized flags `LEGACY_SUPPORT` and `END_LEGACY_SUPPORT` at the start and at the end** of the legacy support code block.  
Add also **the version in witch the support is supposed to be dropped**.

```css
.go-my-block {
    
    /* LEGACY SUPPORT : will be removed in version 2 */
    &__toto {
        /*...*/
    }
    /* END LEGACY SUPPORT */
    
    // replace .go-my-block__toto in version 1.9.6 and higher
    &__tata {

        /* TODO: do something (this should be avoided in production) */
        /*...*/
    }
}
```

### Code comment :

Obviously use as much code comments as you want. Use SCSS comments for that. 

```css
.ga-my-block {
    flex: 1 0 0; // do not use abreviation for ie 10
}
```



