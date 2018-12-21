# Declaration Orders

### Mixins and function should be declared before properties, and a blank line should be added after :

```css
.ga-button {
    @include button-layout(large);
    @include button-theme(standard);

    color: $grey-200;
    font-size: $fs-std;
}
```

### Everything that may change the behavior and appearance of an entity should be declared after the standard properties and before the next entity :

**In that order :**

1. pseudo-selectors
2. state classes
3. mediaqueries
4. modifiers

```css
.ga-button {
    padding: 0.25rem 0.5rem;
    
    &:hover {
        /*...*/
    }
    
    &.is-disabled {
        /*...*/
        &:hover {
            /*...*/
        }
    }
    
    @media screen and (min-width: 200px) {
        /*...*/
    }
    
    &--large {
        /* large modifier styles */
        
        /* then you can repeat the changes here if required */
        @media screen and (min-width: 200px) {
            /*...*/
        }
    }
    
    /* then only we can style children elements */
    &__icon {
        /* define icon */
        
        /* then you can repeat the changes here if required */
        @media screen and (min-width: 200px) {
            /*...*/
        }

        &--spining {
            /* make the thing spin */
        }
    }
}
```

### Order media queries in a mobile first fashion

```css
.ga-button {
   /* small mobile and common code */
        
   /* large mobile */
   @media screen and (min-width: 340px) {
      /*...*/
   }
   
   /* tablet */
   @media screen and (min-width: 480px) {
      /*...*/
   }
   
   /* desktop */
   @media screen and (min-width: 1024px) {
      /*...*/
   }
   
   /* large desktop */
   @media screen and (min-width: 1480px) {
      /*...*/
   }
   
   &__icon {
      /* small mobile and common code */
        
      /* large mobile */
      @media screen and (min-width: 340px) {
         /*...*/
      }
   
      /* tablet */
      @media screen and (min-width: 480px) {
         /*...*/
      }
      
      /* desktop */
      @media screen and (min-width: 1024px) {
         /*...*/
      }
      
      /* large desktop */
      @media screen and (min-width: 1480px) {
         /*...*/
      }
   }
}
```

