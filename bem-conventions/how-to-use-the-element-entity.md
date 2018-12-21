# How to use the Element entity

### Do not is nest elements :

```css
.ga-nav {
    &__menu {
        &__item { /* don't */
            /* output .ga-nav__menu__item */
        }
    }
}
```

It make our class name unnecessary long and it create a structure dependency. In the exemple case this is not such a problem, since item will always be a child of menu but consider the following exemple : 

```css
.ga-nav {
    &__right-column {
        &__search-form { /* don't */
            /* output .ga-nav__right-column__search-form */
        }
    }
}
```

Here we are tied to use the search-form inside the right column.  
If a change is required, the css need to be updated and this is a breaking change.

### Instead do :

```css
.ga-nav {
    &__menu {
        /* output .ga-nav__menu */
    }
    
    &__item { /* do */
        /* output .ga-nav__item */
    }
}
```

or :

```css
.ga-nav {
    &__right-column {
        /* output .ga-nav__right-column */
    }
    &__search-form {
        /* output .ga-nav__right-column__search-form */
    }
}
```

Or if you really think that the class name require a reminder of the parent element :

```css
.ga-nav {
    &__menu {
        /* output .ga-nav__menu */
    }
    
    &__menu-item { /* do */
        /* output .ga-nav__item */
    }
}
```



