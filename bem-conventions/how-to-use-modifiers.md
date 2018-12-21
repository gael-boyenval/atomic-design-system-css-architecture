# How to use the Modifier entity

## How we use modifiers :

Some peoples will write `.block-name--modifier-name__element-name` .  
But in my experience it is overkill, and it prevent us to write modifiers in a Object oriented fashion.

We will prefer to write Element with a block modifier this way : `.block-name--modifier-name .block-name__element-name {}`

You will tell me, this create **unnecessary specificity**, and **BEM state that your specificity should as flat as possible**.

Yes absolutely, but in the first way, **it's a pain in the \*^%!"** to use multiple modifiers.  
Let me explain with an exemple. 

### The button exemple

**Assume I want two modifiers for their color scheme:**

* neutral
* call to action

**Also two modifiers for their sizes :** 

* small
* large

**The button need to have two elements:**

* an icon
* a text container

### The first version

here what it could look like with the first version

```css
.ga-button {
    /* here common and global styles of button */
    
    &--large   { /* larges styles */ }
    &--small   { /* small styles */ }
    
    &--neutral { /* neutral styles */ }
    &--cta     { /* cta styles */ }

    &__icon { /* here common button icon styles */}
    &--large__icon { /* larges button icon styles */ }
    &--small__icon { /* small button icon styles */ }
    &--neutral__icon { /* neutral color icon styles */ }
    &--cta__icon { /* cta color icon styles */ }
    
    &__text { /* here common button text styles */}
    &--large__text { /* larges button text styles */ }
    &--small__text { /* small button text styles */ }
    &--neutral__text { /* neutral color text styles */ }
    &--cta__text { /* cta color text styles */ }
 
}
```

First, we can see that our icon declarations are outside the `icon` element declaration block, witch beat the purpose of our syntactic sugar. And let's face it, developer love syntactic sugar.

We would prefer to have all the declarations related to icon into the icon block, because it make more sense to colocate all styles related to icons. 

It can be tempting to collocate the styles within the modifiers like so : 

```css
.ga-button {
    /* here common and global styles of button */
    &--large   { 
        /* larges styles */
        &__icon { /* larges button icon styles */ }
        &__text { /* larges button text styles */ }
    }
    /*...*/
    &__icon { /* icon common styles */ }
    &__text { /* larges button text styles */ }
}
```

But because of the declaration order, the styles of the non-modified `icon` and `text` styles will be applied… Solving this would result in having to move all the _**modifier**_ related entities at the bottom of our block, and I think this is a lot more confusing. 

**But there is worst, look at the markup :**

```markup
<button class="ga-button ga-button--large ga-button--cta">
    <span class="
        ga-button__icon
        ga-button--large__icon
        ga-button--cta__icon
        ga-icon
        ga-icon--check-mark">
    </span>
    <span class="
        ga-button__text
        ga-button--large__text
        ga-button--cta__text">
        button text
    </span>
</button>
```

We have our button block witch take his modifiers. **But see how we need to re-apply all the modifiers into the all the required elements**. This is a lot of classes. and there is only two elements that need to be modified, what if your block contain plenty of elements and have more than two types of modifiers \(size and color\). I think you see my point here.

_**Side note :**_ We can also see that the icon came with its own selectors from another `.ga-icon` component. and this is part of the magic of BEM : you know the relationship between classes by their names only.

### What we do instead

```css
.ga-button {
    /* here common and global styles of button */
    
    &--large   { /* larges styles */ }
    &--small   { /* small styles */ }
    
    &--neutral { /* neutral styles */ }
    &--cta     { /* cta styles */ }

    &__icon { 
        /* here common button icon styles */
        
        .ga-button--large & { /* larges button icon styles */ }
        .ga-button--small & { /* larges button icon styles */ }
        
        .ga-button--neutral & { /* larges button icon styles */ }
        .ga-button--cta & { /* larges button icon styles */ }
    }
    
    &__text { 
        /* here common button text styles */
        
        .ga-button--large & { /* larges button text styles */ }
        .ga-button--small & { /* larges button text styles */ }
        
        .ga-button--neutral & { /* larges button text styles */ }
        .ga-button--cta & { /* larges button text styles */ }
    }
}
```

**The markup :**

```markup
<button class="ga-button ga-button--large ga-button--cta">
    <span class="ga-button__icon ga-icon ga-icon--check-mark"></span>
    <span class="ga-button__text">button text</span>
</button>
```

In this version, we can see that we have our syntactic sugar, as well as a way, way cleaner markup.  
if we need more modifier types, we just add it to the markup at the block level.

Its cost us a specificity of `20` instead of `10` but in my experience, as our components are isolated, this is rarely causing any problems as long as the [**SRP**](../principles/single-responsibility-principle.md) is applied with good \(enough\) care.

